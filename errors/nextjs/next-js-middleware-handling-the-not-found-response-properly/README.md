# 🐞 Next.js Middleware: Handling the `not-found` Response Properly


## Description of the Error

A common issue in Next.js Middleware is incorrectly handling the `not-found` response.  Middleware functions can redirect or rewrite requests, but if you don't handle a 404 (Not Found) scenario explicitly, your users might see a generic error page instead of a custom 404 page you designed.  This is particularly problematic if your middleware is attempting to rewrite URLs based on conditions which might not always be met.  If the condition fails, the middleware will implicitly pass through, possibly leading to a 404 if the resulting URL doesn't exist.


## Step-by-Step Code Fix

Let's imagine we have middleware that attempts to redirect `/blog/:slug` URLs to a specific CMS-based URL. If the slug doesn't exist in the CMS, we should return a 404 instead of a generic error.

**Incorrect Middleware (Will lead to a generic 404):**

```javascript
// middleware.js
import { NextResponse } from 'next/server'

export function middleware(req) {
  const slug = req.nextUrl.pathname.replace('/blog/', '');

  // Simulate fetching data from a CMS - this could fail
  const blogPost = fetchBlogPost(slug);  // Assume this function sometimes returns null

  if (blogPost) {
    return NextResponse.rewrite(new URL(`/blog-post/${blogPost.id}`, req.url))
  }
  // Missing 404 handling here!
}

export const config = {
  matcher: '/blog/:slug*'
}


//Helper function - simulating an API call that might fail
const fetchBlogPost = async (slug) => {
  // Simulate a failed API call 
  if(slug === 'nonexistent-post') return null;
  return {id: slug} //Simulate successful fetch
}
```

**Corrected Middleware (Handles 404):**

```javascript
// middleware.js
import { NextResponse } from 'next/server'

export async function middleware(req) {
  const slug = req.nextUrl.pathname.replace('/blog/', '');

  const blogPost = await fetchBlogPost(slug);

  if (blogPost) {
    return NextResponse.rewrite(new URL(`/blog-post/${blogPost.id}`, req.url));
  } else {
    return new NextResponse(null, { status: 404 });
  }
}

export const config = {
  matcher: '/blog/:slug*'
};


//Helper function - simulating an API call that might fail
const fetchBlogPost = async (slug) => {
  // Simulate a failed API call 
  if(slug === 'nonexistent-post') return null;
  await new Promise(resolve => setTimeout(resolve, 500));//Simulate API call delay
  return {id: slug} //Simulate successful fetch
}
```

This corrected version explicitly returns a `NextResponse` with a `status` of 404 when `fetchBlogPost` returns `null`, ensuring a proper 404 response is sent.


## Explanation

The crucial change is adding an `else` block to explicitly handle the case where `blogPost` is null (or undefined, depending on your `fetchBlogPost` implementation).  Without this explicit handling, the middleware silently passes through, and Next.js attempts to handle the request, likely resulting in a generic 404 error.  By returning a `NextResponse` with a `404` status code, you ensure that Next.js knows to serve your custom 404 page (if you have one configured), providing a much better user experience.  Using `async/await` ensures proper handling of asynchronous API calls.


## External References

* **Next.js Middleware Documentation:** [https://nextjs.org/docs/app/building-your-application/routing/middleware](https://nextjs.org/docs/app/building-your-application/routing/middleware)
* **NextResponse API:** [https://nextjs.org/docs/api-reference/next/server#nextresponse](https://nextjs.org/docs/api-reference/next/server#nextresponse)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

