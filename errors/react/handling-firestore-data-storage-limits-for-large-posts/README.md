# 🐞 Handling Firestore Data Storage Limits for Large Posts


## Description of the Error

Developers frequently encounter issues when storing large amounts of data within Firestore, particularly when dealing with rich text posts containing images or videos.  Firestore has document size limits (currently 1 MB). Attempting to store a post exceeding this limit results in an error, preventing successful data persistence.  This error usually manifests as a `FAILED_PRECONDITION` error in your Firebase console or client-side error logs.  The error message might not explicitly mention the size limit but rather indicate a document being too large.  This can lead to application crashes or data loss if not handled properly.


## Fixing Step-by-Step

This example demonstrates how to handle large posts by storing the main text content directly in Firestore, but storing media (images in this case) in Firebase Storage and only referencing them in Firestore.


**Step 1:  Project Setup**

Ensure you have the Firebase Admin SDK and Firebase Storage SDK installed.  If using client-side code (e.g., React, Angular, etc.), install the appropriate client SDKs.

```bash
npm install firebase @firebase/storage
```

**Step 2: Store Images in Firebase Storage**

This function uploads an image to Firebase Storage and returns the download URL.

```javascript
import { getStorage, ref, uploadBytesResumable, getDownloadURL } from "firebase/storage";

async function uploadImage(image, postId) {
  const storage = getStorage();
  const storageRef = ref(storage, `posts/${postId}/${image.name}`); // Organize images by post ID
  const uploadTask = uploadBytesResumable(storageRef, image);

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
        reject(error); // Handle unsuccessful uploads
      }, 
      () => {
        getDownloadURL(uploadTask.snapshot.ref).then((downloadURL) => {
          resolve(downloadURL);
        });
      }
    );
  });
}
```


**Step 3: Store Post Data in Firestore**

This function creates a Firestore document containing post metadata and image URLs.

```javascript
import { getFirestore, collection, addDoc } from "firebase/firestore";

async function createPost(postData, imageURLs) {
  const db = getFirestore();
  const docRef = await addDoc(collection(db, "posts"), {
    title: postData.title,
    content: postData.content, // Main text content
    images: imageURLs, // Array of image URLs from Storage
    timestamp: new Date(), // Add a timestamp
  });
  console.log("Document written with ID: ", docRef.id);
}
```


**Step 4: Integrate and Use the Functions**


```javascript
// ... (Import necessary functions and modules) ...

async function handlePostCreation(postData, images) {
  const imageURLs = [];
  try {
      for (const image of images) {
          const url = await uploadImage(image, postData.id); // Assuming postData has an id
          imageURLs.push(url);
      }
      await createPost(postData, imageURLs);
  } catch (error) {
    console.error("Error creating post:", error);
    // Handle error appropriately (e.g., display an error message to the user)
  }
}


// Example usage:
const postData = {
  id: 'uniquePostId', //Generate unique ID
  title: "My Awesome Post",
  content: "This is the main text content of my post.",
};

const images = [ /* Array of File objects representing images */ ];

handlePostCreation(postData, images);

```


## Explanation

This solution leverages Firebase Storage to handle large files (images) separately from the main post data stored in Firestore.  By referencing the image URLs in Firestore, we avoid exceeding the document size limits. This approach maintains data integrity and improves performance as Firestore only needs to retrieve smaller, metadata-rich documents.

## External References

* [Firestore Data Storage Limits](https://firebase.google.com/docs/firestore/quotas)
* [Firebase Storage Documentation](https://firebase.google.com/docs/storage)
* [Firebase Admin SDK](https://firebase.google.com/docs/admin/setup)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

