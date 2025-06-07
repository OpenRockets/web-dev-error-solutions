# 🐞 Next.js Middleware: Preventing Infinite Redirects


This document addresses a common issue developers encounter when using Next.js Middleware: unintended infinite redirect loops.  This typically occurs when middleware redirects to a route that itself triggers the same middleware, creating a recursive redirect chain that never terminates.

## Description of the Error

The error doesn't manifest as a specific error message in the console. Instead, you'll observe your browser continuously loading, showing the spinning loading indicator, or experiencing an extremely slow page load.  Your browser's network tab will likely show a series of increasingly long redirect requests, indicating the infinite loop.  This often happens when you're trying to implement authentication or conditional redirects based on routes.

## Code Example & Step-by-Step Fix

Let's assume we're building an application where only authenticated users can access the `/dashboard` route.  An incorrect implementation might lead to an infinite redirect:

**Incorrect Middleware (`middleware.js`):**

```javascript
import { NextResponse } from 'next/server';

export function middleware(req) {
  const session = req.cookies.get('session'); // Simplistic session check

  if (!session) {
    return NextResponse.redirect(new URL('/login', req.url));
  }
}

export const config = {
  matcher: ['/dashboard'],
};
```

**Incorrect Login Page (`pages/login.js`):**  This would cause the infinite loop because the `/login` page also triggers the `middleware` if it doesn't have a session cookie.

```javascript
// pages/login.js - some basic login page
export default function Login() {
    return <div>Login Page</div>;
}
```

**Step 1: Identifying the Loop**

Carefully examine your middleware's logic and the routes it redirects to. Look for cases where the redirect target also triggers the same middleware.  In this example, both `/dashboard` and `/login` indirectly or directly trigger the same middleware leading to a loop.

**Step 2:  Using `next/server.js` to prevent redirection of /login**

The correct solution requires that the `/login` path *doesn't* trigger the middleware again.  We can achieve this by using the `matcher` config more precisely.

**Corrected Middleware (`middleware.js`):**

```javascript
import { NextResponse } from 'next/server';

export function middleware(req) {
  const session = req.cookies.get('session');

  if (!session) {
    return NextResponse.redirect(new URL('/login', req.url));
  }
}

export const config = {
  matcher: ['/dashboard/:path*'], // Only match routes starting with /dashboard
};
```

**Step 3:  Consider a different approach for protected routes (if possible)**

In many cases, the best solution would be to check authentication on the protected component itself using `getServerSideProps` or `getStaticProps` to fetch user data, or using a library like `next-auth` to manage authentication.

**Corrected Dashboard Page (`pages/dashboard.js`):**

```javascript
import { getSession } from 'next-auth/react';

export async function getServerSideProps(context) {
  const session = await getSession(context);
  if (!session) {
    return {
      redirect: {
        destination: '/login',
        permanent: false,
      },
    };
  }
  return { props: { session } };
}

export default function Dashboard({ session }) {
  return (
    <div>
      <h1>Dashboard</h1>
      <p>Welcome, {session.user.email}!</p>
    </div>
  );
}
```

This approach moves authentication logic to the component itself, preventing the middleware from recursively redirecting.



## Explanation

The infinite redirect occurs because the middleware's redirect logic is recursively called. By carefully defining the `matcher` property in the middleware's `config` object,  we explicitly control which routes trigger the middleware.  Furthermore, moving the authentication check to the protected route, ensures that the middleware is only used for a single redirection.


## External References

* [Next.js Middleware Documentation](https://nextjs.org/docs/app/building-your-application/routing/middleware)
* [NextAuth.js](https://next-auth.js.org/) - A popular authentication library for Next.js.


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

