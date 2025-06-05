# 🐞 Next.js Middleware: Handling `TypeError: Cannot read properties of undefined (reading 'locale')`


This document addresses a common `TypeError` encountered when using Next.js Middleware, specifically when attempting to access properties of the `req.cookies` object before verifying its existence.  This often happens when trying to determine user locale or other session-related data from cookies.

## Description of the Error

The error message `TypeError: Cannot read properties of undefined (reading 'locale')` indicates that you're trying to access the `locale` property (or a similar property) of the `req.cookies` object before ensuring it's defined.  This happens because `req.cookies` might be `undefined` if no cookies are present in the request, leading to the error when your code attempts to read a property from it.


## Code Example:  Problem & Solution

**Problematic Code:**

```javascript
// pages/api/middleware.js
export default function middleware(req, res) {
  const locale = req.cookies.locale; // Error occurs here if req.cookies is undefined

  if (locale === 'es') {
    // Redirect to Spanish version
    res.redirect('/es');
  } else {
    // Continue to default
  }
}
```

**Step-by-Step Solution:**

1. **Check for Cookie Existence:** Before accessing properties of `req.cookies`, always verify it's defined and contains the expected key.

2. **Use Optional Chaining:**  Next.js 13 and above make this significantly easier using optional chaining (`?.`):

```javascript
// pages/api/middleware.js
import { NextResponse } from 'next/server'

export function middleware(req) {
  const locale = req.cookies?.locale;

  if (locale === 'es') {
    return NextResponse.redirect(new URL('/es', req.url))
  }

  //Add other language checks
  if (locale === 'fr') {
    return NextResponse.redirect(new URL('/fr', req.url))
  }

}

export const config = {
  matcher: '/',
}

```

3. **Use Default Value (Alternative):** You can provide a default value if the cookie isn't found using the nullish coalescing operator (`??`):

```javascript
// pages/api/middleware.js
import { NextResponse } from 'next/server'

export function middleware(req) {
  const locale = req.cookies?.locale ?? 'en'; // Default to 'en' if no locale cookie

  if (locale === 'es') {
    return NextResponse.redirect(new URL('/es', req.url))
  }

  //Add other language checks
  if (locale === 'fr') {
    return NextResponse.redirect(new URL('/fr', req.url))
  }

}

export const config = {
  matcher: '/',
}
```


## Explanation

The optional chaining operator (`?.`) prevents the error by safely accessing properties of an object only if the object itself is defined.  If `req.cookies` is `undefined`, the expression `req.cookies?.locale` evaluates to `undefined` without throwing an error. The nullish coalescing operator (`??`) provides a fallback value if the left-hand operand is `null` or `undefined`.


## External References

* [Next.js Middleware Documentation](https://nextjs.org/docs/app/building-your-application/routing/middleware)
* [Optional Chaining Operator (?.)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Optional_chaining)
* [Nullish Coalescing Operator (??)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Nullish_coalescing_operator)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

