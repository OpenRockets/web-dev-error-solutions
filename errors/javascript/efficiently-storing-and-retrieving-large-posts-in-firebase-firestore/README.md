# 🐞 Efficiently Storing and Retrieving Large Posts in Firebase Firestore


This document addresses a common issue developers encounter when managing posts with rich text content or extensive metadata in Firebase Firestore: inefficient data storage and retrieval leading to slow loading times and exceeding Firestore's document size limits.  Firestore has a document size limit of 1MB.  Exceeding this limit will result in an error.  Furthermore, retrieving large documents can impact application performance, especially on mobile devices.

**Description of the Error:**

When attempting to store a large post (e.g., a blog post with images, embedded videos, long text content, and extensive metadata) directly as a single Firestore document, you might encounter the following:

* **`FAILED_PRECONDITION: The document size exceeds the maximum allowed size of 1 MiB.`** This error directly indicates exceeding Firestore's document size limit.
* **Slow loading times:** Even if you don't hit the size limit, fetching a large document can cause significant delays, leading to a poor user experience.
* **Inefficient queries:**  Fetching large documents can also negatively impact query performance, particularly if you need to filter or sort based on fields within the document.


**Fixing the Problem: Data Normalization and Subcollections**

The solution involves implementing data normalization by breaking down the large post into smaller, more manageable units. We'll store the core post information (title, summary, author, etc.) in one document and use a subcollection to manage the rich content (images, text blocks, etc).

**Step-by-step Code (JavaScript):**

```javascript
// 1. Setting up the Firestore instance
import { initializeApp } from "firebase/app";
import { getFirestore, collection, addDoc, doc, getDoc, setDoc, getDocs } from "firebase/firestore";

// Replace with your Firebase configuration
const firebaseConfig = {
  // ... your Firebase config ...
};

const app = initializeApp(firebaseConfig);
const db = getFirestore(app);

// 2. Defining the Post structure
const createPost = async (postDetails) => {
  // Core Post Data
  const postRef = await addDoc(collection(db, "posts"), {
    title: postDetails.title,
    author: postDetails.author,
    summary: postDetails.summary,
    timestamp: new Date(), //Adding a timestamp
  });

  //Subcollection to store detailed post content (text and image URLS)
  const contentRef = collection(db, "posts", postRef.id, "content");
  postDetails.content.forEach(async (contentItem) => {
     await addDoc(contentRef, contentItem);
  });
};

//3. Example Post Data
const newPost = {
  title: "My Awesome Post",
  author: "John Doe",
  summary: "A short summary of the post...",
  content: [
    { type: "text", text: "This is the main text of the post." },
    { type: "image", url: "https://example.com/image1.jpg" },
    { type: "text", text: "More text here..." },
  ],
};


// 4. Adding the post
createPost(newPost).then(() => console.log('Post added successfully!'))
.catch((error)=> console.log('Error adding post:', error))

// 5. Retrieving the post
const getPost = async (postId) => {
  const postDocRef = doc(db, "posts", postId);
  const postDoc = await getDoc(postDocRef);

  if(postDoc.exists()){
    let post = postDoc.data();
    const contentRef = collection(db, "posts", postId, "content");
    const contentSnapshot = await getDocs(contentRef);
    const content = contentSnapshot.docs.map(doc => doc.data());

    post = {...post, content: content};

    return post;
  } else {
    return null;
  }
};


getPost("yourPostId").then((post) => {
  if(post){
     console.log("Retrieved post:", post)
  } else {
    console.log("Post not found")
  }
}).catch((error) => console.log("Error retrieving post:", error))

```

**Explanation:**

* **Data Normalization:** The core post information is stored in the `posts` collection, and the rich content is stored in a subcollection (`content`) associated with each post. This prevents exceeding the document size limit.
* **Efficient Retrieval:**  Retrieving a post now involves fetching the main post document and then querying the subcollection for its content.  This is far more efficient than fetching a single, massive document.
* **Scalability:** This approach is scalable, allowing for the addition of more content to posts without impacting the performance of retrieving other posts.

**External References:**

* [Firebase Firestore Documentation](https://firebase.google.com/docs/firestore)
* [Firestore Data Modeling](https://firebase.google.com/docs/firestore/design-structure)
* [Dealing with large documents in Firestore](https://stackoverflow.com/questions/49177768/how-to-deal-with-large-documents-in-firestore)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

