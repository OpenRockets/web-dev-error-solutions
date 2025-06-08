# 🐞 Next.js Middleware: Handling `headers` in the Response Object


## Description of the Error

A common issue when working with Next.js Middleware is incorrectly modifying the `headers` object within the `Response` object.  Middleware allows you to modify the request/response cycle before a page is rendered, but attempting to directly manipulate the `headers` property can lead to unexpected behavior or errors.  Specifically, you might find that modifications don't persist or that you receive runtime errors indicating the `headers` object is immutable.

This often happens when developers try to directly assign or modify header values like this:

```javascript
// Incorrect approach
export function middleware(req) {
  const res = NextResponse.next();
  res.headers.set('X-Custom-Header', 'some value'); // This will likely throw an error
  return res;
}
```

## Step-by-Step Code Fix

The correct way to modify response headers in Next.js Middleware involves using the `NextResponse.rewrite()` or `NextResponse.redirect()` methods, or updating the headers during the `NextResponse` object creation.


**Method 1: Using `NextResponse` constructor**

This is the most straightforward approach, setting the header directly when you create the `NextResponse` object.

```javascript
import { NextResponse } from 'next/server'

export function middleware(req) {
  const url = req.nextUrl.clone(); // create a copy to avoid modifying original URL
  const response = new NextResponse(null, {
    headers: {
      'X-Custom-Header': 'some value',
      'Cache-Control': 'public, max-age=31536000',
    },
  });
  return response;
}
```

**Method 2:  Using `NextResponse.rewrite()` for maintaining the original request**

If you need to rewrite the request to a different URL while setting headers, use `NextResponse.rewrite()`:

```javascript
import { NextResponse } from 'next/server'

export function middleware(req) {
    const url = req.nextUrl.clone(); // create a copy to avoid modifying original URL
    url.pathname = '/new-page'; // change the pathname
    return NextResponse.rewrite(url, {
        headers: {
            'X-Custom-Header': 'some value from rewrite',
        }
    });
}
```

**Method 3: Using `NextResponse.redirect()` for redirection**

If you need to redirect the user while adding headers, utilize `NextResponse.redirect()`:

```javascript
import { NextResponse } from 'next/server'

export function middleware(req) {
    return NextResponse.redirect(new URL('/redirected-page', req.url), {
        headers: {
            'X-Custom-Header': 'some value from redirect',
            'Location': '/redirected-page' // Important for redirection. This is added automatically if you don't specify it.
        }
    });
}
```


## Explanation

Directly manipulating the `headers` property of a `NextResponse` object after it has been created is not supported. The `NextResponse` object is immutable after creation. The methods described above correctly manage header additions and manipulations within the response lifecycle.  Using the constructor allows us to set headers during the response's initialization.  `NextResponse.rewrite()` and `NextResponse.redirect()` maintain the appropriate HTTP behaviors while integrating header modifications.


## External References

* [Next.js Middleware Documentation](https://nextjs.org/docs/app/api-routes/middleware)
* [NextResponse API Reference](https://nextjs.org/docs/api-reference/next/server#nextresponse)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

