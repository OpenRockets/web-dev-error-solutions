# 🐞 Efficiently Storing and Querying Large Posts in Firebase Firestore


This document addresses a common issue developers encounter when managing posts (e.g., blog posts, social media updates) with rich text content in Firebase Firestore: **inefficient data storage and slow query performance due to large document sizes**.  Storing large text fields directly within Firestore documents can lead to performance bottlenecks, especially when retrieving or filtering posts based on content.

## The Problem

Firestore's optimal performance relies on relatively small document sizes.  Storing large text content (like blog posts or detailed descriptions) directly within a document can exceed the optimal size, resulting in:

* **Slow read speeds:** Retrieving documents with large text fields takes longer.
* **Inefficient indexing:**  Firestore's indexing mechanisms become less effective with large documents, making queries based on text content slow or impossible.
* **Increased costs:**  Larger documents contribute to higher Firestore usage costs.


## The Solution: Separate Text Content into a Storage Service

The most effective solution is to separate the rich text content from the main post document and store it in a cloud storage service like Firebase Storage.  The Firestore document will then contain only a reference (URL) to the text in Storage.

## Step-by-Step Code Example (JavaScript)

This example demonstrates storing a post's title and a reference to its content stored in Firebase Storage.

**1. Install necessary packages:**

```bash
npm install firebase @firebase/storage
```

**2. Initialize Firebase:**

```javascript
import { initializeApp } from "firebase/app";
import { getFirestore, collection, addDoc } from "firebase/firestore";
import { getStorage, ref, uploadBytesResumable, getDownloadURL } from "firebase/storage";

// Your Firebase config
const firebaseConfig = {
  // ... your config ...
};

const app = initializeApp(firebaseConfig);
const db = getFirestore(app);
const storage = getStorage(app);
```

**3. Function to create a new post:**

```javascript
async function createPost(title, content) {
  try {
    // 1. Upload the text content to Firebase Storage.
    const storageRef = ref(storage, `posts/${Date.now()}.txt`); //Generate Unique Filename
    const uploadTask = uploadBytesResumable(storageRef, new Blob([content]));

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
        console.error(error);
      },
      () => {
        // Handle successful uploads on complete
        // Get the download URL from ref.
        getDownloadURL(uploadTask.snapshot.ref).then((downloadURL) => {
            // 2. Store the post metadata (title and storage URL) in Firestore.
            addDoc(collection(db, "posts"), {
                title: title,
                contentUrl: downloadURL
            }).then(() => {
                console.log("Post created successfully!");
            }).catch((error) => {
                console.error("Error creating post:", error);
            });
        });
      }
    );

  } catch (error) {
    console.error("Error creating post:", error);
  }
}
```

**4. Example usage:**

```javascript
const postTitle = "My Awesome Post";
const postContent = "This is the content of my awesome post. It can be very long!";

createPost(postTitle, postContent);
```

## Explanation

This approach significantly improves performance and scalability:

* **Smaller Documents:** Firestore documents now only contain metadata, keeping their size small and improving query performance.
* **Scalability:**  Storage is designed to handle large files efficiently.
* **Efficient Queries:** Queries on the Firestore `posts` collection are fast because documents are small.  You can efficiently query based on the `title` field.
* **Content Retrieval:** You fetch the content from Firebase Storage using the URL stored in the Firestore document when needed.


## External References

* **Firebase Storage Documentation:** [https://firebase.google.com/docs/storage](https://firebase.google.com/docs/storage)
* **Firebase Firestore Documentation:** [https://firebase.google.com/docs/firestore](https://firebase.google.com/docs/firestore)
* **Firebase Best Practices:** [https://firebase.google.com/docs/firestore/best-practices](https://firebase.google.com/docs/firestore/best-practices)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

