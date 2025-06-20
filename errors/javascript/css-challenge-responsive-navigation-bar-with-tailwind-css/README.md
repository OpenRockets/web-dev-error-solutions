# 🐞 CSS Challenge: Responsive Navigation Bar with Tailwind CSS


This challenge focuses on creating a responsive navigation bar using Tailwind CSS.  The navigation bar should adapt smoothly to different screen sizes, collapsing into a hamburger menu on smaller screens.  We'll use Tailwind's pre-built utility classes for efficient styling and responsive design.


**Description of the Styling:**

The navigation bar will contain a logo on the left and a list of navigation links on the right.  On larger screens (e.g., desktops), the logo and links will be displayed inline.  On smaller screens (e.g., mobile phones), the navigation links will collapse behind a hamburger menu icon, revealed on click.  We'll use Tailwind's `flex` and `responsive` utilities to achieve this.


**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <script src="https://cdn.tailwindcss.com"></script>
  <title>Responsive Navigation Bar</title>
</head>
<body class="bg-gray-100">

  <nav class="bg-white shadow-lg">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="flex items-center justify-between h-16">
        <div class="flex items-center">
          <a href="#" class="flex-shrink-0">
            <img class="h-8 w-auto" src="logo.png" alt="Logo">
          </a>
        </div>
        <div class="flex items-center">
          <div class="hidden md:block">
            <div class="ml-10 flex items-baseline space-x-4">
              <a href="#" class="text-gray-700 hover:text-gray-900 font-medium">Home</a>
              <a href="#" class="text-gray-700 hover:text-gray-900 font-medium">About</a>
              <a href="#" class="text-gray-700 hover:text-gray-900 font-medium">Services</a>
              <a href="#" class="text-gray-700 hover:text-gray-900 font-medium">Contact</a>
            </div>
          </div>
          <div class="-mr-2 flex md:hidden">
            <!-- Mobile menu button -->
            <button class="bg-gray-800 inline-flex items-center justify-center p-2 rounded-md text-gray-400 hover:text-white hover:bg-gray-700 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-offset-gray-800 focus:ring-white">
              <svg class="block h-6 w-6" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor" aria-hidden="true">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16" />
              </svg>
              <!-- Menu open: "hidden", Menu closed: "block" -->
            </button>
          </div>
        </div>
      </div>
    </div>

    <!-- Mobile menu, show/hide based on menu state. -->
    <div class="md:hidden">
      <div class="px-2 pt-2 pb-3 space-y-1 sm:px-3">
        <a href="#" class="block px-3 py-2 rounded-md text-base font-medium text-gray-700 hover:text-gray-900 hover:bg-gray-50">Home</a>
        <a href="#" class="block px-3 py-2 rounded-md text-base font-medium text-gray-700 hover:text-gray-900 hover:bg-gray-50">About</a>
        <a href="#" class="block px-3 py-2 rounded-md text-base font-medium text-gray-700 hover:text-gray-900 hover:bg-gray-50">Services</a>
        <a href="#" class="block px-3 py-2 rounded-md text-base font-medium text-gray-700 hover:text-gray-900 hover:bg-gray-50">Contact</a>
      </div>
    </div>
  </nav>

</body>
</html>
```

Remember to replace `"logo.png"` with the actual path to your logo image.  This code uses a simple SVG for the hamburger icon; you can replace it with a more elaborate image or icon font if desired.  Adding JavaScript would improve the functionality of the hamburger menu, but this example focuses on the CSS structure.

**Explanation:**

*   Tailwind's `flex` utility makes it easy to arrange elements horizontally and vertically.
*   `md:hidden` and `hidden md:block` control the visibility of elements based on screen size (using Tailwind's responsive modifiers).
*   The classes like `bg-white`, `shadow-lg`, `text-gray-700` provide pre-defined styles from Tailwind's styling library.
*   The mobile menu is hidden by default (`md:hidden`) and appears on smaller screens.


**Links to Resources to Learn More:**

*   **Tailwind CSS Documentation:** [https://tailwindcss.com/docs](https://tailwindcss.com/docs)
*   **Tailwind CSS Cheat Sheet:** [https://tailwindcss.com/docs/cheat-sheet](https://tailwindcss.com/docs/cheat-sheet) (or search for one online)
*   **Learn CSS Flexbox:**  Search for "CSS Flexbox tutorial" on your preferred learning platform (e.g., MDN Web Docs, freeCodeCamp)

Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

