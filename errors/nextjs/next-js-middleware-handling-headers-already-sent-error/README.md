# 🐞 Next.js Middleware: Handling `headers already sent` Error


This document addresses a common error encountered when working with Next.js Middleware: the "headers already sent" error.  This typically occurs when you attempt to set headers after the response has already begun being sent to the client.

## Description of the Error

The `headers already sent` error in Next.js Middleware manifests as a server-side error.  It prevents your middleware from properly modifying the response headers, resulting in unexpected behavior or a broken application.  The underlying cause is usually attempting to send headers (e.g., using `res.setHeader`, `res.writeHead`, or implicitly through a redirect) after some data has already been written to the response stream. This is often subtle and can be hard to track down.

## Code Example: Problem & Solution

Let's consider a scenario where you're trying to redirect users to a login page if they are not authenticated, using middleware:

**Problem Code (middleware.js):**

```javascript
import { NextResponse } from 'next/server'

export function middleware(req) {
  const session = req.cookies.get('session')

  if (!session) {
    console.log("User not authenticated, redirecting..."); //This log will appear
    // Problem:  The next line tries to redirect AFTER implicitly sending data (console.log)
    return NextResponse.redirect(new URL('/login', req.url)) 
  }
}

export const config = {
  matcher: '/',
}
```

In this example, the `console.log` statement implicitly sends data to the response stream *before* the redirect. This triggers the "headers already sent" error.


**Solution Code (middleware.js):**

```javascript
import { NextResponse } from 'next/server'

export function middleware(req) {
  const session = req.cookies.get('session')

  if (!session) {
    return NextResponse.redirect(new URL('/login', req.url)) 
  }
}

export const config = {
  matcher: '/',
}
```

The solution is simply to remove the `console.log` statement.  Any output to the console (or any other implicit response writing, like prematurely rendering a component) before setting headers will cause this error.  Always ensure all header manipulation happens *before* any data is sent to the client.


## Explanation

Next.js Middleware operates at a low level, interacting directly with the HTTP response.  Once the response begins sending data, it's too late to modify headers.  The order of operations is crucial.  Headers must be set *before* any other part of the response is sent.  This includes:

* **Console Output:** `console.log`, `console.error`, etc.  These implicitly send data.
* **Implicit Data:**  Any data written directly to the response stream (e.g., through a premature `res.write` or by rendering a component).
* **Early Redirects:** Incorrectly placed redirects within conditional statements.

The provided solution prioritizes the `NextResponse.redirect` which properly manages headers before sending the redirect.


## External References

* [Next.js Middleware Documentation](https://nextjs.org/docs/app/building-your-application/routing/middleware) - The official Next.js documentation for middleware.
* [Next.js API Routes Documentation](https://nextjs.org/docs/api-routes/introduction) -  Understanding API routes helps to contrast with middleware behavior.
* [HTTP Headers](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers) - A general understanding of HTTP headers is beneficial.


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

