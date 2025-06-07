# 🐞 Next.js API Routes: Handling CORS Errors


**Description of the Error:**

When building APIs with Next.js API routes, a common error encountered is a `CORS` (Cross-Origin Resource Sharing) error. This occurs when a client (e.g., a browser making a fetch request from a different domain than your API) attempts to access your API route, and the server doesn't have the correct headers configured to allow the request.  The browser's security mechanisms prevent this to avoid unauthorized access. The error message typically varies depending on the browser but might look similar to: `Access to XMLHttpRequest at '...' from origin '...' has been blocked by CORS policy`.

**Step-by-Step Code Fix:**

Let's say we have a simple API route at `/api/hello` that returns "Hello, world!". Without proper CORS headers, a client from a different origin would receive a CORS error.

**1. Incorrect (Error-Prone) API Route:**

```javascript
// pages/api/hello.js
export default function handler(req, res) {
  res.status(200).json({ text: 'Hello, world!' })
}
```

**2. Corrected API Route with CORS Headers:**

```javascript
// pages/api/hello.js
export default function handler(req, res) {
  res.setHeader('Access-Control-Allow-Origin', '*'); // Allow all origins (Use with caution!)
  res.setHeader('Access-Control-Allow-Methods', 'GET, POST, PUT, DELETE'); // Allow specific methods
  res.setHeader('Access-Control-Allow-Headers', 'Content-Type, Authorization'); // Allow specific headers

  if (req.method === 'GET') {
    res.status(200).json({ text: 'Hello, world!' })
  } else {
    res.status(405).end() // Method Not Allowed
  }
}
```

**Explanation:**

* `Access-Control-Allow-Origin`: This header specifies which origins are allowed to access the API.  `*` allows all origins, but **for production environments, this is generally insecure and should be replaced with a specific origin or a list of allowed origins.**  For example,  `res.setHeader('Access-Control-Allow-Origin', 'https://your-frontend-domain.com');`
* `Access-Control-Allow-Methods`: This header defines which HTTP methods are allowed (GET, POST, PUT, DELETE, etc.).
* `Access-Control-Allow-Headers`: This header specifies which headers the client is allowed to send in the request. `Content-Type` is commonly used for specifying the data format, and `Authorization` is used for authentication.

**Important Considerations:**

* **Security:**  Using `Access-Control-Allow-Origin: '*'` in production is a major security risk.  It allows any website to access your API.  Always restrict access to specific origins in production.
* **Preflight Requests (OPTIONS):** For certain requests (like those using POST with custom headers), the browser will send a preflight `OPTIONS` request before the actual request.  The server must handle this `OPTIONS` request correctly to allow the main request to proceed.  The code above implicitly handles this by setting the appropriate headers regardless of the request method.

**External References:**

* [MDN Web Docs on CORS](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS)
* [Next.js API Routes Documentation](https://nextjs.org/docs/api-routes/introduction)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

