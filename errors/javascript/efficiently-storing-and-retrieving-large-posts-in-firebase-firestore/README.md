# 🐞 Efficiently Storing and Retrieving Large Posts in Firebase Firestore


## Description of the Problem

A common challenge when using Firebase Firestore to store blog posts or other content-rich data is managing the size of documents. Firestore has document size limits (currently 1 MB).  Large posts containing extensive text, images, or videos often exceed this limit.  Simply trying to store everything in a single document leads to errors.  This problem necessitates a strategy for efficiently storing and retrieving data while maintaining performance.


## Fixing the Problem: Step-by-Step Code

This solution involves splitting the post data into smaller, manageable documents. We'll use a main document to store metadata and references to other documents holding the larger content.

**1. Data Structure:**

We'll use three collections:

* `posts`: Stores metadata for each post (title, author, timestamp, etc.).
* `postContent`: Stores the main text content of each post, broken down into chunks if needed.
* `postImages`:  Stores references to images (e.g., storage URLs).

**2. Code (using JavaScript):**

```javascript
// Import necessary Firebase modules
import { db, storage } from './firebaseConfig'; // Replace with your config
import { collection, doc, getDoc, setDoc, addDoc, getDocs } from "firebase/firestore";
import { ref, uploadBytesResumable, getDownloadURL } from "firebase/storage";


// Function to create a new post
async function createPost(postData) {
  try {
    // 1. Store post metadata
    const postRef = await addDoc(collection(db, "posts"), {
      title: postData.title,
      author: postData.author,
      timestamp: new Date(),
      contentReference: [], //initially empty array to add references to chunks of content
      imageReferences: [] //initially empty array to add image references
    });

    //2.  Store the content (breaking it down if needed):
    const contentChunks = chunkString(postData.content, 1000); // Adjust chunk size as needed.

    const contentReferences = [];
    for (const chunk of contentChunks) {
        const contentRef = await addDoc(collection(db, "postContent"), {
            postId: postRef.id,
            content: chunk
        });
        contentReferences.push({id: contentRef.id});
    }
      await updatePostContentRef(postRef.id, contentReferences); // Update the post document with the references


    // 3. Upload and store image references:
    const imageReferences = [];
    for (const image of postData.images) {
        const storageRef = ref(storage, `postImages/${postRef.id}/${image.name}`);
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
                    imageReferences.push(downloadURL);
                });
            }
        );
    }

    await updatePostImageRef(postRef.id, imageReferences);


    console.log("Post created successfully!", postRef.id);
    return postRef.id;
  } catch (error) {
    console.error("Error creating post:", error);
    throw error;
  }
}


//Helper Functions
function chunkString(str, len) {
  const numChunks = Math.ceil(str.length / len);
  const chunks = new Array(numChunks);

  for (let i = 0, o = 0; i < numChunks; ++i, o += len) {
    chunks[i] = str.substr(o, len);
  }

  return chunks;
}


async function updatePostContentRef(postId, contentReferences){
    const postRef = doc(db, "posts", postId);
    await updateDoc(postRef, {contentReference: contentReferences});
}

async function updatePostImageRef(postId, imageReferences){
    const postRef = doc(db, "posts", postId);
    await updateDoc(postRef, {imageReferences: imageReferences});
}


// Example usage
const newPostData = {
  title: "My Awesome Post",
  author: "John Doe",
  content: "This is a very long post content that exceeds the Firestore document size limit.  This is a test to see how the chunking works.",
  images: [/* array of image files */]
};


createPost(newPostData);
```


**3. Retrieving a Post:**

```javascript
async function getPost(postId) {
  try {
    const postDocRef = doc(db, "posts", postId);
    const postDoc = await getDoc(postDocRef);

    if (postDoc.exists()) {
        const postData = postDoc.data();
        const content = await getContent(postData.contentReference);
        const images = postData.imageReferences;

        return { ...postData, content, images };
    } else {
      console.log("Post not found!");
      return null;
    }
  } catch (error) {
    console.error("Error getting post:", error);
    throw error;
  }
}

async function getContent(contentReferences){
    let content = '';
    const promises = contentReferences.map(async (reference) => {
        const docRef = doc(db, 'postContent', reference.id);
        const docSnap = await getDoc(docRef);
        if(docSnap.exists()){
            content += docSnap.data().content;
        }
    });

    await Promise.all(promises);
    return content;
}

getPost("yourPostId").then(post => console.log(post));

```


## Explanation

This approach avoids exceeding Firestore's document size limits by:

* **Separating Data:**  Metadata, content, and images are stored in separate collections.
* **Chunking Content:** Long text content is divided into smaller chunks using the `chunkString` function.  You can adjust the chunk size (currently 1000 characters) based on your needs.
* **References:** The main `posts` document contains references to the content and image data, allowing efficient retrieval without exceeding size limits.
* **Asynchronous Operations:**  The code uses asynchronous functions (`async/await`) to handle the potentially time-consuming tasks of uploading images and retrieving data from multiple documents concurrently, improving performance.


## External References

* [Firebase Firestore Documentation](https://firebase.google.com/docs/firestore)
* [Firebase Storage Documentation](https://firebase.google.com/docs/storage)
* [JavaScript `async/await`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/async_function)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

