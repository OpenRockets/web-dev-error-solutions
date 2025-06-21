# 🐞 Handling Firestore Data Limits When Storing Large Posts


This document addresses a common issue developers encounter when storing large text posts (e.g., blog posts, articles) in Firebase Firestore: exceeding the document size limit.  Firestore has a limit on the size of a single document, and exceeding this limit results in errors during write operations.

**Description of the Error:**

When attempting to store a large post exceeding Firestore's document size limit (currently 1 MB), you will encounter an error similar to this:

```
Error: Document size exceeds the maximum allowed size (1 MiB).
```

This error prevents the entire post from being saved to Firestore.  This is especially problematic with rich text posts containing images or embedded media.

**Fixing Step-by-Step (Code):**

This solution involves splitting the post content into smaller, manageable chunks and storing them as separate subcollections within a main post document.

**1. Data Structure:**

We'll use a structure where each post has a main document storing metadata, and a subcollection to hold the post's content in smaller chunks.


```json
// Post document
{
  "postId": "post123",
  "title": "My Awesome Blog Post",
  "author": "John Doe",
  "createdAt": 1678886400000,
  "contentChunks": [ // Array of chunk references
      {
          "chunkId": "chunk1",
          "order": 1
      },
      {
          "chunkId": "chunk2",
          "order": 2
      }
  ]
}

// Subcollection "content" (Documents within the post document)
// chunk1
{
  "chunkId": "chunk1",
  "content": "This is the first part of the blog post..."
}
// chunk2
{
  "chunkId": "chunk2",
  "content": "This is the second part of the blog post..."
}

```


**2. JavaScript Code (using Firebase Admin SDK):**


```javascript
const admin = require('firebase-admin');
admin.initializeApp();
const db = admin.firestore();

async function storeLargePost(postId, title, author, content) {
  const chunkSize = 5000; // Adjust as needed.  Smaller chunks mean more overhead, larger means higher risk of exceeding limits.
  const chunks = [];
  const contentChunksRefs = [];

  let currentChunk = "";
  for (let i = 0; i < content.length; i++) {
    currentChunk += content[i];
    if (currentChunk.length >= chunkSize) {
      const chunkId = `chunk${chunks.length + 1}`;
      const chunkRef = db.collection("posts").doc(postId).collection("content").doc(chunkId);
      await chunkRef.set({ chunkId, content: currentChunk });
      chunks.push({chunkId, order: chunks.length + 1}); // keep track of references
      contentChunksRefs.push({chunkId, order: chunks.length});
      currentChunk = "";
    }
  }

  // Add the last chunk if any
  if (currentChunk.length > 0) {
    const chunkId = `chunk${chunks.length + 1}`;
    const chunkRef = db.collection("posts").doc(postId).collection("content").doc(chunkId);
    await chunkRef.set({ chunkId, content: currentChunk });
    chunks.push({chunkId, order: chunks.length + 1});
    contentChunksRefs.push({chunkId, order: chunks.length});
  }


  const postRef = db.collection("posts").doc(postId);
  await postRef.set({
    postId,
    title,
    author,
    createdAt: admin.firestore.FieldValue.serverTimestamp(),
    contentChunks: contentChunksRefs
  });

  console.log("Post stored successfully!");
}


// Example usage:
const longPostContent = "This is a very long blog post that exceeds the Firestore document size limit.  This is a very long blog post that exceeds the Firestore document size limit.  This is a very long blog post that exceeds the Firestore document size limit.  This is a very long blog post that exceeds the Firestore document size limit.  This is a very long blog post that exceeds the Firestore document size limit. ";


storeLargePost("post123", "My Long Post", "Jane Doe", longPostContent).catch(err => console.error("Error storing post:", err));

```


**3. Retrieving the Post:**

You'll need to retrieve the chunks and concatenate them on the client-side:


```javascript
//Client side (e.g., using Firebase web SDK)

async function getPost(postId){
    const postDoc = await db.collection('posts').doc(postId).get();
    const postData = postDoc.data();
    let fullContent = '';

    for (const chunkRef of postData.contentChunks){
        const chunkDoc = await db.collection('posts').doc(postId).collection('content').doc(chunkRef.chunkId).get();
        fullContent += chunkDoc.data().content;
    }
    return { ...postData, fullContent};
}

```


**Explanation:**

The code divides the post content into smaller chunks of a specified size (`chunkSize`).  Each chunk is stored as a separate document in a subcollection. The main post document then contains references (ids) to these chunks, allowing retrieval and reassembly.  This approach avoids exceeding the document size limit.


**External References:**

* [Firestore Data Size Limits](https://firebase.google.com/docs/firestore/quotas)
* [Firebase Admin SDK](https://firebase.google.com/docs/admin/setup)
* [Firebase Web SDK](https://firebase.google.com/docs/web/setup)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

