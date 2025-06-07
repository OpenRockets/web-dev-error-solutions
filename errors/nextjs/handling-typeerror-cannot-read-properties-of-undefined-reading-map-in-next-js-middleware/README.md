# 🐞 Handling `TypeError: Cannot read properties of undefined (reading 'map')` in Next.js Middleware


This document addresses a common error encountered when working with Next.js Middleware:  `TypeError: Cannot read properties of undefined (reading 'map')`. This typically arises when attempting to iterate over an array or object that is unexpectedly undefined within the middleware function.  Middleware runs early in the request lifecycle, before data fetching, making it prone to this error if you're relying on data fetched from a database or API.


**Scenario:**

Let's imagine a middleware function designed to redirect users based on their role fetched from a session.  If the session data is not yet available, or the role property is missing, the `map` method will throw the error.


**Erroneous Code:**

```javascript
// pages/api/middleware.js
import { NextResponse } from 'next/server'

export function middleware(req) {
  const session = req.cookies.get('session'); //Potentially undefined!
  const roles = session?.user?.roles || []; // Attempt to handle undefined, but might still fail

  const adminRoles = roles.map(role => role.toLowerCase()); // Error occurs here if roles is undefined

  if (adminRoles.includes('admin')) {
    return NextResponse.rewrite(new URL('/admin', req.url));
  }

  return NextResponse.next();
}

export const config = {
  matcher: ['/'],
};
```


**Corrected Code (Step-by-Step):**


1. **Robust Null and Undefined Checks:**  The most crucial step is to thoroughly check for `undefined` or `null` values at each stage.


```javascript
// pages/api/middleware.js
import { NextResponse } from 'next/server'

export function middleware(req) {
  const session = req.cookies.get('session');

  // Check if session exists before accessing nested properties
  if (!session || !session.user || !session.user.roles) {
    return NextResponse.next(); // Continue to the next middleware or page
  }

  const roles = session.user.roles;
  const adminRoles = roles.map(role => role.toLowerCase());

  if (adminRoles.includes('admin')) {
    return NextResponse.rewrite(new URL('/admin', req.url));
  }

  return NextResponse.next();
}

export const config = {
  matcher: ['/'],
};
```

2. **Optional Chaining (?.) and Nullish Coalescing (??):**  For cleaner code, utilize optional chaining and nullish coalescing. This simplifies the null checks:

```javascript
// pages/api/middleware.js
import { NextResponse } from 'next/server'

export function middleware(req) {
  const roles = req.cookies.get('session')?.user?.roles ?? []; // Use optional chaining and nullish coalescing

  const adminRoles = roles.map(role => role.toLowerCase());

  if (adminRoles.includes('admin')) {
    return NextResponse.rewrite(new URL('/admin', req.url));
  }

  return NextResponse.next();
}

export const config = {
  matcher: ['/'],
};
```


**Explanation:**

The original code failed because it assumed the `roles` array would always exist.  The corrected code adds checks to ensure `session`, `session.user`, and `session.user.roles` are defined *before* attempting to access them.  Optional chaining and nullish coalescing make this process more concise and readable.  If any part of the chain is `null` or `undefined`, the expression short-circuits, preventing the error. The `?? []` ensures that `roles` is always an array, even if the preceding expression is nullish.


**External References:**

* [Next.js Middleware Documentation](https://nextjs.org/docs/app/building-your-application/routing/middleware)
* [Next.js API Routes Documentation](https://nextjs.org/docs/api-routes/introduction)
* [JavaScript Optional Chaining](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Optional_chaining)
* [JavaScript Nullish Coalescing](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Nullish_coalescing_operator)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

