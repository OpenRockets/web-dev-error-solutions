# 🐞 Efficiently Storing and Querying Large Posts in Firebase Firestore


## Description of the Problem

A common issue developers face with Firebase Firestore when working with posts (e.g., blog posts, social media updates) involves efficiently storing and querying large amounts of data.  Storing entire posts, especially those with rich text, images, and potentially many comments, directly within a single Firestore document can lead to several problems:

* **Document Size Limits:** Firestore has document size limits (currently 1 MB).  Large posts quickly exceed this limit, resulting in errors when attempting to write or update them.
* **Inefficient Queries:** Querying across large documents is slow. If your posts contain extensive content, filtering and sorting can become computationally expensive and negatively impact application performance.
* **Data Redundancy:** If you need to show similar content across multiple posts (e.g., author information), storing that data repeatedly within each post leads to data redundancy and wasted storage.

This document outlines a solution that addresses these issues by employing a normalized data model and leveraging Firestore's features effectively.


## Step-by-Step Solution: Normalizing Post Data

This solution normalizes the data by breaking down the post into smaller, manageable documents.

**1. Data Model:**

We'll use three collections:

* **`posts`:** Contains a concise summary of each post (ID, title, author ID, creation timestamp, etc.).  This collection will be used for efficient querying and listing posts.
* **`postContent`:** Contains the main body of each post, allowing for larger text and richer content without hitting document size limits.  Each document will have an ID that matches the `postId` in the `posts` collection.
* **`users`:** Stores user information (ID, name, profile picture URL, etc.). This avoids redundancy by centralizing user data.


**2. Code (using JavaScript/Node.js):**

This example demonstrates creating and retrieving a post.  You'll need to adapt it to your specific application framework (e.g., React, Angular, Flutter).

```javascript
const admin = require('firebase-admin');
admin.initializeApp();
const db = admin.firestore();

// Create a new post
async function createPost(postDetails) {
  try {
    const { title, authorId, content } = postDetails;
    const postRef = await db.collection('posts').add({
      title: title,
      authorId: authorId,
      createdAt: admin.firestore.FieldValue.serverTimestamp(),
    });
    const postId = postRef.id;
    await db.collection('postContent').doc(postId).set({
      content: content,
    });
    console.log('Post created successfully with ID:', postId);
    return postId;
  } catch (error) {
    console.error('Error creating post:', error);
    throw error;
  }
}


//Retrieve a Post
async function getPost(postId) {
  try {
    const postDoc = await db.collection('posts').doc(postId).get();
    if (!postDoc.exists) {
      throw new Error(`Post with ID ${postId} not found`);
    }

    const postContentDoc = await db.collection('postContent').doc(postId).get();
    const postData = postDoc.data();
    const postContent = postContentDoc.data();

    const authorDoc = await db.collection('users').doc(postData.authorId).get();
    const authorData = authorDoc.data();

    return {...postData, content: postContent.content, author: authorData};

  } catch (error) {
    console.error('Error getting post:', error);
    throw error;
  }
}


// Example Usage
async function main(){
  const newPost = await createPost({
    title: "My first blog post",
    authorId: "user123",
    content: "This is the content of my first blog post. It can be very long and detailed!"
  });
  console.log("New post ID:", newPost);

  const retrievedPost = await getPost(newPost);
  console.log("Retrieved post:", retrievedPost);
}

main();
```

**3. Explanation:**

This code separates post metadata from its content, allowing for efficient querying of metadata (titles, authors, timestamps) while handling large text in a separate document. The `getPost` function demonstrates how to retrieve both the metadata and the content efficiently using a single call to the `posts` collection and one to the `postContent` collection.


## External References

* **Firestore Data Modeling:** [https://firebase.google.com/docs/firestore/data-model](https://firebase.google.com/docs/firestore/data-model)
* **Firestore Security Rules:** [https://firebase.google.com/docs/firestore/security/get-started](https://firebase.google.com/docs/firestore/security/get-started)  (Crucial for securing your data)
* **Firestore Querying:** [https://firebase.google.com/docs/firestore/query-data/queries](https://firebase.google.com/docs/firestore/query-data/queries)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

