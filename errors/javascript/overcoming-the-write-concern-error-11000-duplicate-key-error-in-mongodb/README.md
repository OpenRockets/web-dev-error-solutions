# 🐞 Overcoming the "Write Concern Error: 11000 duplicate key error" in MongoDB


This document addresses a common MongoDB error encountered during CRUD operations, specifically when inserting documents with duplicate unique keys.  This error, indicated by code `11000`, stems from a violation of a unique index constraint.


**Description of the Error:**

The `11000 duplicate key error` occurs when you attempt to insert a document into a collection that already contains a document with the same value for a field that has a unique index defined. MongoDB prevents duplicate entries to maintain data integrity.  This error typically manifests during application execution, halting the insert operation and potentially leading to application failures if not handled properly.


**Example Scenario:**

Let's say you have a collection named `users` with a unique index on the `email` field.  Attempting to insert a new user document with an email address that already exists in the collection will trigger this error.


**Fixing the Error Step-by-Step (Code):**

This example uses Node.js with the MongoDB driver, but the concept applies to other drivers as well. The key is to handle the error gracefully, preventing application crashes and potentially providing informative feedback to the user.

```javascript
const { MongoClient } = require('mongodb');

const uri = "mongodb://localhost:27017"; // Replace with your connection string
const client = new MongoClient(uri);

async function insertUser(user) {
  try {
    await client.connect();
    const db = client.db('mydatabase'); // Replace with your database name
    const collection = db.collection('users');

    const result = await collection.insertOne(user);
    console.log(`Inserted document with _id: ${result.insertedId}`);
  } catch (err) {
    if (err.code === 11000) {
      console.error("Duplicate key error:", err.message);
      // Handle the duplicate key error, e.g., inform the user, try an update instead, or retry with different data.
      console.log("Email address already exists. Please choose a different email."); 
      return null; // Or throw a custom error for better error handling in higher layers
    } else {
      console.error("Error inserting document:", err);
      throw err; // Re-throw other errors
    }
  } finally {
    await client.close();
  }
}


// Example usage:
const newUser = { name: "John Doe", email: "johndoe@example.com" };
insertUser(newUser)
  .then(() => console.log("Operation complete"))
  .catch(err => console.error("Overall Operation Failure: ", err));

//Example of duplicate insert, leading to error:
const duplicateUser = { name: "Jane Doe", email: "johndoe@example.com" }; // Duplicate email
insertUser(duplicateUser)
  .then(() => console.log("Operation complete"))
  .catch(err => console.error("Overall Operation Failure: ", err));
```

**Explanation:**

1. **Connection:** The code connects to the MongoDB server.  Replace placeholders with your connection string and database name.
2. **`insertOne()`:**  This method attempts to insert a single document.
3. **Error Handling:** The `try...catch` block catches errors.  Specifically, it checks if the error code is `11000`.
4. **Conditional Handling:** If the error code is `11000`, it logs an error message and takes appropriate action – in this case, informing the user of the duplicate email. You could implement more sophisticated logic here, such as updating an existing user instead of inserting a new one, using `updateOne()`.
5. **Re-throwing Errors:** Other errors are re-thrown to be handled at a higher level in the application.
6. **`finally` block:** The connection is closed in the `finally` block, ensuring resource cleanup even if errors occur.


**External References:**

* [MongoDB Documentation on Unique Indexes](https://www.mongodb.com/docs/manual/indexes/#unique-indexes)
* [MongoDB Driver for Node.js](https://www.mongodb.com/docs/drivers/node/)
* [Node.js Error Handling](https://nodejs.org/api/errors.html)


**Copyright (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.**

