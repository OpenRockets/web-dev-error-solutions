# 🐞 Handling Firestore's "out of range" error when storing large posts


## Description of the Error

When storing large amounts of data, particularly rich text or multimedia content within Firestore documents representing posts, you might encounter an error indicating that the data exceeds Firestore's document size limit. This limit is currently 1 MB.  Exceeding this limit results in a `FAILED_PRECONDITION` error with a message indicating that the document is too large.  This is common when embedding large images, videos, or extensive text directly into the Firestore document.


## Fixing the Error: Step-by-Step Code

This solution uses Cloud Storage for storing the large media files and only stores references to them in Firestore.

**1. Project Setup (Assuming you already have a Firebase project and Firestore database):**

Make sure you have the necessary Firebase libraries installed:

```bash
npm install firebase
```

**2. Cloud Storage Configuration:**

In your Firebase project, enable Cloud Storage.  You'll need a service account key file for server-side operations.

**3.  Upload to Cloud Storage:**

This function uploads a file to Cloud Storage and returns the download URL.

```javascript
const { initializeApp } = require('firebase/app');
const { getStorage, ref, uploadBytesResumable, getDownloadURL } = require('firebase/storage');

const firebaseConfig = {
  // Your Firebase config here
};

const app = initializeApp(firebaseConfig);
const storage = getStorage(app);

async function uploadFileToStorage(file, filePath) {
  const storageRef = ref(storage, filePath);
  const uploadTask = uploadBytesResumable(storageRef, file);

  return new Promise((resolve, reject) => {
    uploadTask.on('state_changed',
      (snapshot) => {
        // Observe state change events such as progress, pause, and resume
        // Get task progress, including the number of bytes uploaded and the total number of bytes to be uploaded
        const progress = (snapshot.bytesTransferred / snapshot.totalBytes) * 100;
        console.log('Upload is ' + progress + '% done');
        switch (snapshot.state) {
          case 'paused':
            console.log('Upload is paused');
            break;
          case 'running':
            console.log('Upload is running');
            break;
        }
      },
      (error) => {
        // Handle unsuccessful uploads
        reject(error);
      },
      () => {
        // Handle successful uploads on complete
        getDownloadURL(uploadTask.snapshot.ref).then((downloadURL) => {
          resolve(downloadURL);
        });
      }
    );
  });
}

//Example Usage:
//const file = await fetch('image.jpg').then(r => r.blob());
//const url = await uploadFileToStorage(file, 'posts/post1/image.jpg');
//console.log("File URL:", url);

module.exports = {uploadFileToStorage};
```

**4. Storing Post Data in Firestore:**

Now, instead of storing the media directly, store only the Cloud Storage URLs:

```javascript
import { db } from './firebase'; // Import your Firestore instance
import {uploadFileToStorage} from './cloudStorage'; //Import Cloud Storage function

async function createPost(post) {
  //Upload the images first
  const imageUrls = await Promise.all(post.images.map(async (image) => {
    return await uploadFileToStorage(image, `posts/${post.id}/${image.name}`);
  }));

  const newPost = {
    title: post.title,
    content: post.content, //Keep text content in Firestore
    images: imageUrls,
    // ... other data
    timestamp: new Date()
  };

  await db.collection('posts').doc(post.id).set(newPost);
}
```

**5. Retrieving Post Data:**

When retrieving posts, fetch the media from Cloud Storage using the URLs stored in Firestore:

```javascript
import { db } from './firebase';
async function getPost(postId) {
  const docSnap = await db.collection('posts').doc(postId).get();
  if (docSnap.exists()) {
    const post = docSnap.data();
    return post;
  } else {
    return null;
  }
}


//Example usage
getPost('somePostId').then((post) => {
    console.log('Post:', post);
    //Access Images using post.images
});
```



## Explanation

This solution addresses the "out of range" error by offloading large media files to Cloud Storage, a more suitable service for storing binary data.  Firestore is optimized for structured data and document-level operations. By separating the media and metadata, you avoid exceeding the document size limit while maintaining a clean and efficient data structure. The URLs stored in Firestore act as pointers to the files in Cloud Storage, allowing you to easily retrieve the media when needed.


## External References

* **Firebase Firestore Documentation:** [https://firebase.google.com/docs/firestore](https://firebase.google.com/docs/firestore)
* **Firebase Cloud Storage Documentation:** [https://firebase.google.com/docs/storage](https://firebase.google.com/docs/storage)
* **Firebase JavaScript SDK:** [https://firebase.google.com/docs/web/setup](https://firebase.google.com/docs/web/setup)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

