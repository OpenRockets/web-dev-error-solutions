# 🐞 Next.js Middleware: Handling `headers` and `cookies` correctly for Redirects


## Description of the Error

A common issue when using Next.js Middleware to perform redirects is improperly handling the `headers` and `cookies` objects.  Attempting to modify cookies directly within the middleware's `response` object during a redirect often leads to unpredictable behavior or silently fails to set the intended cookies. This is particularly problematic when you need to set authentication cookies after redirecting a user to a protected route. The redirect might succeed, but the intended cookies may not be set correctly, causing further authentication issues.

## Code: Step-by-Step Fix

Let's say we want to redirect an unauthenticated user to `/login` after checking for the presence of a session cookie named `token`.  A naive, incorrect approach might look like this:


**Incorrect Approach:**

```javascript
// pages/api/middleware.js
import { NextResponse } from 'next/server'

export function middleware(req) {
  const token = req.cookies.get('token')?.value;

  if (!token) {
    const res = NextResponse.redirect(new URL('/login', req.url))
    res.cookies.set('redirect_to', req.nextUrl.pathname) // INCORRECT: This will likely fail
    return res;
  }
}

export const config = {
  matcher: '/',
}
```

This approach is flawed because the `res.cookies.set` method after initiating a redirect does not reliably set the cookie.

**Correct Approach:**

This improved version uses the `NextResponse.rewrite` method instead of `NextResponse.redirect`.  This ensures cookies are set before the response is sent.  We also handle setting the `redirect_to` cookie within the `NextResponse` constructor:

```javascript
// pages/api/middleware.js
import { NextResponse } from 'next/server'

export function middleware(req) {
  const token = req.cookies.get('token')?.value;

  if (!token) {
    return NextResponse.rewrite(new URL('/login', req.url), {
      headers: {
        'Set-Cookie': `redirect_to=${encodeURIComponent(req.nextUrl.pathname)}; Path=/; HttpOnly; Secure; SameSite=Strict`
      }
    });
  }
}

export const config = {
  matcher: '/',
}
```

**Explanation of the Fix:**

1. **`NextResponse.rewrite`:** Instead of `NextResponse.redirect`, we use `NextResponse.rewrite`. This method allows you to modify the response headers before the redirect.

2. **`headers` object:** We use the `headers` object within `NextResponse.rewrite` to set the cookie using the `Set-Cookie` header.  This is the correct and reliable way to set cookies in the response.

3. **Cookie attributes:**  The `Set-Cookie` header includes important attributes:
   - `Path=/`:  The cookie is accessible across all paths on the domain.
   - `HttpOnly`: The cookie is only accessible via HTTP requests and not client-side JavaScript, enhancing security.
   - `Secure`: The cookie is only sent over HTTPS, further increasing security.
   - `SameSite=Strict`: This prevents the cookie from being sent with cross-site requests.

4. **`encodeURIComponent`:**  This function is crucial for safely encoding the URL path to prevent issues with special characters.

Now, the redirect to `/login` will successfully set the `redirect_to` cookie, allowing you to handle the redirect appropriately on the `/login` page.


## External References

* [Next.js Middleware Documentation](https://nextjs.org/docs/app/building-your-application/routing/middleware)
* [NextResponse API Reference](https://nextjs.org/docs/api-reference/next/server#nextresponse)
* [HTTP Cookies](https://developer.mozilla.org/en-US/docs/Web/HTTP/Cookies)


## Copyright (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

