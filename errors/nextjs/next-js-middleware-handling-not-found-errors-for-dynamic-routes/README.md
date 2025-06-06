# 🐞 Next.js Middleware: Handling `Not Found` Errors for Dynamic Routes


This document addresses a common problem encountered when using Next.js Middleware with dynamic routes:  correctly handling 404 (Not Found) errors.  Improperly configured middleware can inadvertently return a 404 for valid routes, leading to a broken user experience.

**Description of the Error:**

When using middleware with dynamic segments in your routes (e.g., `/blog/[slug]`), you might encounter a `Not Found` error even if the requested page exists. This usually happens when the middleware's logic doesn't correctly handle cases where the dynamic segment doesn't match any existing data.  The middleware might prematurely respond with a 404 before the actual page rendering logic has a chance to verify the existence of the resource.


**Code Example: Incorrect Middleware**

This example demonstrates middleware that incorrectly handles a dynamic route, resulting in a `Not Found` error for valid slugs:

```javascript
// pages/api/middleware.js
export function middleware(req) {
  const slug = req.query.slug;
  // Incorrect:  We don't check if a page with this slug exists before setting the response
  if (!slug) {
    return NextResponse.rewrite(new URL('/404', req.url))
  }
    // ...other middleware logic...
}


export const config = {
  matcher: ['/blog/:slug*'],
}

// pages/blog/[slug].js
import { useRouter } from 'next/router'
export default function BlogPost(){
  const router = useRouter()
  const {slug} = router.query
  return(
    <h1>This is blog post {slug}</h1>
  )
}
```

**Step-by-step Fix:**

1. **Conditional Redirects/Rewrites:**  Instead of immediately rewriting to a 404 page, check if the resource exists *before* responding. This usually involves querying a database or file system.

2. **Data Fetching:** Fetch data related to the dynamic segment (e.g., blog post data for `/blog/[slug]`).  Only if the data fetch is successful should you proceed.  If the fetch fails, then you can return a 404.

3. **Error Handling:**  Implement robust error handling to catch potential issues during data fetching.


**Corrected Code:**

```javascript
// pages/api/middleware.js
import { NextResponse } from 'next/server'

export async function middleware(req) {
  const slug = req.query.slug;

  if (!slug) {
    return NextResponse.rewrite(new URL('/404', req.url))
  }

  try {
    // Simulate fetching blog post data; replace with your actual data fetching logic.
    const blogPost = await fetch(`https://api.example.com/blog/${slug}`);

    if (!blogPost.ok) {
      return NextResponse.rewrite(new URL('/404', req.url));
    }

    // ...other middleware logic...

  } catch (error) {
    console.error("Error fetching blog post:", error);
    return NextResponse.rewrite(new URL('/404', req.url));
  }
}

export const config = {
  matcher: ['/blog/:slug*'],
}


// pages/blog/[slug].js
import { useRouter } from 'next/router'
export default function BlogPost(){
  const router = useRouter()
  const {slug} = router.query
  return(
    <h1>This is blog post {slug}</h1>
  )
}
```


**Explanation:**

The corrected middleware now attempts to fetch data for the given `slug`. If the fetch request fails (e.g., due to a network error or the blog post not existing), or the API returns a non-200 status code, a 404 response is returned.  Otherwise, the middleware continues to process the request.  This ensures that a 404 is only returned when a blog post genuinely does not exist.


**External References:**

* [Next.js Middleware Documentation](https://nextjs.org/docs/app/building-your-application/routing/middleware)
* [Next.js API Routes Documentation](https://nextjs.org/docs/api-routes/introduction)
* [Next.js Error Handling](https://nextjs.org/docs/app/building-your-application/handling-errors)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

