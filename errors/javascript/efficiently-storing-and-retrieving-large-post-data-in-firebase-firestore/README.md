# 🐞 Efficiently Storing and Retrieving Large Post Data in Firebase Firestore


## Problem Description:  Performance Issues with Large Post Data

A common problem when using Firebase Firestore to store and retrieve blog posts or similar content is performance degradation when dealing with large amounts of data within a single document.  Storing extensive text content, images (or their URLs), and other rich media directly within a Firestore document can lead to slow read and write operations, impacting the user experience.  Retrieving a single post might become noticeably slow, and querying multiple posts could be prohibitively expensive.  This is because Firestore charges based on document size and the amount of data read/written.

## Solution:  Data Denormalization and Optimized Data Structure

The optimal approach is to denormalize your data and strategically distribute information across multiple Firestore documents.  Instead of embedding everything in a single "post" document, we'll break it down:

1. **Main Post Document:** Contains essential metadata (title, author, short description, timestamp, etc.).  This remains small and fast to retrieve.

2. **Content Document:** Stores the actual blog post content separately. This allows for efficient partial retrieval if needed.

3. **Media Storage:** Utilize Firebase Storage for images and other media files. The Firestore document will only store the URLs pointing to these files in storage.


## Step-by-Step Code Example (Node.js with Admin SDK)

This example demonstrates creating, updating, and retrieving a post with separated content and media:

**1. Installation:**

```bash
npm install firebase-admin
```

**2. Initialization (index.js):**

```javascript
const admin = require('firebase-admin');
const serviceAccount = require('./serviceAccountKey.json'); // Replace with your service account key

admin.initializeApp({
  credential: admin.credential.cert(serviceAccount),
  databaseURL: "YOUR_DATABASE_URL" // Replace with your database URL
});

const db = admin.firestore();
const storage = admin.storage();
```

**3. Creating a Post:**

```javascript
async function createPost(title, author, shortDescription, content, imageUrl) {
  // Upload image to Firebase Storage (replace with your image handling)
  const bucket = storage.bucket();
  const file = bucket.file(`posts/${Date.now()}.jpg`); //Example filename, adjust accordingly.
  const stream = file.createWriteStream({
    metadata: {
      contentType: 'image/jpeg',
    },
  });

  //This is placeholder for image upload, replace with actual upload
  stream.on('error', err => { console.error(err)});
  stream.on('finish', async () => {
    const publicUrl = await file.getSignedUrl({
          action: 'read',
          expires: '03-09-2491'
        });
    console.log("URL: ", publicUrl[0]);

    const postRef = db.collection('posts').doc();
    const postId = postRef.id;

    await db.collection('posts').doc(postId).set({
      title,
      author,
      shortDescription,
      imageUrl: publicUrl[0], //Store the URL.
      createdAt: admin.firestore.FieldValue.serverTimestamp(),
      contentId: postId //Link to the content document.
    });


    await db.collection('postContent').doc(postId).set({
      content
    });

  });
  stream.end(Buffer.from('Fake Image Data', 'utf8')); //Replace with your actual image data
}

```


**4. Retrieving a Post:**

```javascript
async function getPost(postId) {
  const postDoc = await db.collection('posts').doc(postId).get();
  if (!postDoc.exists) {
    return null;
  }

  const postData = postDoc.data();
  const contentDoc = await db.collection('postContent').doc(postId).get();
  postData.content = contentDoc.data().content;

  return postData;
}
```

**5. Example Usage:**

```javascript
const newPost = async () => {
  await createPost("My Awesome Post", "John Doe", "A short description", "This is the long post content", "image.jpg");
};

const getPostData = async () => {
  let post = await getPost("yourPostId"); //Replace with actual ID
  console.log(post);
};

newPost();
getPostData();
```


## Explanation:

This approach significantly improves performance by:

* **Reduced Document Size:** The main post document only contains metadata, keeping it small and efficient for queries and retrieval.
* **Targeted Retrieval:**  You fetch only the necessary data.  Need the main details? Fetch the "posts" document. Need the full content? Fetch the separate content document.
* **Scalability:**  Handles larger amounts of data much more efficiently than storing everything in a single document.
* **Media Management:**  Offloading media to Firebase Storage leverages its optimized infrastructure for handling large files.


## External References:

* [Firebase Firestore Documentation](https://firebase.google.com/docs/firestore)
* [Firebase Storage Documentation](https://firebase.google.com/docs/storage)
* [Understanding Firestore Pricing](https://firebase.google.com/pricing)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

