# 🐞 Next.js Middleware: Handling `next/server` Imports in Pages


This document addresses a common issue encountered when using Next.js Middleware: the inability to import modules from `next/server` within regular page components.  Attempting to do so results in runtime errors because Middleware runs on the server, while page components run on both the server (during Server-Side Rendering) and the client (during hydration).

**Description of the Error:**

You'll encounter a runtime error, typically a `ReferenceError` or an error indicating that a `next/server` module is not defined, when you try to use a function or component imported from `next/server` (e.g., `NextResponse`) within a page component's `page.js` file (or any other client-side rendered component).  This is because `next/server` modules are specifically designed for the server-side execution environment provided by Next.js Middleware or API routes.


**Code and Step-by-Step Fix:**

Let's say you have a function `redirectUser` in a file named `utils/redirect.js` that utilizes `NextResponse` from `next/server`:

```javascript
// utils/redirect.js (INCORRECT - will cause errors in page.js)
import { NextResponse } from 'next/server';

export function redirectUser(req, res, destination) {
  return NextResponse.redirect(new URL(destination, req.url));
}
```

And you attempt to use this function in your `page.js` file:

```javascript
// pages/my-page.js (INCORRECT - will cause errors)
import { redirectUser } from '../utils/redirect';

export default function MyPage() {
  // ... other code ...
  redirectUser(req, res, '/login'); // Error! req and res are undefined in the browser
  // ... other code ...
}
```

This will fail because `req` and `res` objects are only available on the server.  The `NextResponse` object itself is also server-side only.

**Correct Implementation:**

To solve this, separate server-side logic (using `next/server`) from client-side logic.  You can achieve this by creating an API route:

1. **Create an API Route:** Create a file at `pages/api/redirect.js`:

```javascript
// pages/api/redirect.js
import { NextResponse } from 'next/server';

export default function handler(req, res) {
  const destination = req.query.destination;
  return NextResponse.redirect(new URL(destination || '/', req.url));
}
```

2. **Call the API Route from your Page Component:**  Use `fetch` or a similar method to call the API route from your page component:

```javascript
// pages/my-page.js (CORRECT)
export default async function MyPage() {
  // ... other code ...
  const res = await fetch('/api/redirect?destination=/login');
  if (!res.ok) {
    // Handle error
  }
  // ... other code ...
}

```

**Explanation:**

By separating the redirect logic into an API route, the `next/server` imports and server-side functionalities are confined to the server-side code. The client-side component interacts with the server using standard `fetch` calls. This approach ensures that the code runs correctly in both the server and client environments, avoiding runtime errors.

**External References:**

* [Next.js API Routes](https://nextjs.org/docs/api-routes/introduction)
* [Next.js Middleware](https://nextjs.org/docs/app/building-your-application/routing/middleware)
* [Next.js Server Components](https://nextjs.org/docs/app/building-your-application/data-fetching/server-components)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

