# 🐞 Next.js Middleware: Handling `headers already sent` Error


This document addresses a common error encountered when working with Next.js Middleware: the "headers already sent" error.  This typically occurs when you attempt to send headers to the response object multiple times, often due to accidental duplicate calls or incorrect asynchronous handling.

## Description of the Error

The `headers already sent` error in Next.js Middleware (and Node.js in general) arises when your code tries to modify the HTTP response headers after the response has already begun being sent to the client.  This prevents the server from correctly responding, resulting in a broken request and often a 500 Internal Server Error.

## Code Example & Step-by-Step Fix

Let's imagine a scenario where we're using middleware to redirect users based on a cookie.  A common mistake is to inadvertently send headers multiple times within the `middleware` function or from within asynchronous code that isn't properly awaited.

**Problematic Code:**

```javascript
// pages/api/middleware.js
import { NextResponse } from 'next/server'

export function middleware(req) {
  const cookie = req.cookies.get('user')

  if (!cookie) {
    const res = NextResponse.redirect(new URL('/login', req.url))
    // Problem:  This sends a redirect.
    res.headers.set('X-Custom-Header', 'value') // This will throw the error because the response is already sent.
    return res;
  }

  return NextResponse.next();
}

export const config = {
  matcher: '/',
}
```

**Step-by-Step Fix:**

1. **Ensure single header modification:** The key is to make sure you're only setting headers *before* the response is returned. Move all header modifications before the `return res` statement or any other statement that sends the response.


2. **Correctly handle asynchronous operations:** If you're fetching data or performing other asynchronous operations before sending the response, ensure you're using `async/await` to handle the promises correctly. Otherwise, your headers might be set after the response has already started.


**Corrected Code:**

```javascript
// pages/api/middleware.js
import { NextResponse } from 'next/server'

export async function middleware(req) {
  const cookie = req.cookies.get('user')

  if (!cookie) {
    const res = NextResponse.redirect(new URL('/login', req.url))
    res.headers.set('X-Custom-Header', 'value') // Now this will work because it's before the return.
    return res;
  }

  return NextResponse.next();
}

export const config = {
  matcher: '/',
}
```

## Explanation

The `headers already sent` error is fundamentally a timing issue.  Once the `NextResponse` object starts sending the response (e.g., via `redirect`, `json`, or implicitly when the function ends without a returned response), further attempts to modify headers are invalid.  The server has already committed to the response structure.

Using `async/await` ensures that asynchronous operations are completed before the response is sent, preventing race conditions. The corrected code demonstrates placing header setting before the return statement which prevents multiple attempts at modifying headers.

## External References

* [Next.js Middleware Documentation](https://nextjs.org/docs/app/building-your-application/routing/middleware)
* [Node.js HTTP Response](https://nodejs.org/api/http.html#http_class_http_serverresponse) (relevant for understanding the underlying HTTP mechanics)
* [Understanding Async/Await in JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/async_function)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

