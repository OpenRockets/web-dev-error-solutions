# 🐞 Next.js Middleware: Handling `next/server` Imports Outside of Middleware


This document addresses a common error encountered when working with Next.js Middleware: attempting to import modules from `next/server` outside the middleware files themselves.  This results in runtime errors because these modules are specifically designed for the server-side rendering process within the middleware context.

## Description of the Error

When you try to import functions or components from the `next/server` package (e.g., `NextResponse`, `NextRequest`) in a regular component file or API route, you'll typically encounter an error similar to:

```
Error: Cannot find module 'next/server' or its corresponding type declarations.
```

This happens because the `next/server` modules are not available in the client-side or API route contexts, only within the middleware environment.

## Code: Fixing Step-by-Step

Let's say you have a function `redirectToLogin` that you want to use both in a middleware file and a regular page.  Incorrect implementation:

**Incorrect Approach (Will Fail):**

```javascript
// pages/login.js
import { redirect } from 'next/server'; // INCORRECT - This will throw an error

export default function LoginPage() {
  return <p>Login Page</p>;
}

//middleware.js
import { NextResponse } from 'next/server';

export function middleware(req) {
    const url = req.nextUrl.clone()
    url.pathname = '/login'
    return NextResponse.rewrite(url)
}
```


**Correct Approach:**


```javascript
// utils/redirect.js (create a utility file)
export const redirectToLogin = (req, res) => {
  // Depending on your environment choose the appropriate redirection method.
  if (typeof window === 'undefined'){ // Server-side (middleware)
      const url = req.nextUrl.clone()
      url.pathname = '/login'
      return NextResponse.rewrite(url);
  } else { //Client-side
    window.location.href = '/login'; //Client-side redirection
  }
};


// middleware.js
import { redirectToLogin } from '../utils/redirect';

export function middleware(req) {
  return redirectToLogin(req);
}

// pages/some-page.js
import { redirectToLogin } from '../utils/redirect';


export default function SomePage() {
  if (someCondition) { // Example condition
    redirectToLogin(null); // Pass null as the first argument as the req and res object will not be needed in the client side
  }
  return <p>Some Page</p>;
}
```


## Explanation

The corrected code separates the redirection logic into a utility function (`redirectToLogin`). This function checks if it's running server-side (`typeof window === 'undefined'`). If server-side (within middleware), it uses `NextResponse.rewrite`.  If client-side, it uses `window.location.href` for redirection.  This approach ensures compatibility across both middleware and client-side code.

## External References

* **Next.js Middleware Documentation:** [https://nextjs.org/docs/app/building-your-application/routing/middleware](https://nextjs.org/docs/app/building-your-application/routing/middleware)
* **Next.js API Routes Documentation:** [https://nextjs.org/docs/api-routes/introduction](https://nextjs.org/docs/api-routes/introduction)
* **NextResponse Object:** [https://nextjs.org/docs/api-reference/next/server#nextresponse](https://nextjs.org/docs/api-reference/next/server#nextresponse) (look for details on `rewrite`)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

