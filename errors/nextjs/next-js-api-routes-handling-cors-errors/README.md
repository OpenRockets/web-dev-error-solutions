# 🐞 Next.js API Routes: Handling CORS Errors


This document addresses a common problem developers encounter when building APIs with Next.js API routes: **CORS (Cross-Origin Resource Sharing) errors**.  These errors occur when a client (e.g., a web browser making a fetch request from a different origin) tries to access your API route, and the server doesn't allow it.

## Description of the Error

The error typically manifests as a browser console error message like:

```
Access to XMLHttpRequest at 'https://your-nextjs-site.com/api/data' from origin 'https://your-client-site.com' has been blocked by CORS policy: No 'Access-Control-Allow-Origin' header is present on the requested resource.
```

This indicates that your API route is missing the necessary CORS headers to grant access from the client's origin.

## Step-by-Step Code Fix

Let's assume you have an API route at `/api/data` that returns some JSON data.  Here's how to fix the CORS issue:

**1.  Add CORS Middleware:**

The most robust approach is to use middleware to handle CORS for all your API routes. This avoids repetition in each individual route handler.  Create a middleware file (e.g., `middleware.js` or `middleware.ts` inside the `pages/api` directory):

```javascript
// pages/api/middleware.js
import { NextResponse } from 'next/server'

export function middleware(req) {
  const origin = req.headers.get('origin')

  // Allow requests from specific origins.  Replace with your actual origins.
  const allowedOrigins = ['https://your-client-site.com', 'http://localhost:3000'] 

  if (!allowedOrigins.includes(origin)) {
    return new NextResponse(null, { status: 403 }) // Forbidden
  }

  return NextResponse.next({
    headers: {
      'Access-Control-Allow-Origin': origin,
      'Access-Control-Allow-Methods': 'GET, POST, PUT, DELETE, OPTIONS', // Allow specific methods
      'Access-Control-Allow-Headers': 'Content-Type, Authorization', // Allow specific headers
      'Access-Control-Max-Age': '86400', // Cache preflight requests for 24 hours
    },
  })
}

export const config = {
  matcher: '/api/:path*', // Match all API routes
}
```


**2.  Your API Route (`pages/api/data.js`):**

This route remains largely unchanged.  The CORS headers are now handled by the middleware.

```javascript
// pages/api/data.js
export default function handler(req, res) {
  res.status(200).json({ message: 'Hello from API Route!' })
}
```

**Explanation:**

* The middleware intercepts all requests to routes matching `/api/:path*`.
* It checks if the request origin is allowed.  **Crucially**, you should replace `['https://your-client-site.com', 'http://localhost:3000']` with the actual origins your API should allow.  Using `*` is generally discouraged for security reasons.
* If the origin is allowed, it adds the necessary CORS headers to the response.
* `Access-Control-Allow-Origin` specifies the allowed origin(s).  `Access-Control-Allow-Methods` and `Access-Control-Allow-Headers` specify the allowed HTTP methods and headers, respectively.
* `Access-Control-Max-Age` allows the browser to cache preflight requests, improving performance.


## External References

* [Next.js API Routes Documentation](https://nextjs.org/docs/api-routes/introduction)
* [MDN Web Docs on CORS](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS)


## Conclusion

By implementing this middleware, you ensure that your Next.js API routes handle CORS correctly, preventing errors and allowing your client-side applications to access your data seamlessly. Remember to replace the placeholder origins with your actual allowed origins.


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

