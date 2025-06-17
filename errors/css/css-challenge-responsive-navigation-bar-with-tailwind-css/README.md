# 🐞 CSS Challenge: Responsive Navigation Bar with Tailwind CSS


This challenge focuses on creating a responsive navigation bar using Tailwind CSS.  The navigation bar should adapt seamlessly to different screen sizes, collapsing into a hamburger menu on smaller screens. We'll achieve this using Tailwind's responsive modifiers and utility classes.


**Description of the Styling:**

The navigation bar will contain a logo on the left and a list of navigation links on the right. On larger screens (e.g., desktops), the logo and links will be displayed inline.  On smaller screens (e.g., mobile), the links will be hidden by default and revealed when the hamburger menu is toggled.  The styling will employ a clean and modern aesthetic, using Tailwind's pre-defined colors and spacing.

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

  <nav class="bg-white shadow-md">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="flex items-center justify-between h-16">
        <div class="flex items-center">
          <a href="#" class="flex-shrink-0">
            <img class="h-8 w-8" src="logo.svg" alt="Logo">
          </a>
          <div class="hidden md:block">
            <div class="ml-10 flex space-x-4">
              <a href="#" class="text-gray-700 hover:text-gray-900">Home</a>
              <a href="#" class="text-gray-700 hover:text-gray-900">About</a>
              <a href="#" class="text-gray-700 hover:text-gray-900">Services</a>
              <a href="#" class="text-gray-700 hover:text-gray-900">Contact</a>
            </div>
          </div>
        </div>
        <div class="hidden md:block">
          <a href="#" class="text-gray-700 hover:text-gray-900">Login</a>
        </div>
        <div class="-mr-2 flex md:hidden">
          <!-- Mobile menu button -->
          <button class="inline-flex items-center justify-center p-2 rounded-md text-gray-400 hover:text-gray-500 hover:bg-gray-100 focus:outline-none focus:ring-2 focus:ring-inset focus:ring-indigo-500">
            <svg class="block h-6 w-6" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor" aria-hidden="true">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16" />
            </svg>
          </button>
        </div>
      </div>
    </div>

    <!-- Mobile menu, show/hide based on menu state. -->
    <div class="md:hidden">
      <div class="px-2 pt-2 pb-3 space-y-1">
        <a href="#" class="bg-gray-200 text-gray-700 block px-3 py-2 rounded-md text-base font-medium">Home</a>
        <a href="#" class="bg-gray-200 text-gray-700 block px-3 py-2 rounded-md text-base font-medium">About</a>
        <a href="#" class="bg-gray-200 text-gray-700 block px-3 py-2 rounded-md text-base font-medium">Services</a>
        <a href="#" class="bg-gray-200 text-gray-700 block px-3 py-2 rounded-md text-base font-medium">Contact</a>
      </div>
    </div>
  </nav>

</body>
</html>
```

**Remember to replace `"logo.svg"` with the actual path to your logo.**  This code requires the Tailwind CSS CDN.

**Explanation:**

* **`max-w-7xl mx-auto px-4 sm:px-6 lg:px-8`**: This controls the maximum width and padding of the navigation bar, adapting to different screen sizes.
* **`hidden md:block`**: This hides elements on screens smaller than `md` (medium) and shows them on `md` and larger.
* **`-mr-2 flex md:hidden`**: This positions the hamburger menu button and hides it on larger screens.
* **The SVG:** This is the hamburger menu icon.


**Links to Resources to Learn More:**

* **Tailwind CSS Documentation:** [https://tailwindcss.com/docs/](https://tailwindcss.com/docs/)
* **Tailwind CSS Cheat Sheet:** [https://tailwindcss.com/docs/](https://tailwindcss.com/docs/)  (Look for their cheat sheet, often linked within the docs)
* **Learn CSS Grid:**  While not directly used here, understanding CSS Grid can help with more complex layouts.  Many tutorials are available online via search engines.


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

