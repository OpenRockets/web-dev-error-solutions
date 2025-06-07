# 🐞 Next.js Middleware: Handling `404` Errors Gracefully


## Description of the Error

A common issue in Next.js Middleware is how to gracefully handle `404` (Not Found) errors.  If a request hits middleware and doesn't match any defined routes, the middleware might not explicitly return a `404` response, leading to unexpected behavior or potentially leaving the user hanging with a blank page or a confusing error.  This is especially problematic if you rely on middleware to modify or redirect requests.  Without explicit `404` handling, the default Next.js behavior might not be ideal for your application.  For example, you might want to serve a custom `404` page rather than the default Next.js error page.

## Fixing Step-by-Step

Let's assume we have middleware that redirects specific paths and we want to serve a custom `404` for any other path.

**Step 1: Create a custom `404` page.**

Create a file named `404.js` (or `404.tsx`) in your `pages` directory with the following content:

```jsx
// pages/404.js
export default function Custom404() {
  return (
    <div>
      <h1>404 - Page Not Found</h1>
      <p>The page you are looking for does not exist.</p>
    </div>
  );
}
```

**Step 2: Implement Middleware with `404` Handling.**

Create (or modify) your middleware file (e.g., `middleware.js` or `middleware.ts` in the `pages` directory or a dedicated `middleware` directory).  The key is to explicitly return a response for paths that don't match your intended logic.

```javascript
// middleware.js
import { NextResponse } from 'next/server'

export function middleware(req) {
  const url = req.nextUrl.clone()

  //Example redirection to handle a specific path.
  if (req.nextUrl.pathname === '/old-page') {
    url.pathname = '/new-page'
    return NextResponse.rewrite(url)
  }


  // Check if the request matches a specific path. If not, return a 404.
  const allowedPaths = ['/', '/about', '/contact'];
  if (!allowedPaths.includes(req.nextUrl.pathname)) {
    return NextResponse.rewrite(new URL('/404', req.url))
  }

  return NextResponse.next()
}

export const config = {
  matcher: '/', // Match all paths. Adjust as needed.
}
```

**Explanation:**

* We import `NextResponse` from `next/server`.
* The `middleware` function intercepts requests.
* The code checks if the request's pathname matches a list of allowed paths.
* If the pathname is *not* in `allowedPaths`, it creates a new URL pointing to `/404` using `new URL('/404', req.url)` and returns a `NextResponse.rewrite` directing the user to the custom 404 page.
* `NextResponse.next()` allows the request to continue to the next handler if it's not a 404.
* `matcher: '/'` in the `config` object specifies that the middleware applies to all paths. Adjust this if you want to apply middleware to a subset of paths.

## External References

* [Next.js Middleware documentation](https://nextjs.org/docs/app/building-your-application/routing/middleware)
* [NextResponse API Reference](https://nextjs.org/docs/api-reference/next/server#nextresponse)


## Explanation

This approach ensures that any request not explicitly handled in the middleware is gracefully redirected to a custom 404 page. This provides a better user experience compared to the default Next.js error handling for unmatched routes.  Remember to adjust the `allowedPaths` array and the `matcher` configuration to match your application's routing structure.


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

