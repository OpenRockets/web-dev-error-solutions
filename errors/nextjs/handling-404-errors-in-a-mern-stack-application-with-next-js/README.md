# 🐞 Handling 404 Errors in a MERN Stack Application with Next.js


This document addresses a common problem encountered when building applications using MongoDB, Express.js, React.js, and Next.js: handling 404 (Not Found) errors gracefully.  Specifically, we'll focus on routing issues where Next.js routes don't correctly map to your Express.js API endpoints, resulting in 404 errors on the client-side.

## Description of the Error

When a user attempts to access a route that doesn't exist in your Next.js application or your Express.js API, the client will receive a 404 error. This can manifest as a blank page, a generic error message, or a browser error message.  The problem often stems from inconsistencies between your frontend routing (Next.js) and your backend API routing (Express.js).  For example, a frontend route might expect data from `/api/data`, but the Express.js server might not have a route defined for that path.

## Fixing the Problem Step-by-Step

Let's assume we have a Next.js application fetching data from an Express.js API. The goal is to display a custom 404 page when the API returns a 404 status.

**Step 1: Ensure Correct API Route Definition (Express.js)**

First, verify that your Express.js API has the correct route defined.  Here's an example using a route that fetches data:

```javascript
// server.js (or equivalent)
const express = require('express');
const app = express();

app.get('/api/data', (req, res) => {
  // Fetch data from MongoDB or other source
  const data = { message: 'Data fetched successfully!' };
  res.json(data);
});

// ... other routes ...

app.use((req, res) => {
  res.status(404).json({ message: 'API Route Not Found' });
})

const port = process.env.PORT || 3001; // Use a port different from Next.js
app.listen(port, () => console.log(`Server listening on port ${port}`));
```


**Step 2: Implement Data Fetching in Next.js (React)**

In your Next.js page, use `useEffect` or `getStaticProps`/`getServerSideProps` to fetch data from your API.  Handle potential errors appropriately, including 404 errors.


```javascript
import { useState, useEffect } from 'react';

function MyPage() {
  const [data, setData] = useState(null);
  const [error, setError] = useState(null);
  const [loading, setLoading] = useState(true);

  useEffect(() => {
    const fetchData = async () => {
      try {
        const res = await fetch('/api/data');
        if (!res.ok) {
          if (res.status === 404) {
            throw new Error('Data not found'); //Specific error for 404
          }
          throw new Error(`HTTP error! status: ${res.status}`);
        }
        const data = await res.json();
        setData(data);
      } catch (err) {
        setError(err.message);
      } finally {
        setLoading(false);
      }
    };

    fetchData();
  }, []);

  if (loading) return <p>Loading...</p>;
  if (error) return <p>Error: {error}</p>; // Display custom error message
  if (!data) return <p>No data available</p>; // Handle case where data is null

  return (
    <div>
      <h1>My Data</h1>
      <p>{data.message}</p>
    </div>
  );
}

export default MyPage;
```


**Step 3: Implement a Custom 404 Page (Next.js)**

Next.js provides a built-in way to handle 404 pages. Create a file named `404.js` (or `pages/404.js`) in your `pages` directory:

```javascript
function Custom404() {
  return (
    <div>
      <h1>404 - Page Not Found</h1>
      <p>The page you are looking for does not exist.</p>
    </div>
  );
}

export default Custom404;
```

**Step 4: Configure Next.js API routes (optional but recommended):**

If you are using API routes within `pages/api`, be sure to define your routes consistently.  In this example, `pages/api/data.js` would be the corresponding file to `/api/data`.


## Explanation

This solution tackles the problem by:

1. **Ensuring API route consistency:** The Express.js server correctly handles the `/api/data` route. A general 404 handler catches any requests that don't match defined routes.

2. **Handling errors during data fetching:** The Next.js component uses `try...catch` to handle potential errors from the API call, including explicitly checking for 404 status codes.  It displays custom error messages instead of generic errors.

3. **Custom 404 page:** Next.js's built-in 404 page mechanism provides a user-friendly experience when a route isn't found.


## External References

* [Next.js API Routes](https://nextjs.org/docs/api-routes/introduction)
* [Next.js Error Handling](https://nextjs.org/docs/app/building-your-application/routing/error-handling)
* [Express.js Routing](https://expressjs.com/en/guide/routing.html)
* [Fetch API](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

