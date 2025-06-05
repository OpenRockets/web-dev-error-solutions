# 🐞 Handling `getServerSideProps` Data Fetching Errors in Next.js


This document addresses a common problem encountered when using `getServerSideProps` in Next.js applications: gracefully handling errors during data fetching.  Failing to handle these errors can lead to a poor user experience, displaying cryptic error messages or causing the application to crash.

**Description of the Error:**

When using `getServerSideProps` to fetch data from an external API or database, network issues or server-side errors can occur.  If these errors are not caught and handled, Next.js will typically render a blank page or display a generic error message, which is unhelpful for the user.  The application might also crash, depending on the nature of the error.

**Code Example (Problem):**

```javascript
// pages/index.js

import { useRouter } from 'next/router';

export async function getServerSideProps(context) {
  try {
    const res = await fetch('https://api.example.com/data');
    if (!res.ok) {
      throw new Error(`Error! status: ${res.status}`);
    }
    const data = await res.json();
    return {
      props: { data },
    };
  } catch (error) {
    console.error('Error fetching data:', error); // This is logged on the server, but not handled on the client
    return {
      props: { data: null }, // Doesn't provide useful information to the client
    };
  }
}

export default function Home({ data }) {
  const router = useRouter();

  if (router.isFallback) {
    return <div>Loading...</div>; //This only handles the initial loading state
  }

  if (!data) {
    return <div>Error loading data</div>; //Generic error message
  }

  return (
    <div>
      <h1>My Page</h1>
      <pre>{JSON.stringify(data, null, 2)}</pre>
    </div>
  );
}
```

**Code Example (Solution):**


```javascript
// pages/index.js
import { useRouter } from 'next/router';

export async function getServerSideProps(context) {
  try {
    const res = await fetch('https://api.example.com/data');
    if (!res.ok) {
      //throw new Error(`Error! status: ${res.status}`); //remove this
      return {
        props: {
          error: {
            status: res.status,
            message: `Error fetching data: ${res.status}`
          },
          data: null,
        },
      };
    }
    const data = await res.json();
    return {
      props: { data },
    };
  } catch (error) {
    console.error('Error fetching data:', error);
    return {
      props: {
        error: {
          status: 500,
          message: 'An unexpected error occurred.' //more user-friendly message
        },
        data: null,
      },
    };
  }
}

export default function Home({ data, error }) {
  const router = useRouter();

  if (router.isFallback) {
    return <div>Loading...</div>;
  }

  if (error) {
    return (
      <div>
        <h1>Error</h1>
        <p>Status: {error.status}</p>
        <p>{error.message}</p>
      </div>
    );
  }

  if (!data) { //This is redundant now, since error handling is better. Consider removing it for cleaner code.
    return <div>Error loading data</div>;
  }

  return (
    <div>
      <h1>My Page</h1>
      <pre>{JSON.stringify(data, null, 2)}</pre>
    </div>
  );
}

```

**Explanation:**

The improved code handles errors more gracefully.  Instead of simply logging the error on the server or returning a generic error message, it now:

1. **Returns a structured error object:**  `getServerSideProps` now returns an `error` object containing a status code and a user-friendly message. This provides more context to the client-side rendering.

2. **Displays a more informative error message:** The client-side component checks for the presence of the `error` object and displays a more helpful error message, including the status code.

3. **Improved User Experience:** A more informative error page improves user experience. The user is more likely to understand the issue and to know what to do next.


**External References:**

* [Next.js Official Documentation on `getServerSideProps`](https://nextjs.org/docs/basic-features/data-fetching/getserversideprops)
* [Next.js Error Handling](https://nextjs.org/docs/app/building-your-application/routing/error-handling) (Relevant for app router; similar principles apply to pages router)

**Copyright (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.**

