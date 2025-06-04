# 🐞 Next.js API Routes: Handling CORS Errors


This document addresses a common problem developers encounter when working with Next.js API routes: **CORS (Cross-Origin Resource Sharing) errors**.  These errors occur when a frontend application (e.g., a Next.js application running on a different port or domain) attempts to make requests to an API route hosted on the same Next.js application but in a different context. Browsers, for security reasons, will block these requests unless the API route is correctly configured to handle CORS.


**Description of the Error:**

You'll typically see an error in your browser's developer console similar to this:

```
Access to fetch at 'http://localhost:3000/api/data' from origin 'http://localhost:3001' has been blocked by CORS policy: No 'Access-Control-Allow-Origin' header is present on the requested resource.
```

This indicates that your frontend application (originating from `http://localhost:3001` in this example) is trying to access your API route (`http://localhost:3000/api/data`), but the server doesn't allow it due to a missing or incorrect `Access-Control-Allow-Origin` header.

**Step-by-step Code Fix:**

The solution involves adding the appropriate CORS headers to your API route's response.  Here's how you can do it, assuming your API route is written in Node.js:

**1.  Before:**

```javascript
// pages/api/data.js
export default function handler(req, res) {
  res.status(200).json({ data: 'Hello from API!' });
}
```

**2. After (Adding CORS headers):**

```javascript
// pages/api/data.js
export default function handler(req, res) {
  res.setHeader('Access-Control-Allow-Origin', '*'); // or a specific origin
  res.setHeader('Access-Control-Allow-Methods', 'GET, POST, PUT, DELETE'); // Allowed methods
  res.setHeader('Access-Control-Allow-Headers', 'Content-Type, Authorization'); // Allowed headers

  if (req.method === 'GET') {
    res.status(200).json({ data: 'Hello from API!' });
  } else {
    res.status(405).end(); // Method Not Allowed
  }
}
```

This modified code adds the necessary CORS headers:

* `Access-Control-Allow-Origin`:  Specifies which origins are allowed to access the API. `*` allows all origins (use cautiously in production; specify specific origins for enhanced security).
* `Access-Control-Allow-Methods`: Lists the HTTP methods allowed (GET, POST, PUT, DELETE, etc.).
* `Access-Control-Allow-Headers`: Specifies allowed request headers.  `Content-Type` and `Authorization` are common examples.


**Explanation:**

The `res.setHeader` function adds headers to the HTTP response.  These headers instruct the browser to allow the cross-origin request.  The `Access-Control-Allow-Origin` header is crucial; it tells the browser that the request from the specified origin is permitted.  The other headers further refine the allowed actions and headers.  The `if` statement handles different HTTP methods, returning a 405 error for unsupported methods. Using `*` is generally discouraged in production as it opens your API to everyone.  In a production environment, replace `'*'` with the specific origin of your frontend application (e.g., `'https://yourdomain.com'`).

**External References:**

* [Next.js API Routes](https://nextjs.org/docs/api-routes/introduction)
* [MDN Web Docs: CORS](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS)


**Important Security Note:**  Using `Access-Control-Allow-Origin: '*'` is convenient for development but poses a significant security risk in production.  In a production setting, always restrict access to specific origins to prevent unauthorized access to your API.


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

