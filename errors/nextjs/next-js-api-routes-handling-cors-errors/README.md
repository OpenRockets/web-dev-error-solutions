# 🐞 Next.js API Routes: Handling CORS Errors


## Description of the Error

A common issue when working with Next.js API routes is encountering CORS (Cross-Origin Resource Sharing) errors.  This happens when a client (e.g., a frontend application running on a different domain or port) tries to make a request to your API route, and the server doesn't allow it due to security restrictions.  The browser will typically block the request, resulting in a `CORS` error in your browser's developer console.  This usually manifests as an error message similar to: `Access to XMLHttpRequest at '...' from origin '...' has been blocked by CORS policy: No 'Access-Control-Allow-Origin' header is present on the requested resource.`

## Step-by-Step Code Fix

Let's assume you have a Next.js API route located at `/api/hello` that simply returns "Hello from API Route!".  The problem is that a frontend application running on a different origin (e.g., `http://localhost:3000`) is trying to access it.

**1. Incorrect (Error-Causing) API Route:**

```javascript
// pages/api/hello.js
export default function handler(req, res) {
  res.status(200).json({ text: 'Hello from API Route!' });
}
```

This code doesn't handle CORS, so it will fail if accessed from a different origin.


**2. Corrected API Route with CORS Headers:**

```javascript
// pages/api/hello.js
export default function handler(req, res) {
  res.setHeader('Access-Control-Allow-Origin', 'http://localhost:3000'); // Adjust this to your frontend's origin
  res.setHeader('Access-Control-Allow-Methods', 'GET, POST, OPTIONS'); // Add other methods as needed
  res.setHeader('Access-Control-Allow-Headers', 'Content-Type, Authorization'); // Add other headers as needed

  if (req.method === 'OPTIONS') {
    res.status(200).end();
    return;
  }

  res.status(200).json({ text: 'Hello from API Route!' });
}
```

This improved version adds the necessary CORS headers:

* `Access-Control-Allow-Origin`: Specifies the origin(s) that are allowed to access the API.  **Replace `http://localhost:3000` with the actual origin of your frontend application.**  You can use `*` to allow all origins (generally not recommended for production).
* `Access-Control-Allow-Methods`: Specifies the allowed HTTP methods (GET, POST, PUT, DELETE, etc.).
* `Access-Control-Allow-Headers`: Specifies the allowed headers in the request (e.g., `Content-Type` for JSON requests, `Authorization` for authentication).

The `OPTIONS` method handling is crucial for preflight requests (especially for POST requests with custom headers).  It sends a response indicating which methods and headers are allowed.

## Explanation

CORS is a security mechanism implemented by browsers to prevent malicious websites from making unauthorized requests to other websites.  By adding the appropriate `Access-Control-Allow-*` headers to your API route's response, you explicitly tell the browser which origins are permitted to access your API.  This allows your frontend application to make requests to your API without being blocked by the CORS policy.  Using a wildcard (`*`) for `Access-Control-Allow-Origin` is generally discouraged in production environments as it opens your API to potential security vulnerabilities.  It's best to specify the exact origin(s) of your frontend applications.


## External References

* [MDN Web Docs: CORS](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS)
* [Next.js API Routes](https://nextjs.org/docs/api-routes/introduction)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

