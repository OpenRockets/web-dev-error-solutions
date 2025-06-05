# 🐞 Next.js Middleware: Handling `next/server` Import Errors


This document addresses a common error developers encounter when working with Next.js Middleware: importing modules from `next/server`. This error typically occurs when developers attempt to use server-side-only modules in client-side components or pages.

**Description of the Error:**

The error usually manifests as a runtime error or a build-time error, indicating that a module from `next/server` (e.g., `NextResponse`, `Headers`) is being accessed in a context where it's not available.  You'll see error messages like:

* `ReferenceError: NextResponse is not defined`
* `Module not found: Can't resolve 'next/server' in ...`
* Build errors related to incompatible modules

**Full Code of Fixing Step by Step:**

Let's consider a scenario where you're trying to use `NextResponse` in a component that also renders on the client-side:

**Incorrect Code (Problem):**

```javascript
// pages/my-page.js
import { NextResponse } from 'next/server';

export default function MyPage() {
  const response = new NextResponse('Hello from client!'); // Incorrect - NextResponse is server-side only
  return <div>My Page {response.body}</div>;
}
```

**Correct Code (Solution):**

The solution involves separating server-side logic (using `next/server`) from client-side rendering.  We'll use Middleware for the server-side logic and a regular component for client-side display.

**Step 1: Create a Middleware function:**

```javascript
// middleware.js
import { NextResponse } from 'next/server';

export function middleware(req) {
  const url = req.nextUrl.clone();
  url.pathname = '/api/data'; // Redirect to an API route

  return NextResponse.rewrite(url);
}

export const config = {
  matcher: ['/my-page'], // Apply this middleware only to /my-page
};
```

**Step 2: Create an API Route to handle the logic:**

```javascript
// pages/api/data.js
export default function handler(req, res) {
  res.status(200).json({ message: 'Hello from server!' });
}
```

**Step 3: Update the Client-Side Component:**

```javascript
// pages/my-page.js
import useSWR from 'swr';

export default function MyPage() {
  const { data, error } = useSWR('/api/data');

  if (error) return <div>failed to load</div>;
  if (!data) return <div>loading...</div>;

  return <div>My Page: {data.message}</div>;
}
```


**Explanation:**

* **Middleware:** We moved the `NextResponse` usage to `middleware.js`. This ensures it only runs on the server. The middleware redirects requests to `/my-page` to the API route `/api/data`.
* **API Route:**  The API route handles the server-side logic and returns data in a format that the client can understand (JSON).
* **Client-side Component:** The `MyPage` component now uses `useSWR` (you might need to install it: `npm install swr`) to fetch data from the API route. This keeps the client-side logic clean and focused on rendering the data.  This avoids the `next/server` import error entirely.

**External References:**

* [Next.js Middleware Documentation](https://nextjs.org/docs/app/building-your-application/routing/middleware)
* [Next.js API Routes Documentation](https://nextjs.org/docs/api-routes/introduction)
* [SWR Documentation](https://swr.vercel.app/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

