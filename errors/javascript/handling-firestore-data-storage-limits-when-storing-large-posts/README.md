# 🐞 Handling Firestore Data Storage Limits When Storing Large Posts


## Description of the Error

A common issue when working with Firebase Firestore and storing blog posts or other content-rich data is exceeding Firestore's document size limits (currently 1 MB).  Attempting to store large posts directly within a single Firestore document can lead to errors such as `FAILED_PRECONDITION: The document size exceeds the maximum allowed size`. This prevents the data from being written to the database.  This problem is often exacerbated by storing images or other large binary data directly within the document.

## Step-by-Step Code Fix: Using Cloud Storage for Media and Referencing in Firestore

This solution leverages Firebase Cloud Storage to store large media files (images, videos, etc.) and then stores only references to these files within Firestore. This keeps Firestore documents small while still providing access to the media.


**1. Set up Firebase Cloud Storage:**

Ensure you have Firebase Cloud Storage configured in your project. This usually involves setting up rules in the Firebase console.  You can refer to the official documentation for detailed instructions: [Firebase Cloud Storage Documentation](https://firebase.google.com/docs/storage)


**2.  Upload Media to Cloud Storage:**

This code snippet demonstrates uploading an image. Adapt as needed for other media types.

```javascript
import { getStorage, ref, uploadBytesResumable, getDownloadURL } from "firebase/storage";

async function uploadImage(image, postID) {
  const storage = getStorage();
  const storageRef = ref(storage, `posts/${postID}/image.jpg`); // Customize path as needed

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
      console.error("Upload Error:", error);
    }, 
    () => {
      // Handle successful uploads on complete
      getDownloadURL(uploadTask.snapshot.ref).then((downloadURL) => {
        console.log('File available at', downloadURL);
        // Store downloadURL in Firestore (see next step)
        return downloadURL;
      });
    }
  );
}

// Example Usage:
const image = /* Your image file */; // Get the image file from input or other source
const postID = "yourPostID"; // Generate a unique ID for your post
uploadImage(image, postID).then(downloadURL => {
  //Use the downloadURL here
  //Example: addDownloadURLToFirestore(postID, downloadURL)
});
```

**3. Store Reference in Firestore:**

After successfully uploading to Cloud Storage, store only the download URL in your Firestore document.

```javascript
import { doc, setDoc, getFirestore } from "firebase/firestore";

async function addDownloadURLToFirestore(postID, downloadURL) {
  const db = getFirestore();
  const postRef = doc(db, "posts", postID);
  await setDoc(postRef, {
    title: "My Post Title",
    content: "This is the post content.",
    imageUrl: downloadURL,
    // ... other post data
  });
}
```

**4. Retrieving Data:**

When retrieving the post data, use the download URL to fetch the image from Cloud Storage.


```javascript
import { getDoc, doc, getFirestore } from "firebase/firestore";
import { getStorage, ref, getDownloadURL } from "firebase/storage";

async function getPost(postID) {
  const db = getFirestore();
  const storage = getStorage();
  const postRef = doc(db, "posts", postID);
  const postSnap = await getDoc(postRef);
  if (postSnap.exists()) {
    const postData = postSnap.data();
    if(postData.imageUrl) {
      const imageRef = ref(storage, postData.imageUrl.split('/o/')[1].split('?')[0]); //Extract image path from url
      const url = await getDownloadURL(imageRef);
      postData.imageUrl = url; //update the url in the postData
    }
    return postData;
  } else {
    return null;
  }
}
```

## Explanation

This approach significantly improves scalability and performance. By separating media from your Firestore data, you avoid exceeding document size limits.  Furthermore, Cloud Storage is optimized for storing and serving large binary files, making the retrieval process more efficient.  The use of asynchronous operations ensures that your application remains responsive while handling potentially long upload and download processes.

## External References

* [Firebase Cloud Storage Documentation](https://firebase.google.com/docs/storage)
* [Firebase Firestore Documentation](https://firebase.google.com/docs/firestore)
* [Firebase JavaScript SDK](https://firebase.google.com/docs/web/setup)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

