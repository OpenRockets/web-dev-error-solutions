# 🐞 Next.js Middleware: Handling `headers already sent` Error


This document addresses a common error encountered when working with Next.js Middleware: the `headers already sent` error. This typically happens when you try to set headers or send a response multiple times within the same middleware function.

**Description of the Error:**

The `headers already sent` error indicates that your Next.js middleware function has already begun sending a response to the client, but it's attempting to modify headers or send additional data. This usually happens because you've unintentionally called `next()` (or implicitly called it through redirect or rewrite) more than once or you've attempted to write to the response body after headers have been sent.  This is a common problem when you are trying to manipulate headers before routing happens or dealing with asynchronous operations.


**Full Code of Fixing Step by Step:**

Let's assume you have a middleware function intended to check for authentication and redirect unauthenticated users:

**Problem Code:**

```javascript
// middleware.js
import { NextResponse } from 'next/server'

export function middleware(req) {
  const token = req.cookies.get('token');

  if (!token) {
    const url = req.nextUrl.clone();
    url.pathname = '/login';
    return NextResponse.redirect(url); 
  }
  //This line will cause the error if the redirect above is already processed
  if (token === "invalid"){
      return new NextResponse("Unauthorized", { status: 401});
  }

  return NextResponse.next();
}

export const config = {
  matcher: ['/profile'],
}
```


**Corrected Code:**

```javascript
// middleware.js
import { NextResponse } from 'next/server'

export function middleware(req) {
  const token = req.cookies.get('token');

  if (!token) {
    const url = req.nextUrl.clone();
    url.pathname = '/login';
    return NextResponse.redirect(url); 
  }

  //Early exit to prevent multiple responses
  if (token === "invalid"){
      return new NextResponse("Unauthorized", { status: 401});
  }

  return NextResponse.next();
}

export const config = {
  matcher: ['/profile'],
}
```


**Explanation:**

The problem lies in having multiple `return` statements that send responses within the middleware.  In the corrected code, we added conditional checks. If an unauthenticated user is detected, a redirect is performed, and the function immediately terminates using the `return` statement. This prevents the subsequent check for an invalid token from executing after a response has already been sent.  Only one response is allowed per middleware execution.


**External References:**

* [Next.js Middleware Documentation](https://nextjs.org/docs/app/building-your-application/routing/middleware)
* [Next.js API Routes Documentation](https://nextjs.org/docs/api-routes/introduction)
* [Next.js Error Handling](https://nextjs.org/docs/app/building-your-application/handling-errors)


**Copyright (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.**

