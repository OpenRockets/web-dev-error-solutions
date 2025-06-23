# 🐞 Efficiently Storing and Retrieving Large Posts in Firebase Firestore


## Description of the Problem

A common challenge when using Firebase Firestore to store and retrieve blog posts or other content-rich data is managing the size of individual documents.  Firestore has document size limits (currently 1 MB).  Storing large amounts of text, images, or other media directly within a single Firestore document can easily exceed this limit, leading to errors and preventing data from being saved.  Simply splitting the post into multiple documents can complicate data retrieval and require complex querying and stitching operations on the client-side.


## Step-by-Step Solution: Using Storage for Media and Separate Collections for Metadata

This solution involves using Firebase Storage to handle large media files (images, videos) and storing only metadata (like title, author, short description, timestamps, and links to media files in Storage) in Firestore. This approach keeps Firestore documents small and manageable while allowing for efficient retrieval of complete posts.

### Step 1: Set up Firebase Storage

Ensure you have Firebase Storage properly configured in your project. You can find instructions in the official Firebase documentation: [Firebase Storage Documentation](https://firebase.google.com/docs/storage)

### Step 2:  Upload Media to Storage

Before saving the post to Firestore, upload your media files (images, videos etc.) to Firebase Storage.  The upload process returns a download URL.  This URL will be stored as metadata in Firestore.

```javascript
import { getStorage, ref, uploadBytesResumable, getDownloadURL } from "firebase/storage";

async function uploadMedia(file) {
  const storage = getStorage();
  const storageRef = ref(storage, `posts/${file.name}`);
  const uploadTask = uploadBytesResumable(storageRef, file);

  return new Promise((resolve, reject) => {
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
        reject(error);
      },
      () => {
        // Handle successful uploads on complete
        getDownloadURL(uploadTask.snapshot.ref).then((downloadURL) => {
          resolve(downloadURL);
        });
      }
    );
  });
}


//Example Usage:
const imageFile = document.getElementById("imageFile").files[0];
uploadMedia(imageFile)
  .then((downloadURL) => {
    console.log('File available at', downloadURL);
    //Now use downloadURL to save in Firestore
  })
  .catch((error) => {
    console.error('Upload failed:', error);
  });
```

### Step 3: Create a Firestore Collection for Post Metadata

Create a collection in Firestore, for example, named "posts".  Each document in this collection will represent a single post and contain only the metadata.

### Step 4: Store Post Metadata in Firestore

After uploading the media to Storage, save the metadata (title, author, short description,  timestamp, and the download URLs from Storage) to your "posts" collection in Firestore.

```javascript
import { getFirestore, collection, addDoc } from "firebase/firestore";

async function savePostToFirestore(postData) {
  const db = getFirestore();
  const postsCollection = collection(db, "posts");
  try {
    await addDoc(postsCollection, postData);
  } catch (error) {
    console.error("Error adding document: ", error);
  }
}

// Example usage (assuming you have postTitle, postAuthor, postDescription, and imageURL from previous steps)
const postData = {
  title: postTitle,
  author: postAuthor,
  description: postDescription,
  imageUrl: imageURL, //from uploadMedia function
  timestamp: firebase.firestore.FieldValue.serverTimestamp()
};

savePostToFirestore(postData)
  .then(() => {
    console.log("Post saved successfully!");
  })
  .catch((error) => {
    console.error("Error saving post:", error);
  });
```

### Step 5: Retrieve Post Data

To retrieve a post, fetch the metadata from Firestore and then use the download URLs to retrieve the media from Storage.

```javascript
import { getFirestore, collection, getDocs, query, where } from "firebase/firestore";
import { getStorage, ref, getDownloadURL } from "firebase/storage";


async function getPost(postId) {
  const db = getFirestore();
  const postsCollection = collection(db, "posts");
  const q = query(postsCollection, where(firebase.firestore.FieldPath.documentId(), "==", postId));
  const querySnapshot = await getDocs(q);
  if (querySnapshot.empty) {
    return null; //Post not found
  }
  const postData = querySnapshot.docs[0].data();
  const storage = getStorage();

  // Fetch images from Storage (modify for other media types)
  if(postData.imageUrl){
    const storageRef = ref(storage, postData.imageUrl.split("?alt=media")[0].substring(1)); // remove query parameters and starting / from storage path
    const url = await getDownloadURL(storageRef);
    postData.imageUrl = url;
  }

  return postData;
}

getPost("yourPostId")
  .then(post => {
    console.log(post); //The post data, including the media URLs is available here
  })
  .catch(error => {
    console.error("Error getting post:", error);
  });
```


## Explanation

This strategy significantly improves scalability and avoids exceeding Firestore's document size limits.  By separating media from metadata, you can handle much larger posts efficiently.  The client-side code retrieves the metadata and then fetches the media assets only as needed, optimizing bandwidth usage.


## External References

* [Firebase Firestore Documentation](https://firebase.google.com/docs/firestore)
* [Firebase Storage Documentation](https://firebase.google.com/docs/storage)
* [Firebase JavaScript SDK](https://firebase.google.com/docs/web/setup)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

