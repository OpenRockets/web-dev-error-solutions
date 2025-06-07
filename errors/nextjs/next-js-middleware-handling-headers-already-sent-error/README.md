# 🐞 Next.js Middleware: Handling `headers already sent` Error


This document addresses a common error developers encounter when working with Next.js Middleware: the `headers already sent` error. This error typically occurs when you try to send headers to the client more than once within a single request.  This often happens when you mix middleware with other response-modifying techniques.


**Description of the Error:**

The `headers already sent` error in Next.js Middleware indicates that your middleware function has already attempted to send headers to the client (e.g., using `res.setHeader()` or implicitly through a redirect) before another attempt to modify the response. This can be frustrating as it often doesn't provide clear context to its source.

**Scenario:**

Let's imagine you're building authentication middleware that redirects unauthenticated users and adds custom headers for authenticated users.  If you incorrectly attempt to redirect *after* setting custom headers, you'll run into this problem.


**Code Demonstrating the Error (Incorrect):**

```javascript
// pages/api/middleware.js
import { NextResponse } from 'next/server'

export function middleware(req) {
  const token = req.cookies.get('auth-token')

  if (!token) {
    //Incorrect Placement - sends headers before redirection
    res.setHeader('X-Custom-Header', 'some-value')
    return NextResponse.redirect(new URL('/login', req.url)) 
  }

  return NextResponse.next()
}


export const config = {
  matcher: ['/protected/:path*'],
}
```

**Step-by-Step Code Fix:**

1. **Prioritize Redirection:**  Always handle redirection *before* setting any headers. This ensures you're only manipulating the response if it isn't already committed to being a redirection.

2. **Conditional Header Setting:**  Only set headers if the request isn't being redirected.  This isolates the header setting logic to cases where it's safe to apply.

```javascript
// pages/api/middleware.js (Corrected)
import { NextResponse } from 'next/server'

export function middleware(req) {
  const token = req.cookies.get('auth-token')

  if (!token) {
    return NextResponse.redirect(new URL('/login', req.url))
  }

  //Set headers only if not redirected
  const response = NextResponse.next()
  response.headers.set('X-Custom-Header', 'some-value')
  return response;
}

export const config = {
  matcher: ['/protected/:path*'],
}
```

**Explanation:**

The corrected code prioritizes redirection. If the user isn't authenticated, a redirect is immediately returned.  If the user is authenticated, `NextResponse.next()` creates a response object that can safely have headers added later without conflicts; it then adds the custom header and returns the modified response.


**External References:**

* [Next.js Middleware Documentation](https://nextjs.org/docs/app/building-your-application/routing/middleware): The official documentation on Next.js Middleware.
* [Next.js API Routes Documentation](https://nextjs.org/docs/api-routes/introduction):  Understanding API routes helps clarify how middleware interacts with the request/response cycle.
* [MDN Web Docs - `headers already sent`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Headers_already_sent): A broader explanation of the error from a web development perspective.


**Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.**

