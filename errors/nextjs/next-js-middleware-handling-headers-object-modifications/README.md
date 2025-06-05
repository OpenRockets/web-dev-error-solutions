# 🐞 Next.js Middleware: Handling `headers` Object Modifications


This document addresses a common issue developers encounter when working with Next.js Middleware: Unexpected behavior or errors related to modifying the `headers` object.  Middleware provides a powerful way to intercept requests and modify responses before they reach the page, but improper manipulation of the `headers` object can lead to unexpected results.  This example specifically focuses on issues arising from directly mutating the `headers` object, instead of using the correct approach provided by the `NextResponse` object.


**Description of the Error:**

Attempting to directly modify the `headers` object passed into the middleware function often results in no changes being reflected in the final response.  This is because middleware functions don't directly modify the original `headers` object; they create a copy internally.  Changes made directly to the passed object are therefore discarded.  You might see no errors, but the headers will not be changed as expected, leading to debugging headaches.  This often manifests in issues with CORS, caching, or custom headers not being applied correctly.

**Step-by-Step Code Fix:**

Let's say we want to add a custom header, `X-Custom-Header: MyValue`, to all responses. Incorrect and correct implementations are shown below.

**Incorrect Implementation (Will not work):**

```javascript
// pages/api/middleware.js
export function middleware(req) {
  req.headers['X-Custom-Header'] = 'MyValue'; // Incorrect:  This does NOT modify the response headers.
  return NextResponse.next();
}
export const config = {
  matcher: ['/'], // Match all routes
};
```

**Correct Implementation (Using NextResponse):**

```javascript
// pages/api/middleware.js
import { NextResponse } from 'next/server';

export function middleware(req) {
  const res = NextResponse.next();
  res.headers.set('X-Custom-Header', 'MyValue'); // Correct: Modifies the response headers correctly
  return res;
}
export const config = {
  matcher: ['/'], // Match all routes
};
```

**Explanation:**

The correct implementation uses the `NextResponse` object to properly manage the response headers.  `NextResponse.next()` creates a new response object, and the `.headers.set()` method correctly modifies the headers of *this new response object*.  This modified response is then returned, ensuring the changes are applied.  Directly modifying the `req.headers` object has no effect on the final response.



**External References:**

* **Next.js Middleware Documentation:** [https://nextjs.org/docs/app/building-your-application/routing/middleware](https://nextjs.org/docs/app/building-your-application/routing/middleware)  (Check for the latest documentation)
* **NextResponse API Reference:** [https://nextjs.org/docs/api-reference/next/server#nextresponse](https://nextjs.org/docs/api-reference/next/server#nextresponse) (Check for the latest documentation)


**Summary:**

Always use the `NextResponse` object to modify headers within Next.js Middleware.  Directly manipulating the `headers` object passed into the middleware function is ineffective and will lead to unexpected behavior.  The `NextResponse.next()` method returns a response object which allows you to modify its headers.


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

