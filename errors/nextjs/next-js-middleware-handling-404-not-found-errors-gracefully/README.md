# 🐞 Next.js Middleware: Handling `404 Not Found` Errors Gracefully


**Description of the error:**

A common issue when using Next.js Middleware is handling `404 Not Found` errors.  If a user navigates to a route that doesn't exist, the default behavior is to return a plain `404` response.  This can lead to a poor user experience, as it might not be clear to the user why the page is not found, or how they might navigate to the correct content.  Ideally, you'd want a custom 404 page that provides helpful information or redirects to a relevant page.

**Step-by-step code fix:**

The solution involves creating a custom `404` page and handling the `404` response within the middleware.  We'll use the `next/server` API's `notFound()` function.


**1. Create a custom 404 page:**

Create a file named `pages/404.js` (or `pages/404.tsx` if you're using TypeScript) with the following content:

```javascript
// pages/404.js
import Link from 'next/link';

export default function Custom404() {
  return (
    <div>
      <h1>404 - Page Not Found</h1>
      <p>The page you are looking for does not exist.</p>
      <Link href="/">
        <a>Go back to the homepage</a>
      </Link>
    </div>
  );
}
```

**2. Implement Middleware to handle the 404:**

Create (or modify) your middleware file (e.g., `middleware.js` or `middleware.ts` in the `pages` directory).  Import the `NextResponse` object and handle the 404:

```javascript
// middleware.js
import { NextResponse } from 'next/server';

export function middleware(req) {
  // ... other middleware logic ...

  if (req.nextUrl.pathname.startsWith('/api')) {
    //Skip middleware for API routes
    return NextResponse.next();
  }

  //check if route is valid.  Replace with your route validation
  const validRoutes = ['/', '/about', '/contact'];
  if (!validRoutes.includes(req.nextUrl.pathname)) {
    return NextResponse.rewrite(new URL('/404', req.url));
  }

  return NextResponse.next();
}


export const config = {
  matcher: ['/((?!api|_next/static|_next/image|favicon.ico).*)'], //Match all routes except API, static assets, and favicon
};
```

**Explanation:**

* **`pages/404.js`:** This component renders a custom 404 page with a user-friendly message and a link back to the homepage. You can customize this to fit your application's design and messaging.
* **`middleware.js`:** This middleware function intercepts requests before they reach the page rendering process.  The `if` statement checks if the requested route is valid. If not, `NextResponse.rewrite()` redirects the request to the `/404` page.  `NextResponse.next()` allows the request to proceed normally.
* **`matcher` config:** The `matcher` property in the `config` object specifies which paths the middleware should apply to.  The regular expression excludes API routes, static assets, and the favicon.  Adjust as needed for your application's structure.  Without this, the 404 redirect could infinitely loop.

**External References:**

* [Next.js Middleware Documentation](https://nextjs.org/docs/app/building-your-application/routing/middleware)
* [NextResponse API](https://nextjs.org/docs/api-reference/next/server#nextresponse)
* [Next.js Routing](https://nextjs.org/docs/app/building-your-application/routing)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

