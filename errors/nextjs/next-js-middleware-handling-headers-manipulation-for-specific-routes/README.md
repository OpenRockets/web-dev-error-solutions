# 🐞 Next.js Middleware: Handling `headers` Manipulation for Specific Routes


This document addresses a common issue encountered when using Next.js Middleware: incorrectly modifying headers and potentially affecting all routes instead of targeting a specific one.  Middleware, powerful for its ability to modify requests and responses globally, can lead to unexpected behavior if not carefully scoped. This example focuses on applying custom headers only to a specific path.

**Description of the Error:**

Let's say you want to add a `Cache-Control` header to improve performance, but only for requests to `/api/products`. If you apply the header modification globally within the middleware, all routes, including your pages, will inherit this header. This can lead to caching issues for pages that shouldn't be cached or conflicting with existing caching strategies.

**Code (Incorrect Implementation):**

```javascript
// middleware.js (Incorrect)
import { NextResponse } from 'next/server'

export function middleware(req) {
  const res = NextResponse.next();
  res.headers.set('Cache-Control', 'public, max-age=3600'); //Incorrectly applied to all routes
  return res;
}

export const config = {
  matcher: '/', //this matches all routes, leading to the global issue
}
```

**Code (Step-by-step Fix):**

1. **Specify the matcher:** The `matcher` property in the `config` object determines which routes the middleware affects.  Instead of `'/'`, we'll use a more specific matcher to target only `/api/products`.

2. **Conditional Header Setting:**  Inside the middleware function, we'll check the request path before setting the header.

```javascript
// middleware.js (Corrected)
import { NextResponse } from 'next/server'

export function middleware(req) {
  const res = NextResponse.next();

  // Check if the request is for /api/products
  if (req.nextUrl.pathname.startsWith('/api/products')) {
    res.headers.set('Cache-Control', 'public, max-age=3600');
  }

  return res;
}

export const config = {
  matcher: '/api/products', // Matches only /api/products and its subpaths
}
```


**Explanation:**

The corrected code addresses the issue by:

* **Precise Matching:** The `matcher: '/api/products'` ensures the middleware only runs for requests starting with `/api/products`.  This avoids unintended consequences on other routes.
* **Conditional Logic:** The `if` statement within the `middleware` function checks the `req.nextUrl.pathname` to confirm if the current request URL matches the target before setting the header. This allows fine-grained control over header manipulation.

**External References:**

* [Next.js Middleware Documentation](https://nextjs.org/docs/app/building-your-application/routing/middleware):  The official Next.js documentation on Middleware.
* [NextResponse API Reference](https://nextjs.org/docs/api-reference/next/server#nextresponse): Learn more about the `NextResponse` object and its methods.


**Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.**

