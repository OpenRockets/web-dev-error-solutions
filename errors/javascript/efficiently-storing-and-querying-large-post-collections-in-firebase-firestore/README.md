# 🐞 Efficiently Storing and Querying Large Post Collections in Firebase Firestore


## Problem Description:  Performance Degradation with Large Post Datasets

A common issue developers encounter with Firebase Firestore, especially when dealing with social media-style applications featuring posts, is performance degradation as the number of posts increases.  Simply storing all post data in a single collection and querying it directly can lead to slow load times, exceeding Firestore's query limitations (e.g., the 10 MB document size limit or the limitations on the number of documents returned by a single query).  This is often manifested as slow loading times for feeds, search results, or other features relying on retrieving many posts.

## Step-by-Step Solution: Implementing Pagination and Denormalization

This solution demonstrates how to improve performance by using pagination and a degree of denormalization.  We'll assume a simple post structure with `postId`, `userId`, `timestamp`, `content`, and `likes`.


**Step 1:  Data Modeling (Denormalization)**

Instead of storing all post data in a single collection, we create two collections:

* **`posts`:**  This collection stores the core post data. We'll limit the size of each document by only including essential data and references.
* **`userPosts`:**  This collection will store references to user posts, organized by user ID.  This allows for efficient retrieval of a user's posts.  We'll use a subcollection for each user.

**Step 2: Code Implementation (using JavaScript)**

```javascript
// Import necessary Firebase modules
import { db, getFirestore } from "firebase/firestore";
import { addDoc, collection, doc, getDocs, getFirestore, query, where, orderBy, limit, startAfter, collectionGroup, getDoc } from "firebase/firestore";



// Add a new post (requires authentication handling - omitted for brevity)
async function addPost(userId, content) {
  const timestamp = new Date();
  const postRef = await addDoc(collection(db, "posts"), {
    userId: userId,
    timestamp: timestamp,
    content: content,
    likes: 0, //Initialize likes
  });
  await addDoc(collection(db, `userPosts/${userId}/posts`), {
    postId: postRef.id, //reference to post in the posts collection
  });
  return postRef.id;
}

// Fetch posts with pagination (for a feed, for example)
async function fetchPosts(lastPost, limitNum = 10) {
  let q;

  if (lastPost) {
    const lastPostDoc = await getDoc(doc(db, 'posts', lastPost));
    q = query(collection(db, "posts"), orderBy("timestamp", "desc"), startAfter(lastPostDoc), limit(limitNum));
  } else {
    q = query(collection(db, "posts"), orderBy("timestamp", "desc"), limit(limitNum));
  }
  const querySnapshot = await getDocs(q);

  const posts = [];
  querySnapshot.forEach((doc) => {
    posts.push({ ...doc.data(), id: doc.id });
  });
  return {posts, lastPost: posts.length > 0 ? posts[posts.length - 1].id : null};
}

// Fetch a user's posts with pagination
async function fetchUserPosts(userId, lastPostId, limitNum = 10) {
  let q;
  if(lastPostId) {
    const lastPostDoc = await getDoc(doc(db, `userPosts/${userId}/posts`, lastPostId));
    q = query(collection(db, `userPosts/${userId}/posts`), orderBy("postId", "desc"), startAfter(lastPostDoc), limit(limitNum));
  } else {
    q = query(collection(db, `userPosts/${userId}/posts`), orderBy("postId", "desc"), limit(limitNum));
  }
  const querySnapshot = await getDocs(q);

  const postIds = [];
  querySnapshot.forEach((doc) => {
    postIds.push(doc.data().postId);
  });


  let userPosts = [];
  for (let postId of postIds) {
    const postDoc = await getDoc(doc(db, "posts", postId));
    if (postDoc.exists()) {
      userPosts.push({ ...postDoc.data(), id: postId });
    }
  }

  return { userPosts, lastPostId: userPosts.length > 0 ? userPosts[userPosts.length - 1].id : null };
}



// Example usage:
// addPost("user123", "Hello, world!");
// fetchPosts().then(data => console.log(data));
// fetchUserPosts("user123").then(data => console.log(data));


```

**Step 3: Client-Side Pagination Implementation**

On the client-side, you would integrate the `fetchPosts` or `fetchUserPosts` functions into your UI.  After the initial load, when the user scrolls to the bottom, you'd fetch the next page of posts using the `lastPost` or `lastPostId`  returned by the functions.

## Explanation

This approach improves performance by:

* **Reducing document size:** Each document in the `posts` collection is smaller, reducing the data transferred and processed.
* **Targeted Queries:** Queries on `userPosts` are specific to a user, resulting in far fewer documents to retrieve and process than querying the entire `posts` collection.
* **Pagination:** By fetching posts in batches, we avoid retrieving the entire dataset at once, improving initial load times and reducing the load on Firestore.

## External References

* [Firebase Firestore Documentation](https://firebase.google.com/docs/firestore)
* [Firebase Query Limits](https://firebase.google.com/docs/firestore/query-data/query-limitations)
* [Understanding Data Modeling in NoSQL](https://www.mongodb.com/nosql-explained)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

