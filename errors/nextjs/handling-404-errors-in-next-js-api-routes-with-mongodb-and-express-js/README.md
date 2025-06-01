# 🐞 Handling 404 Errors in Next.js API Routes with MongoDB and Express.js


This document addresses a common problem developers encounter when building applications with the MERN stack (MongoDB, Express.js, React.js, Next.js): receiving 404 Not Found errors when fetching data from a Next.js API route that interacts with a MongoDB database via Express.js. This typically happens when the API route doesn't correctly handle requests or when data isn't found in the database.


**Description of the Error:**

The error manifests as a `404 Not Found` response from your Next.js API route.  This can occur for various reasons, including incorrect routing in Next.js, incorrect data fetching logic in Express.js, or missing data in your MongoDB database.  The client-side (React.js) application will then display an error indicating it could not fetch the expected data.  The browser's developer console may show a `404` status code.


**Step-by-Step Code Fix:**

Let's assume we have a Next.js API route (`pages/api/products/[id].js`) that fetches a product from a MongoDB database based on its ID.

**1.  Next.js API Route (`pages/api/products/[id].js`):**

```javascript
import { MongoClient } from 'mongodb';

const client = new MongoClient(process.env.MONGODB_URI); // Remember to set your MONGODB_URI as environment variable
const db = client.db('your_database_name'); // Replace with your database name
const collection = db.collection('products');

export default async function handler(req, res) {
  const { id } = req.query;

  try {
    await client.connect(); // Ensure connection is established

    const product = await collection.findOne({ _id: new ObjectId(id) }); // Use ObjectId for proper querying

    if (!product) {
      return res.status(404).json({ message: 'Product not found' }); //Handle the case where product is not found
    }

    res.status(200).json(product);
  } catch (error) {
    console.error('Error fetching product:', error);
    res.status(500).json({ message: 'Internal Server Error' }); //Handle server errors
  } finally {
    await client.close(); //Always close the connection
  }
}

//Import necessary ObjectId if using _id
import { ObjectId } from 'mongodb';
```


**2. React Component (example using `useSWR`):**

```javascript
import useSWR from 'swr';

const fetcher = (url) => fetch(url).then((res) => res.json());

const ProductDetails = ({ id }) => {
  const { data, error } = useSWR(`/api/products/${id}`, fetcher);

  if (error) {
    return <div>Error loading product: {error.message}</div>;  //Handle errors gracefully
  }
  if (!data) {
    return <div>Loading...</div>; //Handle loading state
  }

  return (
    <div>
      <h1>{data.name}</h1>
      <p>{data.description}</p>
      {/* ... rest of your product details */}
    </div>
  );
};

export default ProductDetails;
```


**Explanation:**

* **Error Handling:** The improved API route now explicitly checks if a product is found (`if (!product)`).  If not, it returns a `404` status code with a clear message.  It also includes a `try...catch` block to handle potential errors during database interaction and returns a `500` error if something goes wrong on the server-side.  Finally, it closes the database connection in a `finally` block.
* **ObjectId:**  Using `ObjectId` from the `mongodb` library is crucial when querying MongoDB by its `_id` field, as it's a special BSON type and not a simple string.
* **Client-Side Handling:** The React component uses `useSWR` (you can use `fetch` directly as well) to fetch data and handles both loading and error states gracefully, preventing crashes and improving user experience.


**External References:**

* [Next.js API Routes Documentation](https://nextjs.org/docs/api-routes/introduction)
* [MongoDB Driver for Node.js](https://www.mongodb.com/docs/drivers/node/)
* [useSWR](https://swr.vercel.app/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

