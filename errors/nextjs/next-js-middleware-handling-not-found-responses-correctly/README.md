# 🐞 Next.js Middleware: Handling `not-found` Responses Correctly


**Description of the Error:**

A common issue when using Next.js Middleware is incorrectly handling `not-found` responses.  If your middleware attempts to redirect or modify a request that ultimately results in a 404 (Not Found) error from your application, you might see unexpected behavior, such as redirects that don't work or unexpected error pages. This often stems from trying to modify the response after a `notFound` is already determined.

**Scenario:**  Imagine you have middleware that checks for authentication and redirects unauthenticated users to the login page. If the requested page itself doesn't exist (a 404), the middleware might still attempt to redirect, leading to a confusing user experience.


**Step-by-Step Code Fix:**

Let's say we have middleware that attempts to redirect unauthenticated users, but fails gracefully if the page is already a 404:

**Incorrect Middleware:**

```javascript
// middleware.js (INCORRECT)
import { NextResponse } from 'next/server'

export function middleware(req) {
  const token = req.cookies.get('token')

  if (!token) {
    return NextResponse.redirect(new URL('/login', req.url))
  }
}

export const config = {
  matcher: ['/((?!api|_next/static|_next/image|favicon.ico).*)'],
}
```

This code redirects unauthenticated users, but will attempt a redirect *even if the page the user is requesting doesn't exist*.  This is problematic.

**Correct Middleware:**

```javascript
// middleware.js (CORRECT)
import { NextResponse } from 'next/server'

export async function middleware(req) {
  const token = req.cookies.get('token')
  const response = NextResponse.next();

  if (!token) {
    const url = new URL('/login', req.url);
    
    //Check if the original request already resulted in a 404, and bypass the redirect if so
    if(response.status != 404){
        return NextResponse.redirect(url)
    } else {
      return response;
    }
  }
  return response;
}

export const config = {
  matcher: ['/((?!api|_next/static|_next/image|favicon.ico).*)'],
}
```

This improved version checks the response status before redirecting.  If it's already a 404, it avoids the unnecessary redirect and lets the `notFound` response proceed.


**Explanation:**

The key change is the addition of a check against `response.status`. Before attempting the redirect, the middleware now verifies whether the underlying request has already resulted in a 404.  Only if the status is not a 404, does it proceed with the redirect. This ensures that the middleware gracefully handles cases where the requested resource is not found.  The `NextResponse.next()` method is essential, acting as a default response which middleware can modify.


**External References:**

* [Next.js Middleware Documentation](https://nextjs.org/docs/app/building-your-application/routing/middleware)
* [NextResponse API Reference](https://nextjs.org/docs/api-reference/next/server#nextresponse)


**Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.**

