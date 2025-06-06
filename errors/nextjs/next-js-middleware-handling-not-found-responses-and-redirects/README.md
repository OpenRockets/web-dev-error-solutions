# 🐞 Next.js Middleware: Handling `not_found` Responses and Redirects


This document addresses a common issue developers encounter when using Next.js Middleware: incorrectly handling `not_found` responses and subsequent redirects.  Improperly configured middleware can lead to unexpected behavior, such as infinite redirect loops or failure to display a custom 404 page.


**Description of the Error:**

When a request hits your Next.js Middleware, and the middleware determines that the resource is not found (e.g., a non-existent page), it needs to return a proper `not_found` response.  Failing to do so, or attempting a redirect within the `not_found` response logic incorrectly, can result in the application getting stuck in a redirect loop or failing to display a 404 page.  The error manifests as an endless redirect loop in the browser, or a blank page with no helpful error messages.


**Code: Step-by-Step Fix**

Let's assume we have a middleware function that attempts to redirect based on a condition, and if the condition fails, it should return a 404.

**Incorrect Middleware:**

```javascript
// pages/api/middleware.js
import { NextResponse } from 'next/server'

export function middleware(req) {
  const path = req.nextUrl.pathname;

  if (path === '/some-page') {
    return NextResponse.redirect(new URL('/home', req.url));
  } else {
    // INCORRECT: This will cause an infinite redirect loop if the route is not found
    return NextResponse.redirect(new URL('/404', req.url)); 
  }
}

export const config = {
  matcher: ['/some-page', '/another-page'],
};
```

**Corrected Middleware:**

```javascript
// pages/api/middleware.js
import { NextResponse } from 'next/server'

export function middleware(req) {
  const path = req.nextUrl.pathname;

  if (path === '/some-page') {
    return NextResponse.redirect(new URL('/home', req.url));
  } else {
    // CORRECT: Returns a proper 404 response
    return new Response('Not Found', { status: 404 });
  }
}

export const config = {
  matcher: ['/some-page', '/another-page'],
};
```

**Explanation:**

The incorrect code uses `NextResponse.redirect` even when the page is not found.  This leads to a continuous redirect loop. The correct version uses `new Response('Not Found', { status: 404 })` which explicitly returns a 404 status code, allowing Next.js to handle the error gracefully and display a custom 404 page (if defined).  `NextResponse.redirect` should only be used when a redirect is intended, and only after successful path validation within the middleware function.


**External References:**

* [Next.js Middleware Documentation](https://nextjs.org/docs/app/building-your-application/routing/middleware)
* [NextResponse API Reference](https://nextjs.org/docs/api-reference/next/server#nextresponse)
* [Handling 404 Errors in Next.js](https://nextjs.org/docs/app/building-your-application/routing/404)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

