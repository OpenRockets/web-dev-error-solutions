# 🐞 Handling `getServerSideProps` Data in Next.js Middleware


## Description of the Error

A common issue when integrating Next.js Middleware with `getServerSideProps` (or `getStaticProps`) is attempting to access data fetched in `getServerSideProps` within the middleware.  Middleware runs *before* the page component, meaning the data fetched in `getServerSideProps` is not yet available.  This leads to errors like `undefined is not an object (evaluating 'props.data.someProperty')` or similar, depending on how you're trying to access the data.


## Step-by-Step Code Fix

Let's illustrate this with an example.  Suppose you have a page that fetches user data using `getServerSideProps` and you want to use that data to conditionally redirect based on user role in middleware.


**Incorrect Approach (Will Fail):**

```javascript
// pages/profile.js
export async function getServerSideProps(context) {
  const res = await fetch('https://api.example.com/user');
  const data = await res.json();

  return {
    props: {
      user: data,
    },
  };
}

export default function Profile({ user }) {
  return <div>Welcome, {user.name}!</div>;
}


// middleware.js
import { NextResponse } from 'next/server'

export function middleware(req) {
  const userRole = req.cookies.get('userRole'); //This is wrong and will not work
  const isAdmin = req.cookies.get('userRole') === 'admin';  

  if (!isAdmin && user.role !== 'admin') { // user is not defined here!!
    return NextResponse.redirect(new URL('/login', req.url))
  }
}

export const config = {
  matcher: '/profile',
};
```

**Correct Approach:**

The solution is to avoid directly accessing `getServerSideProps` data within the middleware. Instead, leverage cookies, session storage (using libraries like `next-auth`), or query parameters to pass necessary information from the page component to the middleware.


```javascript
// pages/profile.js
export async function getServerSideProps(context) {
  const res = await fetch('https://api.example.com/user');
  const data = await res.json();

  return {
    props: {
      user: data,
    },
  };
}

export default function Profile({ user }) {
  return <div>Welcome, {user.name}!</div>;
}

// middleware.js
import { NextResponse } from 'next/server'

export function middleware(req) {
  const userRole = req.cookies.get('userRole'); //Now this is right. we set this cookie in the backend on login.


  if (!userRole || userRole !== 'admin') {
    return NextResponse.redirect(new URL('/login', req.url))
  }
}

export const config = {
  matcher: '/profile',
};
```

Now,  we are only checking against userRole cookie. you have to set this cookie in the backend logic after successful login.


## Explanation

Middleware executes *before* any rendering logic, including `getServerSideProps`.  It has access to the request object but not the response data generated by the page component's data fetching functions.  Attempting to access `getServerSideProps` data directly leads to errors because that data hasn't been generated yet.  The solution is to manage the necessary data for the middleware's logic (like user authentication) separately using other methods like cookies, session storage, or query parameters.


## External References

* [Next.js Middleware Documentation](https://nextjs.org/docs/app/building-your-application/routing/middleware)
* [Next.js API Routes Documentation](https://nextjs.org/docs/api-routes/introduction)
* [Next.js getServerSideProps Documentation](https://nextjs.org/docs/basic-features/data-fetching/getserversideprops)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

