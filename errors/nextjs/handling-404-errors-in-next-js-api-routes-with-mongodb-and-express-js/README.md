# 🐞 Handling 404 Errors in Next.js API Routes with MongoDB and Express.js


This document addresses a common issue developers face when building applications using Next.js API routes that interact with a MongoDB database via Express.js: receiving 404 (Not Found) errors when attempting to fetch data that doesn't exist.  This often happens when a request is made to an API route that expects a specific document ID, but that ID is not present in the MongoDB collection.

**Description of the Error:**

When making a request to a Next.js API route that queries a MongoDB database, a 404 error will occur if the queried document is not found. This might manifest in your client-side React application as a blank page, an error message, or unexpected behavior.  The server-side error log will typically show a 404 response.

**Code and Fixing Steps:**

This example uses `mongodb` driver for node.js and assumes you have a basic Next.js API route and a MongoDB connection setup.  Let's say you have a collection named `products` and you're trying to fetch a product by its ID.

**Problem Code (Illustrative):**

```javascript
// pages/api/products/[id].js
import { MongoClient } from 'mongodb';

const uri = process.env.MONGODB_URI; // Ensure this is set in your .env file
const client = new MongoClient(uri);

export default async function handler(req, res) {
  const { id } = req.query;
  try {
    await client.connect();
    const db = client.db('mydatabase');
    const product = await db.collection('products').findOne({ _id: id }); //Potential 404
    if (!product) {
        return res.status(404).json({ message: 'Product not found' });
    }
    res.status(200).json(product);
  } catch (error) {
    console.error(error);
    res.status(500).json({ error: 'Failed to fetch product' });
  } finally {
    await client.close();
  }
}
```


**Fixed Code:**

The main issue is that the original code didn't explicitly handle the scenario where `findOne` returns null. The fix is to include explicit error handling for when no document is found:


```javascript
// pages/api/products/[id].js
import { MongoClient, ObjectId } from 'mongodb';

const uri = process.env.MONGODB_URI; // Ensure this is set in your .env file
const client = new MongoClient(uri);

export default async function handler(req, res) {
  const { id } = req.query;
  try {
    await client.connect();
    const db = client.db('mydatabase');
    // Convert id to ObjectId to ensure proper matching.  Crucial for MongoDB
    const product = await db.collection('products').findOne({ _id: new ObjectId(id) });
    if (!product) {
      return res.status(404).json({ message: 'Product not found' });
    }
    res.status(200).json(product);
  } catch (error) {
    console.error(error);
    if (error.message.includes("ObjectId")) { //check for invalid ObjectId
        return res.status(400).json({ message: 'Invalid product ID' });
    }
    res.status(500).json({ error: 'Failed to fetch product' });
  } finally {
    await client.close();
  }
}
```

**Explanation:**

The improved code explicitly checks if `product` is null after the `findOne` operation. If it is, a 404 response with a user-friendly message is returned.  It also adds crucial conversion of the `id` string to a `mongodb.ObjectId` before the query.  This is fundamental for correctly querying documents by their _id field.  Further, error handling is improved to catch invalid `ObjectId` values that could cause other errors.



**External References:**

* [Next.js API Routes](https://nextjs.org/docs/api-routes/introduction)
* [MongoDB Driver for Node.js](https://www.mongodb.com/docs/drivers/node/current/)
* [Handling Errors in Express.js](https://expressjs.com/en/guide/error-handling.html)
* [MongoDB ObjectID](https://www.mongodb.com/docs/manual/reference/method/ObjectId/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

