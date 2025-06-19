# 🐞 Efficiently Storing and Retrieving Large Post Data in Firebase Firestore


## Problem Description:  Performance Degradation with Large Post Data

A common issue developers encounter when using Firebase Firestore to store and retrieve posts (especially those containing rich media like images, videos, or extensive text) is performance degradation.  Storing large amounts of data directly within a single Firestore document can lead to slow read and write operations, exceeding Firestore's document size limits (currently 1 MB), and ultimately impacting the user experience.  Retrieving large documents also consumes significant bandwidth and client-side processing power.


## Solution:  Data Denormalization and Optimized Data Structure

The solution involves implementing data denormalization and structuring your data to minimize the amount of data retrieved in a single operation.  Instead of storing all post content in a single document, we'll separate it into smaller, manageable chunks.

## Step-by-Step Code Fix (using Node.js with Firebase Admin SDK)

This example demonstrates how to store post metadata in one document and store the actual post content (like a long text body) separately.

**1. Project Setup:**

```bash
npm install firebase-admin
```

**2. Firebase Initialization:**

```javascript
const admin = require('firebase-admin');
const serviceAccount = require('./path/to/serviceAccountKey.json'); // Replace with your service account key

admin.initializeApp({
  credential: admin.credential.cert(serviceAccount),
  databaseURL: "YOUR_DATABASE_URL" // Replace with your database URL
});

const db = admin.firestore();
```

**3. Post Data Structure:**

Instead of:

```javascript
// Inefficient - Large document
const post = {
  title: "My Awesome Post",
  author: "JohnDoe",
  content: "This is a very long post with lots and lots of text...", //Potentially >1MB
  images: ["image1.jpg", "image2.jpg"]
};
```

We'll use:

```javascript
// Efficient - Separated data
const postMetadata = {
  postId: "uniquePostId",
  title: "My Awesome Post",
  author: "JohnDoe",
  contentRef: db.doc("postsContent/uniquePostId"), //Reference to the content document
  images: ["image1.jpg", "image2.jpg"]
};

const postContent = {
  text: "This is a very long post with lots and lots of text...",
};
```

**4. Storing the Post:**

```javascript
async function createPost(postMetadata, postContent) {
  try {
    const metadataRef = db.collection('posts').doc();
    const contentRef = metadataRef.id; // Use metadataRef.id to get unique id and update reference
    await db.collection('posts').doc(metadataRef.id).set({...postMetadata, postId: metadataRef.id});
    await db.collection('postsContent').doc(contentRef).set(postContent);
    console.log('Post created successfully!');
  } catch (error) {
    console.error('Error creating post:', error);
  }
}


//Example usage
const metadata = {
    title: "My Awesome Post 2",
    author: "JaneDoe",
    images: ["image3.jpg", "image4.jpg"]
};

const content = {
    text: "Another long post."
}

createPost(metadata, content);
```


**5. Retrieving the Post:**

```javascript
async function getPost(postId) {
  try {
    const metadataDoc = await db.collection('posts').doc(postId).get();
    if (!metadataDoc.exists) {
      return null;
    }
    const metadata = metadataDoc.data();
    const contentDoc = await metadata.contentRef.get();
    const content = contentDoc.data();
    return { ...metadata, content };
  } catch (error) {
    console.error('Error retrieving post:', error);
    return null;
  }
}

getPost("uniquePostId").then(post => console.log(post));

```


## Explanation:

By separating the post metadata (smaller, frequently accessed information) from the post content (potentially large text or binary data), we improve performance in several ways:

* **Reduced Document Size:** Firestore document size limits are avoided.
* **Faster Queries:** Retrieving only the metadata is much faster than fetching the entire post.
* **Efficient Data Retrieval:** Only necessary data is retrieved.
* **Improved Scalability:** The system is better equipped to handle a large number of posts.

## External References:

* [Firebase Firestore Documentation](https://firebase.google.com/docs/firestore)
* [Firebase Admin SDK (Node.js)](https://firebase.google.com/docs/admin/setup)
* [Data Modeling in Firestore](https://firebase.google.com/docs/firestore/modeling)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

