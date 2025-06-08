# 🐞 Next.js Middleware: Handling `headers` in a non-standard way


This document addresses a common issue developers encounter when working with Next.js Middleware: manipulating response headers in a way that isn't fully compatible with the Next.js API and its expectations.  Specifically, this example tackles a scenario where attempting to set headers directly using `res.setHeader` within middleware leads to unexpected behavior or errors, particularly when dealing with redirects.

**Description of the Error:**

When using `res.setHeader` within a Next.js Middleware function to set custom headers before a redirect, the headers might not be correctly applied to the redirected response. This can manifest as missing headers in the final response received by the client, resulting in functionality relying on those headers (like CORS) to fail.  The error might not be explicitly thrown but rather observed as missing functionality or incorrect behavior on the client-side.

**Code Example (Illustrative Problem):**

```javascript
// pages/api/middleware.js
export function middleware(req, res) {
  // Incorrect way to set headers before redirect
  res.setHeader('Custom-Header', 'middleware-value'); 
  res.redirect('/about'); 
}

// pages/about.js
export default function AboutPage() {
  const customHeader = typeof window !== 'undefined' ? window.localStorage.getItem('customHeader') : null;
  return (
    <div>
      <h1>About Us</h1>
      {customHeader && <p>Custom Header: {customHeader}</p>}
    </div>
  );
}
```

In this code, we're *trying* to set a custom header within Middleware before redirecting.  However, this approach is not guaranteed to work reliably as `res.redirect` might override or ignore the manually set headers. The Client-Side Javascript (in `pages/about.js`) will not receive `customHeader`.


**Step-by-Step Fix:**

The correct approach is to utilize the `NextResponse` object to manage headers and redirects effectively:

```javascript
// pages/api/middleware.js (Corrected)
import { NextResponse } from 'next/server';

export function middleware(req) {
  const res = NextResponse.redirect(new URL('/about', req.url));
  res.headers.set('Custom-Header', 'middleware-value');
  return res;
}

// pages/about.js (Adjusted to access headers)
export default function AboutPage() {
  const customHeader = typeof window !== 'undefined' ? document.querySelector('meta[name="customHeader"]').content : null;

  return (
    <div>
      <h1>About Us</h1>
      <meta name="customHeader" content="" /> {/* added this meta tag */}
      {customHeader && <p>Custom Header: {customHeader}</p>}
    </div>
  );
}
```


**Explanation:**

1. **Import `NextResponse`:** We import the `NextResponse` object which provides the proper API for handling responses in Next.js Middleware.
2. **Use `NextResponse.redirect`:** Instead of `res.redirect`, we use `NextResponse.redirect` to create a `NextResponse` object representing the redirect. This object allows for proper header management.
3. **Set Headers using `res.headers.set`:**  We use `res.headers.set('Custom-Header', 'middleware-value')` to set the header correctly within the `NextResponse` object.  This ensures that the header is properly included in the redirect response.
4. **Return the `NextResponse` object:** It's crucial to return the `NextResponse` object from the middleware function to send the response including the header and redirection.
5. **Access Header on Client-Side:**  We now access the custom header through meta tags in the client-side, a more reliable approach since the middleware directly controls the response's headers.

**External References:**

* [Next.js Middleware documentation](https://nextjs.org/docs/app/building-your-application/routing/middleware)
* [NextResponse API Reference](https://nextjs.org/docs/app/api-reference/server-runtime/next-response)


**Copyright (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.**

