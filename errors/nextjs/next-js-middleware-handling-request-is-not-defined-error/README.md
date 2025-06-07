# 🐞 Next.js Middleware: Handling `Request is not defined` Error


This document addresses a common error encountered when working with Next.js Middleware:  `ReferenceError: Request is not defined`. This error occurs because the `Request` object, crucial for middleware functionality, is not accessible in all contexts within your middleware function.  This typically happens when you try to access the `Request` object outside the middleware's main function, perhaps in a helper function or a module imported into the middleware.

**Description of the Error:**

The `ReferenceError: Request is not defined` error in Next.js Middleware means that your code is attempting to use the `Request` object (or other objects like `Response` provided by the middleware environment) in a location where it's not available.  The `Request` object is automatically provided as the first argument to your middleware function, but this context isn't propagated to other functions unless explicitly passed.

**Code: Problem and Solution**

Let's illustrate with an example.  Suppose you have a middleware function that needs to check user authentication before proceeding.  An incorrect implementation might look like this:

```javascript
// pages/api/middleware.js (INCORRECT)
import { getToken } from './auth';

export function middleware(req, res) {
  const token = getToken(req); // Error: Request is not defined inside getToken

  if (!token) {
    return new Response("Unauthorized", { status: 401 });
  }

  // ... rest of the middleware
}

export const config = {
  matcher: ['/protected/:path*'],
}

//pages/api/auth.js
export const getToken = (req) => {
  // ... logic to extract token from request headers ...
  const authHeader = req.headers.get('authorization');
  return authHeader;
}
```

The `getToken` function is attempting to use `req` which is only available directly within the `middleware` function.

Here's the corrected version:

```javascript
// pages/api/middleware.js (CORRECT)
import { getToken } from './auth';

export function middleware(req, res) {
  const token = getToken(req);

  if (!token) {
    return new Response("Unauthorized", { status: 401 });
  }

  // ... rest of the middleware
}

export const config = {
  matcher: ['/protected/:path*'],
}

//pages/api/auth.js
export const getToken = (req) => {
  // ... logic to extract token from request headers ...
  const authHeader = req.headers.get('authorization');
  return authHeader;
}
```

The solution is simple: pass the `req` object as an argument to `getToken`:


```javascript
// pages/api/middleware.js (CORRECT)
import { getToken } from './auth';

export function middleware(req, res) {
  const token = getToken(req); // Correct: req is explicitly passed

  if (!token) {
    return new Response("Unauthorized", { status: 401 });
  }

  // ... rest of the middleware
}

export const config = {
  matcher: ['/protected/:path*'],
}

//pages/api/auth.js
export const getToken = (req) => {
    // ... logic to extract token from request headers ...
    const authHeader = req.headers.get('authorization');
    return authHeader;
  }

```

**Explanation:**

The `Request` and `Response` objects are inherently tied to the Next.js middleware execution context.  They are not global objects.  To use them in any helper function, you must explicitly pass them as arguments. This ensures that the function receives the necessary context to operate correctly.


**External References:**

* [Next.js Middleware Documentation](https://nextjs.org/docs/app/building-your-application/routing/middleware)
* [Next.js API Routes Documentation](https://nextjs.org/docs/api-routes/introduction)


**Copyright (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.**

