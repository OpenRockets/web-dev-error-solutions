# 🐞 Handling Firestore Data for Posts: Efficiently Storing and Retrieving Large Images


This document addresses a common problem developers encounter when using Firebase Firestore to store and retrieve posts containing large images: **exceeding Firestore's document size limits and impacting performance**.  Firestore has a limit on the size of individual documents (currently 1 MB).  Large images easily exceed this limit, leading to errors and slow loading times.

**Description of the Error:**

When attempting to store a post with a large image directly within a Firestore document, you'll likely encounter an error indicating that the document size exceeds the limit. This can manifest as a `FieldValue.serverTimestamp()` error or a generic "document too large" error depending on the specific circumstances and your code.  The application may crash or simply fail to update the database.  Retrieving posts with embedded large images will also be slow and inefficient.

**Fixing the Problem: Storage + References**

The solution is to use Firebase Storage to store the images and then store only a reference (URL) to the image in Firestore. This keeps Firestore documents small and efficient, ensuring fast reads and writes.

**Step-by-Step Code (JavaScript):**

First, ensure you have the necessary Firebase packages installed:

```bash
npm install firebase @firebase/storage
```

**1. Upload Image to Firebase Storage:**

```javascript
import { getStorage, ref, uploadBytesResumable, getDownloadURL } from "firebase/storage";

async function uploadImage(image, postId) {
  const storage = getStorage();
  const storageRef = ref(storage, `posts/${postId}/image.jpg`); // Customize path as needed

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
      console.error("Upload failed:", error);
    },
    () => {
      // Handle successful uploads on complete
      // Get the download URL
      getDownloadURL(uploadTask.snapshot.ref).then((downloadURL) => {
        console.log('File available at', downloadURL);
        return downloadURL; //Return the download URL for storage in Firestore
      });
    }
  );
}

```

**2. Store Post Data in Firestore (including image URL):**

```javascript
import { getFirestore, doc, setDoc } from "firebase/firestore";

async function addPost(postData, imageUrl) {
  const db = getFirestore();
  const postRef = doc(db, "posts", postData.postId);

  try {
    await setDoc(postRef, {
      ...postData, // other post data like title, content, author etc.
      imageUrl: imageUrl,
    });
    console.log("Post added successfully!");
  } catch (error) {
    console.error("Error adding post:", error);
  }
}
```

**3. Retrieving Post Data (and Image URL):**

```javascript
import { getFirestore, doc, getDoc } from "firebase/firestore";

async function getPost(postId) {
  const db = getFirestore();
  const postRef = doc(db, "posts", postId);
  const docSnap = await getDoc(postRef);

  if (docSnap.exists()) {
    return docSnap.data();
  } else {
    console.log("No such document!");
    return null;
  }
}
```

**Explanation:**

The improved approach separates image storage from post data.  Large images are handled by Firebase Storage, a service designed for efficient storage and retrieval of binary data.  Firestore then only stores a lightweight URL pointing to the image. This significantly reduces document sizes, leading to better performance and avoiding size-related errors.


**External References:**

* [Firebase Storage Documentation](https://firebase.google.com/docs/storage)
* [Firestore Data Limits](https://firebase.google.com/docs/firestore/quotas)
* [Firebase JavaScript SDK](https://firebase.google.com/docs/web/setup)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

