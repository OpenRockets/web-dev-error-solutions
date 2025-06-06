# 🐞 Next.js Middleware: Handling `headers` Issues in `next/server`


This document addresses a common problem developers encounter when using Next.js Middleware within the `next/server` API, specifically related to manipulating response headers.  The issue often manifests as unexpected behavior or errors when attempting to set or modify headers, leading to incorrect caching, CORS problems, or other functionalities not working as intended.

## Description of the Error

The error often isn't a specific, thrown error, but rather an unexpected result. For example, you might try to set a `Cache-Control` header to control browser caching, but the browser ignores your settings, leading to unpredictable behavior.  Another common issue is incorrect CORS handling where your middleware attempts to set CORS headers but fails to do so correctly, resulting in blocked requests from different origins.  The problem usually stems from misunderstanding how the `next/server` API handles the `Response` object and its methods for setting headers.

## Code: Step-by-Step Fix

Let's assume we're trying to add a `Cache-Control` header to our middleware to enable caching for 1 hour.  An incorrect approach might look like this:

**Incorrect Approach:**

```javascript
// middleware.js
import { NextResponse } from 'next/server'

export function middleware(req) {
  const res = NextResponse.next();
  res.headers.set('Cache-Control', 'public, max-age=3600'); //Incorrect!
  return res;
}
```

This is incorrect because the `headers` property of the `NextResponse` object is read-only after the initial response creation. The correct approach involves creating a new `NextResponse` object with the updated headers.

**Correct Approach:**

```javascript
// middleware.js
import { NextResponse } from 'next/server'

export function middleware(req) {
  const url = req.nextUrl.clone(); // clone the URL
  url.pathname = '/api/hello'
  const res = NextResponse.rewrite(url); // or NextResponse.redirect
  return new NextResponse(res.body, {
    headers: {
      'Cache-Control': 'public, max-age=3600',
    },
  });
}

// pages/api/hello.js
export default function handler(req, res) {
    res.status(200).json({ message: 'Hello from API!' });
}

```

This code first clones the current URL and rewrites it to `/api/hello`, allowing us to retrieve data from the API route. Subsequently it creates a new `NextResponse` object with the correct `Cache-Control` header.


## Explanation

The key to fixing this type of header-related problem is understanding that directly modifying the `headers` property of a `NextResponse` object after its initial creation is not supported.  You must create a *new* `NextResponse` instance with the desired headers.  This ensures that the headers are properly applied and that the response is correctly constructed. If using `NextResponse.rewrite` or `NextResponse.redirect`, the body is omitted therefore we have to add it manually on the new `NextResponse`


## External References

* [Next.js Middleware Documentation](https://nextjs.org/docs/app/building-your-application/routing/middleware)
* [Next.js API Routes Documentation](https://nextjs.org/docs/app/api-routes/introduction)
* [MDN Web Docs: Cache-Control](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Cache-Control)
* [MDN Web Docs: CORS](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

