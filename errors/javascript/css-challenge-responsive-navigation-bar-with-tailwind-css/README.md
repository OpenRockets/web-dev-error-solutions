# 🐞 CSS Challenge: Responsive Navigation Bar with Tailwind CSS


This challenge focuses on creating a responsive navigation bar using Tailwind CSS.  The navigation bar will adapt smoothly to different screen sizes, displaying a hamburger menu on smaller screens and a horizontal menu on larger screens.  We'll incorporate hover effects and subtle animations for an enhanced user experience.


## Styling Description

The navigation bar will have a dark background with light text.  Navigation links will be spaced evenly. On smaller screens, the hamburger menu icon will be visible. Clicking it will toggle the visibility of the navigation links. On larger screens, the navigation links will be displayed horizontally. Hovering over navigation links will slightly change their background color.


## Full Code

```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <script src="https://cdn.tailwindcss.com"></script>
  <title>Responsive Navigation Bar</title>
</head>
<body class="bg-gray-900">

  <nav class="bg-gray-800">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="flex items-center justify-between h-16">
        <div class="flex items-center">
          <a href="#" class="text-white font-bold text-xl">My Website</a>
        </div>
        <div class="hidden md:block">
          <div class="flex space-x-8">
            <a href="#" class="text-gray-300 hover:bg-gray-700 hover:text-white px-3 py-2 rounded-md text-sm font-medium">Home</a>
            <a href="#" class="text-gray-300 hover:bg-gray-700 hover:text-white px-3 py-2 rounded-md text-sm font-medium">About</a>
            <a href="#" class="text-gray-300 hover:bg-gray-700 hover:text-white px-3 py-2 rounded-md text-sm font-medium">Services</a>
            <a href="#" class="text-gray-300 hover:bg-gray-700 hover:text-white px-3 py-2 rounded-md text-sm font-medium">Contact</a>
          </div>
        </div>
        <div class="md:hidden">
          <!-- Mobile menu button -->
          <button class="inline-flex items-center justify-center p-2 rounded-md text-gray-400 hover:text-white hover:bg-gray-700 focus:outline-none focus:ring-2 focus:ring-inset focus:ring-white">
            <svg class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16" />
            </svg>
          </button>
        </div>
      </div>
    </div>
    <!-- Mobile menu -->
    <div class="md:hidden">
      <div class="px-2 pt-2 pb-3 space-y-1 sm:px-3">
          <a href="#" class="block px-3 py-2 rounded-md text-base font-medium text-gray-300 hover:bg-gray-700 hover:text-white">Home</a>
          <a href="#" class="block px-3 py-2 rounded-md text-base font-medium text-gray-300 hover:bg-gray-700 hover:text-white">About</a>
          <a href="#" class="block px-3 py-2 rounded-md text-base font-medium text-gray-300 hover:bg-gray-700 hover:text-white">Services</a>
          <a href="#" class="block px-3 py-2 rounded-md text-base font-medium text-gray-300 hover:bg-gray-700 hover:text-white">Contact</a>
      </div>
    </div>
  </nav>

</body>
</html>

```


## Explanation

This code utilizes Tailwind CSS classes for styling.  The `md:hidden` and `hidden md:block` classes control the visibility of elements based on screen size.  The hamburger menu icon is a simple SVG.  JavaScript would be needed to add functionality to the hamburger button to toggle the mobile menu's visibility (This is omitted for brevity).  The hover effects are implemented using Tailwind's hover modifiers. The layout utilizes Tailwind's flexbox utilities for easy responsive design.


## Resources to Learn More

* **Tailwind CSS Documentation:** [https://tailwindcss.com/docs](https://tailwindcss.com/docs)
* **Learn CSS Grid:** [https://css-tricks.com/snippets/css/complete-guide-grid/](https://css-tricks.com/snippets/css/complete-guide-grid/) (While not directly used here, understanding grid is beneficial for layout)
* **Understanding Responsive Design:** [https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Responsive_Design](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Responsive_Design)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

