# 🐞 Efficiently Storing and Retrieving Large Post Data in Firebase Firestore


## Description of the Problem

A common challenge when using Firebase Firestore to manage posts (e.g., blog posts, social media updates) is efficiently handling large amounts of data within each post document.  Storing extensive text content, multiple images, or rich media directly within a single Firestore document can lead to several issues:

* **Document Size Limits:** Firestore imposes document size limits (currently 1 MB). Exceeding this limit results in errors when attempting to create or update the document.
* **Read Performance:** Retrieving large documents impacts read performance, potentially slowing down your application and increasing costs.
* **Data Management:**  Managing large, complex documents can be cumbersome and lead to inefficient data updates.


## Step-by-Step Code Solution: Utilizing Subcollections

The most effective approach is to break down large post documents into smaller, manageable units using Firestore subcollections.  Instead of storing everything in a single `posts` document, we'll create a main `posts` document with essential metadata and then use subcollections to hold the lengthy content, images, and other rich media.


**1. Data Structure:**

Our new data structure will look like this:

* **Collection: `posts`**
    * **Document: `postId`**  (e.g., `post123`)
        * `title`: string
        * `authorId`: string
        * `createdAt`: timestamp
        * `summary`: string (short summary)
        * ...other relevant metadata...

    * **Subcollection: `content`**
        * **Document: `content`**
            * `body`: string (full post body)

    * **Subcollection: `images`**
        * **Document: `image1`**
            * `url`: string (image URL)
        * **Document: `image2`**
            * `url`: string (image URL)
        * ...more image documents...


**2. Code Example (JavaScript):**

This example uses the Firebase JavaScript SDK.  Remember to install it: `npm install firebase`


```javascript
import { initializeApp } from "firebase/app";
import { getFirestore, collection, addDoc, doc, setDoc, getDoc } from "firebase/firestore";
import { getStorage, ref, uploadBytesResumable, getDownloadURL } from "firebase/storage";

// Your Firebase configuration
const firebaseConfig = {
  // ... your config ...
};

const app = initializeApp(firebaseConfig);
const db = getFirestore(app);
const storage = getStorage(app);


async function createPost(postDetails) {
  const { title, authorId, summary, body, images } = postDetails;

  const postRef = await addDoc(collection(db, "posts"), {
    title: title,
    authorId: authorId,
    createdAt: new Date(),
    summary: summary
  });

  const postId = postRef.id;


  //Store post body in subcollection
  await setDoc(doc(db, "posts", postId, "content", "content"), {body});

  //Store images in subcollection  (assuming images are files)
  for (let i = 0; i < images.length; i++) {
    const image = images[i];
    const storageRef = ref(storage, `posts/${postId}/images/image${i + 1}`);
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
        console.error(error);
      },
      () => {
        // Handle successful uploads on complete
        getDownloadURL(uploadTask.snapshot.ref).then((downloadURL) => {
          setDoc(doc(db, "posts", postId, "images", `image${i+1}`), {url: downloadURL});
        });
      }
    );
  }

}


//Example usage:
const newPost = {
  title: "My Awesome Post",
  authorId: "user123",
  summary: "A short summary...",
  body: "This is the full body of my awesome post.  It's quite long!",
  images: [/* Array of image files */]
};

createPost(newPost);
```

**3. Retrieving Data:**

Retrieving data involves fetching the main post document and then querying its subcollections:

```javascript
async function getPost(postId) {
  const postDocRef = doc(db, "posts", postId);
  const postDocSnap = await getDoc(postDocRef);
  let post = postDocSnap.data();

  if (post){
    const contentRef = collection(db, "posts", postId, "content");
    const contentSnap = await getDocs(contentRef);
    post.body = (contentSnap.docs[0] || {}).data()?.body || '';

    const imagesRef = collection(db, "posts", postId, "images");
    const imagesSnap = await getDocs(imagesRef);
    post.images = imagesSnap.docs.map(doc => doc.data().url);
  }
  return post;

}

```


## Explanation

This approach leverages Firestore's subcollections to segregate data, ensuring that no single document exceeds size limits.  It also improves read performance by retrieving only the necessary data at a given time.  For example, displaying a post summary on a feed only requires fetching the main `posts` document; the full content is loaded only when the user clicks to view the entire post.


## External References

* [Firebase Firestore Documentation](https://firebase.google.com/docs/firestore)
* [Firebase Storage Documentation](https://firebase.google.com/docs/storage)
* [JavaScript SDK](https://firebase.google.com/docs/web/setup)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

