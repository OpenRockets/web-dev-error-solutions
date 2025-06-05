# 🐞 Next.js Middleware: Handling `unstable_revalidate` and Cache Invalidation


## Description of the Error

A common issue when using Next.js Middleware with `unstable_revalidate` is inconsistent cache invalidation.  You might expect a page to update immediately after a change to its data source, but it continues to serve the cached version.  This often happens because the `unstable_revalidate` value doesn't precisely control when the cache is revalidated, especially when dealing with dynamic content or data fetching complexities.  The page might appear to update eventually (after a period defined by `unstable_revalidate`), but the delay can be frustrating and lead to users seeing stale data.

## Step-by-Step Code Fix

Let's assume we have a blog post page that fetches data from a headless CMS. The `unstable_revalidate` is set to 10 seconds, but the cache is not invalidated consistently.

**Problem Code (Illustrative):**

```javascript
// pages/posts/[slug].js
import { getPosts } from '../../lib/data';

export async function getStaticProps({ params }) {
  const post = getPosts().find((post) => post.slug === params.slug);
  return {
    props: { post },
    revalidate: 10, // Incorrect use in getStaticProps
  };
}

export default function Post({ post }) {
  return (
    <div>
      <h1>{post.title}</h1>
      <p>{post.content}</p>
    </div>
  );
}
```

```javascript
// middleware.js
import { NextResponse } from 'next/server'

export function middleware(req) {
  // This middleware does NOT reliably invalidate the cache
  // because it's unrelated to the data source.
  return NextResponse.next()
}
```

**Corrected Code:**

This solution uses middleware to handle the caching invalidation, correctly employing the `cache` API to bust the cache. This will work better in conjunction with a correctly handled revalidate in `getStaticProps` (if using it).

```javascript
// pages/posts/[slug].js
import { getPosts } from '../../lib/data';

export async function getStaticProps({ params }) {
  const post = getPosts().find((post) => post.slug === params.slug);
  return {
    props: { post },
    revalidate: 10, // Correct use in getStaticProps.  It's still preferable to handle invalidation via middleware.
  };
}

export default function Post({ post }) {
  return (
    <div>
      <h1>{post.title}</h1>
      <p>{post.content}</p>
    </div>
  );
}
```

```javascript
// middleware.js
import { NextResponse } from 'next/server'

export async function middleware(req) {
  // Use middleware only if a data source changes that necessitates cache invalidation
  const url = req.nextUrl.clone()
  const slug = req.page.params?.slug

  // Check for conditions that require cache invalidation - example check
  if (slug && await checkIfPostUpdated(slug)) {
      //Cache will not be revalidated until the next request
      //Cache will be cleared on the next request.
      url.headers.set('Cache-Control', 's-maxage=0, stale-while-revalidate=0')
  }

  return NextResponse.rewrite(url)
}

//Helper function to check if a post was updated (example)
async function checkIfPostUpdated(slug){
  // This is a placeholder - replace with your actual logic to check if post was recently updated
  // example interaction with a CMS API endpoint.
    const res = await fetch(`https://your-cms.com/api/posts/${slug}`);
    const data = await res.json();
    //Check if the last updated time is recent, etc.
    return data.lastUpdated > new Date(Date.now() - 10000); // updated in last 10 seconds.
}

```


## Explanation

The original code relied solely on `revalidate` in `getStaticProps`. While this helps, it's not a guaranteed immediate update. The improved solution utilizes Next.js Middleware with `Cache-Control` header manipulation.  The `checkIfPostUpdated` function (placeholder) is crucial; it determines if the data has changed and triggers cache invalidation only when necessary.  This is more efficient and reliable than always invalidating the cache, regardless of whether the data has changed.  The middleware intercepts requests and applies the appropriate `Cache-Control` headers, ensuring the cache is invalidated on the next request when data changes.



## External References

* [Next.js Middleware Documentation](https://nextjs.org/docs/app/building-your-application/routing/middleware)
* [Next.js `Cache-Control` Header](https://nextjs.org/docs/app/building-your-application/routing/caching)
* [Understanding Cache Invalidation](https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/caching)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

