# 🐞 Next.js Middleware: Handling `Not Found` Errors for Dynamic Routes


This document addresses a common issue developers encounter when using Next.js Middleware with dynamic routes:  handling `404 Not Found` errors gracefully.  Middleware runs before a request reaches your page, and if it throws an error, it can be difficult to prevent a full application crash and instead return a proper 404 page.

**Description of the Error:**

When using middleware with dynamic routes (e.g., `/blog/[slug]`),  if the middleware attempts to access a resource that doesn't exist (e.g., a blog post with an invalid `slug`), it might throw an error, leading to a server-side error (500) instead of the expected 404.  This leaves the user with a generic error page instead of a more user-friendly "Not Found" experience.

**Step-by-Step Code Fix:**

Let's assume you have a middleware file at `middleware.js` that fetches blog post data based on the `slug`:

**Incorrect Middleware (`middleware.js`):**

```javascript
import { NextResponse } from 'next/server'

export function middleware(req) {
  const slug = req.nextUrl.pathname.split('/blog/')[1]
  const post = getPostData(slug); // Function to fetch post data; may throw if post not found

  if (!post) {
    return NextResponse.redirect(new URL('/404', req.url)) // THIS WON'T WORK AS EXPECTED IN ALL CASES
  }

  // ... rest of your middleware logic ...
}

export const config = {
  matcher: '/blog/:slug'
}
```

The issue here is that `getPostData(slug)` might throw an error if the post doesn't exist, and the `if (!post)` check will not catch those exceptions.

**Correct Middleware (`middleware.js`):**

```javascript
import { NextResponse } from 'next/server'

export async function middleware(req) {
  const slug = req.nextUrl.pathname.split('/blog/')[1]

  try {
    const post = await getPostData(slug); // Function to fetch post data

    if (!post) {
      return NextResponse.rewrite(new URL('/404', req.url));
    }

    // ... rest of your middleware logic ...
  } catch (error) {
    // Handle errors gracefully, e.g., log the error and return a 404
    console.error("Error fetching post:", error);
    return NextResponse.rewrite(new URL('/404', req.url));
  }
}

export const config = {
  matcher: '/blog/:slug'
}

// Example getPostData function (replace with your actual implementation)
async function getPostData(slug) {
  // Simulate fetching data; replace with your database or API call
  const posts = {
    "my-first-post": { title: "My First Post" },
    "my-second-post": { title: "My Second Post" },
  };
  return posts[slug] || null;
}
```


**Explanation:**

The corrected middleware uses a `try...catch` block to handle potential errors during the `getPostData` call. If an error occurs (e.g., a database error or a network issue), the `catch` block executes, logs the error for debugging, and returns a `NextResponse.rewrite` to the `/404` page.  Using `rewrite` instead of `redirect` ensures the middleware continues to process the request and allows potentially other middleware or page specific logic to operate. If the post is not found (`!post`), we also handle this with a `rewrite`.


**External References:**

* [Next.js Middleware documentation](https://nextjs.org/docs/app/building-your-application/routing/middleware)
* [Next.js Error Handling](https://nextjs.org/docs/app/building-your-application/handling-errors)
* [NextResponse API](https://nextjs.org/docs/api-reference/next/server#nextresponse)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

