# 🐞 Next.js Middleware: Handling `Error: Only absolute URLs are supported`


This document addresses a common error encountered when using Next.js Middleware: `Error: Only absolute URLs are supported`. This error typically arises when attempting to redirect or rewrite requests using relative URLs within your middleware function.  Middleware operates at a lower level than the client-side rendering context, meaning relative paths aren't interpreted correctly against the application's base URL.

## Description of the Error

The `Error: Only absolute URLs are supported` in Next.js Middleware indicates that you've used a URL path that's relative to the current request path, instead of an absolute URL that's relative to the entire application's domain. This often manifests when redirecting users based on authentication status, route-specific logic, or dynamically generated content paths.

## Code Example & Step-by-Step Fix

Let's say you have a middleware function that attempts to redirect users to `/profile` if they're not logged in:

**Problematic Code:**

```javascript
// pages/api/middleware.js
import { NextResponse } from 'next/server'

export function middleware(req) {
  const isLoggedIn = false; // Replace with your actual authentication check

  if (!isLoggedIn) {
    return NextResponse.redirect('/profile'); // This will throw the error
  }
}

export const config = {
  matcher: ['/'], // Match all routes
}
```

**Corrected Code:**

To fix this, we need to use an absolute URL.  We achieve this by constructing the URL using the `Request` object's `nextUrl` property:

```javascript
// pages/api/middleware.js
import { NextResponse } from 'next/server'

export function middleware(req) {
  const isLoggedIn = false; // Replace with your actual authentication check

  if (!isLoggedIn) {
    const res = NextResponse.redirect(new URL('/profile', req.url));
    return res;
  }
}

export const config = {
  matcher: ['/'], // Match all routes
}
```


**Explanation:**

The corrected code uses `new URL('/profile', req.url)` to construct an absolute URL.  `req.url` provides the base URL of the current request, and `/profile` is appended to create the complete, absolute URL for the redirect.  This ensures that the redirect works correctly regardless of the original request path.


## External References

* **Next.js Middleware Documentation:** [https://nextjs.org/docs/app/building-your-application/routing/middleware](https://nextjs.org/docs/app/building-your-application/routing/middleware)
* **NextResponse Documentation:** [https://nextjs.org/docs/api-reference/next/server#nextresponse](https://nextjs.org/docs/api-reference/next/server#nextresponse)
* **URL API (MDN):** [https://developer.mozilla.org/en-US/docs/Web/API/URL](https://developer.mozilla.org/en-US/docs/Web/API/URL)


## Explanation of the solution:

The core issue stems from the context in which middleware operates.  It runs before the client-side routing happens.  Therefore, a simple relative path like `/profile` lacks the context of the base URL.  By using `new URL('/profile', req.url)`, we explicitly create a fully qualified URL that's understandable to the middleware layer.  This ensures the redirect consistently targets the correct location within your Next.js application.


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

