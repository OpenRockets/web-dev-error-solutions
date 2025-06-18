# 🐞 Handling Firestore Data Limits When Storing Large Posts with Images


## Description of the Error

A common issue when using Firebase Firestore to store blog posts or similar content with images is exceeding Firestore's document size limits.  Firestore documents have a maximum size of 1 MB.  If you're storing large images directly within the document, or have a very large amount of text, you'll quickly hit this limit.  This leads to errors during write operations, preventing your application from saving the post.  The specific error message might vary, but it will generally indicate a data size exceeding the limit.

## Fixing the Problem Step-by-Step

This solution involves storing images separately in Firebase Storage and referencing them in Firestore. This approach keeps your Firestore documents small and manageable while still allowing you to associate images with your posts.

**Step 1: Upload Images to Firebase Storage**

First, upload your images to Firebase Storage.  This requires the Firebase Storage SDK.  The following code snippet demonstrates uploading an image using the JavaScript SDK.  Remember to replace placeholders like `<your-storage-bucket>` with your actual values.

```javascript
import { getStorage, ref, uploadBytesResumable, getDownloadURL } from "firebase/storage";

const storage = getStorage(); // Initialize Firebase Storage

async function uploadImage(image, postId) {
  const storageRef = ref(storage, `posts/${postId}/${image.name}`); // Create a reference to the image location

  const uploadTask = uploadBytesResumable(storageRef, image); // Start uploading the image

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
    },
    () => {
      // Handle successful uploads on complete
      getDownloadURL(uploadTask.snapshot.ref).then((downloadURL) => {
        console.log('File available at', downloadURL);
        // Use the downloadURL to update your Firestore document
        return downloadURL;
      });
    }
  );
}


// Example Usage:
const image = /* Your image file object */;
const postId = 'yourPostId';

uploadImage(image, postId)
  .then(downloadURL => {
    //Now you can store this downloadURL in firestore
  })
  .catch(error => console.error("Error uploading and getting URL", error));


```

**Step 2: Update Firestore Document with Image URL**

Once the image is uploaded, retrieve the download URL and store it in your Firestore document.  This URL acts as a reference to the image.

```javascript
import { collection, addDoc } from "firebase/firestore";
import { db } from './firebaseConfig' //Import your Firestore instance

async function addPostToFirestore(postData, imageUrl){
    try {
        const docRef = await addDoc(collection(db, "posts"), {
            title: postData.title,
            content: postData.content,
            imageUrl: imageUrl,
            // ... other post data
        });
        console.log("Document written with ID: ", docRef.id);
    } catch (e) {
        console.error("Error adding document: ", e);
    }
}


// Example Usage (after successful uploadImage call):
const postData = {
  title: "My Awesome Post",
  content: "This is the content of my awesome post...",
  // ... other post data
};

addPostToFirestore(postData, downloadURL); //Pass the download URL here.


```

## Explanation

This solution follows a common pattern for handling large files in NoSQL databases like Firestore.  By separating the image data from the document data, we avoid exceeding the size limits. Firestore is optimized for storing structured data, while Firebase Storage is ideal for storing unstructured binary data like images and videos.  Using this approach, you maintain a clean, efficient data model and avoid potential errors related to exceeding document size limits.


## External References

* **Firebase Storage Documentation:** [https://firebase.google.com/docs/storage](https://firebase.google.com/docs/storage)
* **Firebase Firestore Documentation:** [https://firebase.google.com/docs/firestore](https://firebase.google.com/docs/firestore)
* **Firebase JavaScript SDK:** [https://firebase.google.com/docs/web/setup](https://firebase.google.com/docs/web/setup)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

