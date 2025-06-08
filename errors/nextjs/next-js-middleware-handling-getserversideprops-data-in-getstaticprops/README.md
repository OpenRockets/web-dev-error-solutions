# 🐞 Next.js Middleware: Handling `getServerSideProps` Data in `getStaticProps`


## Description of the Error

A common issue arises when attempting to use data fetched within `getServerSideProps` (or `getStaticProps` with `revalidate`) within a component that also utilizes `getStaticProps`.  The problem stems from the fact that `getStaticProps` runs at build time (or during revalidation) and doesn't have access to the request-specific data retrieved by `getServerSideProps` (which runs on every request).  Trying to access such data directly will result in undefined values or runtime errors when pre-rendering the page.


## Code Example: The Problem

Let's imagine a scenario where we fetch user data based on a session ID, which we want to display on a user profile page.

**pages/profile.js:**

```javascript
import { getServerSideProps } from 'next/server';
import { getSession } from 'next-auth/react';

export async function getServerSideProps(context) {
  const session = await getSession(context);

  if (!session) {
    return {
      redirect: {
        destination: '/login',
        permanent: false,
      },
    };
  }

  const res = await fetch(`https://api.example.com/user/${session.user.id}`);
  const userData = await res.json();

  return {
    props: { userData },
  };
}

export default function Profile({ userData }) {
  return (
    <div>
      <h1>Profile</h1>
      <p>Name: {userData.name}</p>  {/* This might be undefined at build time */}
      <p>Email: {userData.email}</p> {/* This might be undefined at build time */}
    </div>
  );
}
```

This code works perfectly for server-side rendering, but will throw errors if used for static site generation (SSG) because `userData` will be undefined during the build process.


## Fixing the Issue Step-by-Step

To resolve this, we need to separate the data fetching into a function accessible by both `getServerSideProps` and the component.

**pages/profile.js (Fixed):**

```javascript
import { getServerSideProps } from 'next/server';
import { getSession } from 'next-auth/react';

async function fetchUserData(session) {
  if (!session) {
    return null;
  }
  const res = await fetch(`https://api.example.com/user/${session.user.id}`);
  return res.json();
}


export async function getServerSideProps(context) {
  const session = await getSession(context);
  const userData = await fetchUserData(session);

  if (!userData) {
      return {
        redirect: {
          destination: '/login',
          permanent: false,
        },
      };
  }

  return {
    props: { userData },
  };
}

export default function Profile({ userData }) {
  // Fallback to prevent errors during build time
  if (!userData) return <div>Loading...</div>;

  return (
    <div>
      <h1>Profile</h1>
      <p>Name: {userData.name}</p>
      <p>Email: {userData.email}</p>
    </div>
  );
}
```

**Explanation:**

1. **`fetchUserData` function:** This function encapsulates the API call, making it reusable.
2. **`getServerSideProps`:**  This function calls `fetchUserData` after getting the session.  It handles redirection if no session exists.
3. **Conditional Rendering:** The component now includes a fallback (`<div>Loading...</div>`) to handle the case where `userData` is initially undefined during build time or revalidation.  Once the data is fetched on the server, the actual profile data will be displayed.

This approach ensures that the data is fetched correctly during server-side rendering, while also preventing errors during the build process.



## External References

* [Next.js Official Documentation on `getServerSideProps`](https://nextjs.org/docs/basic-features/data-fetching/getserversideprops)
* [Next.js Official Documentation on `getStaticProps`](https://nextjs.org/docs/basic-features/data-fetching/getstaticprops)
* [NextAuth.js Documentation](https://next-auth.js.org/) (for authentication example)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

