# 🐞 CSS Challenge: Responsive Navigation Bar with Tailwind CSS


This challenge focuses on creating a responsive navigation bar using Tailwind CSS.  The navigation bar should be fixed at the top of the viewport, collapse into a hamburger menu on smaller screens, and have smooth transitions.  We'll use Tailwind's utility classes to style the navigation bar efficiently.


## Styling Description

The navigation bar will have a dark background and light text.  The logo will be on the left, and the navigation links will be on the right. On smaller screens (below 768px), the navigation links will be hidden by default and revealed when the hamburger menu is clicked. The transition between states should be smooth.


## Full Code

```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Responsive Navigation Bar</title>
  <script src="https://cdn.tailwindcss.com"></script>
</head>
<body class="bg-gray-100">

  <nav class="bg-gray-800 text-white p-4 fixed w-full top-0 z-10">
    <div class="container mx-auto flex justify-between items-center">
      <a href="#" class="text-xl font-bold">My Logo</a>

      <div class="md:flex items-center hidden">
        <a href="#" class="mx-4 hover:underline">Home</a>
        <a href="#" class="mx-4 hover:underline">About</a>
        <a href="#" class="mx-4 hover:underline">Services</a>
        <a href="#" class="mx-4 hover:underline">Contact</a>
      </div>

      <button class="md:hidden block p-2 rounded-md bg-gray-700 hover:bg-gray-600">
        <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16"/>
        </svg>
      </button>
    </div>
  </nav>

  <div class="mt-20">
      <!--Main Content Here-->
  </div>

</body>
</html>
```


## Explanation

* **`bg-gray-800 text-white p-4 fixed w-full top-0 z-10`**: This sets the background color, text color, padding, positioning (fixed to the top), full width, and z-index for the navigation bar.  `z-10` ensures it appears above other content.
* **`container mx-auto flex justify-between items-center`**: This uses Tailwind's container utility for responsive sizing, flexbox for layout, and aligns items to the center.
* **`md:flex items-center hidden`**: This uses a responsive modifier (`md:` applies to medium screens and larger).  The links are hidden on smaller screens and displayed on medium screens and above.
* **`md:hidden block`**: The hamburger menu button is visible only on smaller screens (below medium).
* **`hover:underline`**: This adds an underline on hover to the links.

## Resources to Learn More

* **Tailwind CSS Documentation:** [https://tailwindcss.com/docs](https://tailwindcss.com/docs)
* **MDN Web Docs (for CSS and HTML fundamentals):** [https://developer.mozilla.org/en-US/docs/Web/CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) and [https://developer.mozilla.org/en-US/docs/Web/HTML](https://developer.mozilla.org/en-US/docs/Web/HTML)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

