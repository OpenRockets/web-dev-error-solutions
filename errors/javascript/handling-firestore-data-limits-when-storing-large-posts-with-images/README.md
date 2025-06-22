# 🐞 Handling Firestore Data Limits When Storing Large Posts with Images


## Description of the Error

Developers often encounter issues when storing large amounts of data, particularly rich media like images within their posts in Firestore.  Firestore has document size limits (currently 1 MB).  Attempting to store large images directly within a Firestore document for each post will lead to errors if the combined size of the post data and image(s) exceeds this limit.  This results in a failure to write the document to Firestore, often manifesting as an error message indicating a document size exceeding the limit or a general write failure.

## Fixing the Problem: Step-by-Step Code

This solution uses Cloud Storage for images and stores only references to the images in Firestore.

**Step 1: Upload Images to Cloud Storage**

First, we'll use the Firebase Admin SDK to upload images to Cloud Storage.  This code assumes you already have a Firebase project set up and the necessary credentials configured.

```javascript
const { initializeApp } = require('firebase/app');
const { getStorage, ref, uploadBytesResumable, getDownloadURL } = require('firebase/storage');

// Your Firebase configuration
const firebaseConfig = {
  // ... your firebase config ...
};

const app = initializeApp(firebaseConfig);
const storage = getStorage(app);

async function uploadImage(file, postID) {
  const storageRef = ref(storage, `posts/${postID}/${file.name}`);
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


//Example Usage
const file = /* your image file */; //replace with actual file
const postID = 'yourPostID'; // replace with your post ID

uploadImage(file, postID).then((downloadURL) => {
  console.log('File available at', downloadURL);
  //Store downloadURL in Firestore
}).catch((error) => {
    console.error('Upload failed:', error);
});

```


**Step 2: Store Image URLs in Firestore**

After uploading, store only the Cloud Storage URLs in your Firestore documents. This keeps document sizes small.

```javascript
import { getFirestore, doc, setDoc } from "firebase/firestore";
const db = getFirestore(app);

async function createPost(postID, text, imageUrl) {
    try {
        await setDoc(doc(db, "posts", postID), {
            text: text,
            imageUrl: imageUrl,
            // ... other post data
        });
    } catch (error) {
        console.error("Error adding document: ", error);
    }
}


//Example Usage:
const postID = 'yourPostID';
const text = "This is your post";
const imageUrl = 'yourImageURL';

createPost(postID, text, imageUrl);
```


## Explanation

This approach leverages Cloud Storage's scalability to handle large files.  Firestore is best suited for structured data and metadata, not large binary files. By separating image storage from your post data in Firestore, you avoid exceeding document size limits.  The application fetches the images from Cloud Storage only when needed for display, optimizing performance and storage costs.


## External References

* [Firestore Data Types and Limits](https://firebase.google.com/docs/firestore/quotas)
* [Firebase Storage Documentation](https://firebase.google.com/docs/storage)
* [Firebase Admin SDK](https://firebase.google.com/docs/admin/setup)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

