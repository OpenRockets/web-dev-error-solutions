# 🐞 Handling 404 Errors in Next.js API Routes with MongoDB and Express.js


This document addresses a common problem developers encounter when building applications using Next.js API routes, Express.js, and MongoDB: handling 404 (Not Found) errors effectively.  This often arises when fetching data from MongoDB based on requests made through Next.js API routes, and the requested resource doesn't exist.

**Description of the Error:**

When a request is made to your Next.js API route, which interacts with a MongoDB database via Express.js, a 404 error will occur if the database query returns no results.  By default, this might simply return a blank page or a generic error message, hindering a smooth user experience.  We need a robust way to handle these cases, providing informative feedback to the client-side.

**Code to Fix Step-by-Step:**

This example demonstrates using `async/await` for clarity, and assumes you're using `mongoose` for MongoDB interaction.  Replace placeholders like `<YOUR_MONGODB_URI>`, `<YOUR_COLLECTION_NAME>`, and `<YOUR_ID>` with your actual values.

**1.  Next.js API Route (`pages/api/data/[id].js`):**

```javascript
import { MongoClient } from 'mongodb';

const uri = process.env.MONGODB_URI || "<YOUR_MONGODB_URI>"; // Replace with your MongoDB connection string
const client = new MongoClient(uri);

export default async function handler(req, res) {
  const { id } = req.query;

  try {
    await client.connect();
    const db = client.db("yourDatabaseName"); //Replace with your database name
    const collection = db.collection("<YOUR_COLLECTION_NAME>"); // Replace with your collection name

    const data = await collection.findOne({ _id: new ObjectId(id) });

    if (!data) {
      return res.status(404).json({ message: "Data not found" }); // Handle 404 gracefully
    }

    res.status(200).json(data);
  } catch (error) {
    console.error("Error fetching data:", error);
    res.status(500).json({ message: "Internal Server Error" });
  } finally {
    await client.close();
  }
}

```

**2.  Next.js Frontend (`pages/index.js` Example):**

```javascript
import { useEffect, useState } from 'react';

export default function Home() {
  const [data, setData] = useState(null);
  const [error, setError] = useState(null);
  const [loading, setLoading] = useState(true);

  useEffect(() => {
    const fetchData = async () => {
      try {
        const response = await fetch('/api/data/12345'); //Replace with your actual ID
        if (!response.ok) {
          if (response.status === 404) {
            setError("Data not found");
          } else {
            throw new Error(`HTTP error! status: ${response.status}`);
          }
        }
        const result = await response.json();
        setData(result);
      } catch (err) {
        setError(err.message);
      } finally {
        setLoading(false);
      }
    };

    fetchData();
  }, []);

  if (loading) return <p>Loading...</p>;
  if (error) return <p>Error: {error}</p>;
  if (!data) return <p>No data available</p>; // Handle potential data absence

  return (
    <div>
      <h1>Data</h1>
      <pre>{JSON.stringify(data, null, 2)}</pre>
    </div>
  );
}

```

**Explanation:**

The API route now explicitly checks if the `findOne` operation returns null. If it does, a 404 JSON response with a descriptive message is sent.  The frontend code then handles this 404 response, displaying a user-friendly error message instead of a generic error.  The `try...catch...finally` block ensures proper error handling and database connection closure.  Remember to install `mongodb` package using `npm install mongodb`.


**External References:**

* [Next.js API Routes Documentation](https://nextjs.org/docs/api-routes/introduction)
* [MongoDB Node.js Driver](https://www.mongodb.com/docs/drivers/node/)
* [Express.js Documentation](https://expressjs.com/)
* [Mongoose documentation](https://mongoosejs.com/docs/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

