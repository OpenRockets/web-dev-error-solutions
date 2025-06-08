# 🐞 Next.js Middleware: Handling `request.nextUrl.pathname` in Redirect


This document addresses a common issue encountered when using Next.js Middleware:  incorrectly handling the `request.nextUrl.pathname` property, leading to unintended redirect loops or unexpected behavior.  This often occurs when attempting to redirect based on the current pathname but inadvertently creating a circular redirect.

**Description of the Error:**

When using middleware to redirect based on the URL path, developers might incorrectly manipulate the `request.nextUrl.pathname` directly within the middleware function.  If not handled carefully, changing `request.nextUrl.pathname` to a value that already matches the current path (or triggers another redirect to the same path) will create an infinite redirect loop, resulting in a browser error.

**Scenario:** Let's say you want to redirect all requests to `/blog` to `/news` unless the current path is already `/news`.  A naive approach might look like this:

```javascript
// pages/api/middleware.js (incorrect)
export function middleware(req) {
  if (req.nextUrl.pathname.startsWith('/blog')) {
    req.nextUrl.pathname = '/news';
    return NextResponse.rewrite(req.nextUrl);
  }
}
export const config = {
  matcher: ['/blog/:path*'],
};
```

This will lead to an infinite loop if the user is already on `/news`.  After the redirect, `req.nextUrl.pathname` will become `/news`, and the condition `req.nextUrl.pathname.startsWith('/blog')` will still be false during the next request from the browser after the initial redirect.

**Step-by-Step Code Fix:**

The solution involves using the `NextResponse.redirect()` method instead of `NextResponse.rewrite()` and ensuring that the redirect target is different from the current path.

```javascript
// pages/api/middleware.js (correct)
import { NextResponse } from 'next/server';

export function middleware(req) {
  const currentPath = req.nextUrl.pathname;
  if (currentPath.startsWith('/blog') && currentPath !== '/news') {
    return NextResponse.redirect(new URL('/news', req.url));
  }
  return NextResponse.next();
}
export const config = {
  matcher: ['/blog/:path*'],
};
```


**Explanation:**

1. **`currentPath = req.nextUrl.pathname;`**: We store the original pathname in a variable to avoid modifying the original request URL object.

2. **`if (currentPath.startsWith('/blog') && currentPath !== '/news')`**: This condition checks if the path starts with `/blog` *and* is not already `/news`. This prevents the infinite redirect loop.

3. **`return NextResponse.redirect(new URL('/news', req.url));`**:  `NextResponse.redirect()` performs a proper HTTP redirect, ensuring the browser gets a new response with the correct status code. Using `new URL('/news', req.url)` constructs a correctly formatted URL, using the original request's base URL to avoid potential issues with relative paths.

4. **`return NextResponse.next();`**: If the condition is false (the path doesn't start with `/blog` or it's already `/news`), the middleware continues processing the request without interfering.

**External References:**

* [Next.js Middleware Documentation](https://nextjs.org/docs/app/building-your-application/routing/middleware)
* [NextResponse API Reference](https://nextjs.org/docs/api-reference/next/server#nextresponse)


**Copyright (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.**

