# 🐞 Next.js Middleware: Handling `headers` manipulation for different paths


This document addresses a common issue developers encounter when using Next.js Middleware: correctly manipulating headers based on the requested path.  Improperly configured middleware can lead to unexpected behavior, such as incorrect caching or CORS issues across different parts of your application.  This example focuses on setting custom headers for specific routes.

**Description of the Error:**

Let's say you want to set a custom `Cache-Control` header for your `/blog` pages, but not for other parts of your site (like `/about` or `/contact`).  If you incorrectly configure your middleware, you might apply the header globally, causing unintended caching or performance implications.  The error might manifest as incorrect caching behavior (stale content) or unexpected responses from the browser depending on the misused header.


**Code (Step-by-Step Fix):**

Here's how to correctly set a `Cache-Control` header for only the `/blog` routes using Next.js Middleware:


**Incorrect (Global) Implementation:**

```javascript
// pages/api/middleware.js
import { NextResponse } from 'next/server'

export function middleware(req) {
  const res = NextResponse.next();
  res.headers.set('Cache-Control', 'public, max-age=3600'); // Incorrect: Applies to all routes
  return res;
}

export const config = {
  matcher: ['/((?!api|_next/static|_next/image|favicon.ico).*)'],
};
```

This incorrectly applies the `Cache-Control` header to all routes, ignoring path specificity.


**Correct (Path-Specific) Implementation:**

```javascript
// pages/api/middleware.js
import { NextResponse } from 'next/server'

export function middleware(req) {
  const url = req.nextUrl.clone();
  const pathname = url.pathname;

  if (pathname.startsWith('/blog')) {
    const res = NextResponse.next();
    res.headers.set('Cache-Control', 'public, max-age=3600');
    return res;
  }
  return NextResponse.next(); // Pass through for other paths
}

export const config = {
  matcher: ['/((?!api|_next/static|_next/image|favicon.ico).*)'],
};
```

This revised code checks the `pathname` before setting the header, ensuring it only applies to routes beginning with `/blog`.  Other requests pass through unaffected.



**Explanation:**

The key to solving this problem lies in leveraging the `req.nextUrl.pathname` property within the middleware function.  This provides the path of the requested URL, allowing conditional logic to determine whether to apply the header modification.  The `matcher` config ensures the middleware applies to all paths except for the API routes, static files, and Next.js internal paths.


**External References:**

* **Next.js Middleware Documentation:** [https://nextjs.org/docs/app/building-your-application/routing/middleware](https://nextjs.org/docs/app/building-your-application/routing/middleware)
* **NextResponse API Reference:** [https://nextjs.org/docs/api-reference/next/server/next-response](https://nextjs.org/docs/api-reference/next/server/next-response)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

