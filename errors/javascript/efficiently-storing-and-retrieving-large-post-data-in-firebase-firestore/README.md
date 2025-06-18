# 🐞 Efficiently Storing and Retrieving Large Post Data in Firebase Firestore


This document addresses a common issue developers face when managing posts with large amounts of data in Firebase Firestore: performance degradation due to inefficient data structuring and retrieval.  Storing entire posts, including potentially large images or videos directly within Firestore documents, can lead to slow read and write operations, especially as your application scales.  This problem manifests itself in slow loading times for users, increased latency, and potentially exceeding Firestore's document size limits.

## Description of the Error

The core problem arises from violating the principle of efficient data modeling for Firestore.  Trying to store large binary data (images, videos) directly within Firestore documents results in:

* **Slow read speeds:** Downloading large documents takes longer, impacting user experience.
* **Slow write speeds:** Uploading large documents can lead to timeouts and errors.
* **Document size limits:** Firestore imposes limits on document size. Exceeding this limit will result in errors.
* **Inefficient queries:** Retrieving specific fields from large documents is less efficient than retrieving them from smaller, targeted documents.


## Step-by-Step Code Solution (Using Cloud Storage and Firestore)

This solution leverages Firebase Cloud Storage to store the large binary data (images, videos) and Firestore to store metadata and references.

**1. Upload Image to Cloud Storage:**

```javascript
import { getStorage, ref, uploadBytesResumable, getDownloadURL } from "firebase/storage";

async function uploadImage(image, postId) {
  const storage = getStorage();
  const storageRef = ref(storage, `posts/${postId}/image.jpg`); // Customizable path

  const uploadTask = uploadBytesResumable(storageRef, image);

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
      console.error("Error uploading image:", error);
      // ... error handling logic ...
    }, 
    () => {
      // Handle successful uploads on complete
      getDownloadURL(uploadTask.snapshot.ref).then((downloadURL) => {
        console.log('File available at', downloadURL);
        //Store downloadURL in Firestore
        return downloadURL;
      });
    }
  );
}
```

**2. Store Metadata in Firestore:**

```javascript
import { addDoc, collection, serverTimestamp } from "firebase/firestore";
import { db } from "./firebaseConfig"; //Import your Firebase configuration

async function createPost(title, content, imageUrl) {
  try {
    const docRef = await addDoc(collection(db, "posts"), {
      title: title,
      content: content,
      imageUrl: imageUrl, // Store the URL from Cloud Storage
      timestamp: serverTimestamp(),
    });
    console.log("Document written with ID: ", docRef.id);
  } catch (e) {
    console.error("Error adding document: ", e);
  }
}


// Example usage combining uploadImage and createPost functions:
const image = /* your image file */;
const postId = /* generate a unique ID for the post */;

uploadImage(image, postId)
  .then((downloadURL) => {
    createPost("My Post Title", "My Post Content", downloadURL);
  })
  .catch((error) => {
    console.error("Failed to upload image or create post:", error);
  });

```

**3. Retrieve Post Data:**

```javascript
import { getDoc, doc, getFirestore } from "firebase/firestore";

async function getPost(postId) {
    const db = getFirestore();
    const docRef = doc(db, "posts", postId);
    const docSnap = await getDoc(docRef);

    if (docSnap.exists()) {
        return docSnap.data();
    } else {
        console.log("No such document!");
        return null;
    }
}

getPost("yourPostId").then((postData) => {
    console.log(postData); // access title, content, and imageUrl
    //use postData.imageUrl to load from Cloud Storage
});

```



## Explanation

This approach separates large binary data from metadata.  Cloud Storage is optimized for storing and serving files, while Firestore is ideal for structured data and fast querying of metadata.  This improves performance, scalability, and adherence to Firestore's document size limits.  The application retrieves the image from Cloud Storage using the URL stored in Firestore, improving efficiency and user experience.


## External References

* [Firebase Storage Documentation](https://firebase.google.com/docs/storage)
* [Firebase Firestore Documentation](https://firebase.google.com/docs/firestore)
* [Firebase JavaScript SDK](https://firebase.google.com/docs/web/setup)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

