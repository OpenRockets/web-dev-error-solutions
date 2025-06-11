# 🐞 CSS Challenge: Responsive Navigation Bar with Tailwind CSS


This challenge focuses on creating a responsive navigation bar using Tailwind CSS. The navigation bar should adapt seamlessly to different screen sizes, transitioning from a horizontal menu on larger screens to a hamburger menu on smaller screens.  We'll leverage Tailwind's utility classes for efficient and rapid styling.


**Description of the Styling:**

The navigation bar will contain a logo on the left, a list of navigation links in the center, and a hamburger menu icon on the right (visible only on smaller screens).  On larger screens, the navigation links will be displayed horizontally.  On smaller screens, clicking the hamburger icon will toggle the visibility of the navigation links.  We'll use Tailwind's responsive modifiers to achieve this responsiveness.  The styling will be clean and modern, using a dark theme for contrast.


**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Responsive Navigation Bar</title>
  <link href="https://cdn.jsdelivr.net/npm/tailwindcss@2.2.19/dist/tailwind.min.css" rel="stylesheet">
  <script src="https://cdn.tailwindcss.com"></script>

</head>
<body class="bg-gray-900 text-white">

  <nav class="bg-gray-800 p-4 flex justify-between items-center">
    <div class="text-xl font-bold">My Logo</div>

    <div class="md:flex hidden space-x-6">
      <a href="#" class="hover:text-gray-300">Home</a>
      <a href="#" class="hover:text-gray-300">About</a>
      <a href="#" class="hover:text-gray-300">Services</a>
      <a href="#" class="hover:text-gray-300">Contact</a>
    </div>


    <button id="menu-btn" class="md:hidden focus:outline-none">
      <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 text-white" fill="none" viewBox="0 0 24 24" stroke="currentColor">
        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16" />
      </svg>
    </button>

  </nav>

  <div id="mobile-menu" class="md:hidden absolute top-12 bg-gray-800 w-full">
    <ul class="py-4">
      <li><a href="#" class="block px-4 py-2 hover:bg-gray-700">Home</a></li>
      <li><a href="#" class="block px-4 py-2 hover:bg-gray-700">About</a></li>
      <li><a href="#" class="block px-4 py-2 hover:bg-gray-700">Services</a></li>
      <li><a href="#" class="block px-4 py-2 hover:bg-gray-700">Contact</a></li>
    </ul>
  </div>


  <script>
    const menuBtn = document.getElementById('menu-btn');
    const mobileMenu = document.getElementById('mobile-menu');

    menuBtn.addEventListener('click', () => {
      mobileMenu.classList.toggle('hidden');
    });
  </script>

</body>
</html>
```


**Explanation:**

* **Tailwind Classes:** The code extensively uses Tailwind CSS classes like `bg-gray-900`, `text-white`, `flex`, `justify-between`, `items-center`, `md:hidden`, `hidden`, `space-x-6`, `hover:text-gray-300`,  `absolute`, etc., for layout and styling.  These classes provide responsive design features easily.
* **Responsiveness:**  `md:hidden` and `md:flex` conditionally show/hide elements based on screen size (medium screens and larger).
* **Hamburger Menu:** The SVG icon acts as the hamburger menu, and JavaScript toggles the visibility of the mobile menu (`mobile-menu` div) when clicked.
* **JavaScript:** A simple JavaScript snippet handles the toggle functionality of the mobile menu.


**Links to Resources to Learn More:**

* **Tailwind CSS Documentation:** [https://tailwindcss.com/docs/](https://tailwindcss.com/docs/)  -  The official documentation is the best place to start learning about Tailwind CSS.
* **Learn CSS Grid:** [various online tutorials available, search "Learn CSS Grid" on your preferred search engine.] - While not directly used here, understanding CSS Grid is beneficial for more advanced layout designs.

Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

