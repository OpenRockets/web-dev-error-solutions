# 🐞 Handling `Error: Unexpected token < in JSON at position 0` in Next.js API Routes


This document addresses a common error encountered when developing API routes in Next.js: `Error: Unexpected token < in JSON at position 0`.  This error typically arises when your API route returns HTML or a non-JSON response, while the client expects JSON. This often happens due to incorrect error handling, unintended rendering, or mismatched client-side expectations.

## Description of the Error

The error message `Error: Unexpected token < in JSON at position 0` indicates that the JavaScript `JSON.parse()` function, used by the client to process the API response, encountered an unexpected character (`<` in this case) at the beginning of the response.  This character signifies the start of an HTML tag, implying that the server is returning an HTML page instead of a JSON object.  This mismatch between expected (JSON) and actual (HTML) response formats causes this parsing error.

## Steps to Fix the Error

Let's assume our API route, `/api/data`, is malfunctioning and producing this error.  Here's a step-by-step guide to resolving it:

**1. Identify the Source of the Problem:**

First, carefully examine the `pages/api/data.js` file (or wherever your API route is defined).  Look for any instances where the response might inadvertently be returning HTML instead of JSON. Common causes include:

* **Unhandled errors:** If an error occurs within your API route, make sure you're handling it gracefully and returning a JSON response indicating the error.
* **Incorrect `res.json()` usage:**  Ensure you are consistently using `res.json()` to send JSON data.  Do not accidentally use `res.send()` with HTML content.
* **Conditional rendering in API route:** API routes shouldn't perform client-side rendering. Avoid rendering components or HTML within your API route logic.


**2. Corrected API Route (`pages/api/data.js`):**

```javascript
// pages/api/data.js
export default async function handler(req, res) {
  try {
    // Your API logic here...  Example: Fetching data from a database
    const data = await fetchData(); // Replace fetchData with your data fetching logic

    // Return JSON response
    res.status(200).json({ data });
  } catch (error) {
    // Handle errors gracefully and return a JSON error response
    console.error("API Error:", error);
    res.status(500).json({ error: "Internal Server Error" });
  }
}


async function fetchData() {
  // Replace this with your actual data fetching logic.
  // This example simulates fetching data.
  await new Promise(resolve => setTimeout(resolve, 1000));
  return [{id:1, name: "Example 1"}, {id:2, name: "Example 2"}];
}
```

**3. Client-Side Consumption:**

Ensure your client-side code (e.g., in a `getStaticProps` function or a `useEffect` hook) correctly handles potential errors during the fetching process:

```javascript
// pages/index.js (Example client-side code)
import { useEffect, useState } from 'react';

export default function Home() {
  const [data, setData] = useState(null);
  const [error, setError] = useState(null);

  useEffect(() => {
    const fetchData = async () => {
      try {
        const res = await fetch('/api/data');
        if (!res.ok) {
          throw new Error(`HTTP error! status: ${res.status}`);
        }
        const jsonData = await res.json();
        setData(jsonData.data);
      } catch (error) {
        setError(error);
        console.error("Error fetching data:", error);
      }
    };

    fetchData();
  }, []);

  if (error) {
    return <p>Error: {error.message}</p>;
  }

  if (!data) {
    return <p>Loading...</p>;
  }

  return (
    <ul>
      {data.map(item => (
        <li key={item.id}>{item.name}</li>
      ))}
    </ul>
  );
}
```


## Explanation

The key to fixing this error is robust error handling in your API route. By always returning a JSON response, even in case of errors, you ensure consistency and prevent the client from receiving unexpected data formats.  The client-side code should also handle potential network errors and non-2xx status codes gracefully to prevent crashing or displaying malformed data.


## External References

* [Next.js API Routes Documentation](https://nextjs.org/docs/api-routes/introduction)
* [Fetch API Documentation](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API)
* [Handling errors in JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Control_flow_and_error_handling)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

