# 🐞 CSS Challenge: Responsive Navigation Bar with Tailwind CSS


This challenge focuses on creating a responsive navigation bar using Tailwind CSS.  The navigation bar should adapt seamlessly to different screen sizes, transitioning from a horizontal menu on larger screens to a hamburger menu on smaller screens.  We'll include a logo and several navigation links.

**Description of the Styling:**

The navigation bar will have a dark background with light text.  The logo will be positioned on the left, and the navigation links will be on the right on larger screens. On smaller screens, the navigation links will be hidden behind a hamburger menu icon, which, when clicked, reveals the links in a dropdown menu.  The styling will be clean and modern, leveraging Tailwind's utility classes for efficiency.


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

  <nav class="bg-gray-800 p-4">
    <div class="container mx-auto flex justify-between items-center">
      <a href="#" class="text-2xl font-bold">My Logo</a>

      <button id="mobile-menu-button" class="block md:hidden focus:outline-none">
        <svg class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16"/>
        </svg>
      </button>

      <div id="mobile-menu" class="hidden md:flex md:space-x-6">
        <a href="#" class="hover:underline">Home</a>
        <a href="#" class="hover:underline">About</a>
        <a href="#" class="hover:underline">Services</a>
        <a href="#" class="hover:underline">Contact</a>
      </div>
    </div>
  </nav>

  <script>
    const mobileMenuButton = document.getElementById('mobile-menu-button');
    const mobileMenu = document.getElementById('mobile-menu');

    mobileMenuButton.addEventListener('click', () => {
      mobileMenu.classList.toggle('hidden');
    });
  </script>

</body>
</html>
```


**Explanation:**

* **Tailwind CSS:** The code leverages Tailwind CSS utility classes for rapid styling.  For instance, `bg-gray-800` sets the background color, `p-4` adds padding, and `flex justify-between items-center` controls the layout of the navigation bar.
* **Responsiveness:**  The `md:hidden` and `md:flex` classes make the navigation bar responsive. The hamburger menu is only visible on screens smaller than a medium-sized device (using Tailwind's breakpoint system).
* **Hamburger Menu:**  A simple SVG icon is used for the hamburger menu, and JavaScript toggles the visibility of the navigation links when the button is clicked.
* **JavaScript:** A small JavaScript snippet handles the toggling of the mobile menu's visibility.


**Links to Resources to Learn More:**

* **Tailwind CSS Official Documentation:** [https://tailwindcss.com/docs](https://tailwindcss.com/docs)
* **Learn CSS Grid:** [https://css-tricks.com/snippets/css/complete-guide-grid/](https://css-tricks.com/snippets/css/complete-guide-grid/) (While not directly used here, understanding CSS Grid is beneficial for advanced layout techniques)
* **Understanding SVG Icons:** [https://developer.mozilla.org/en-US/docs/Web/SVG](https://developer.mozilla.org/en-US/docs/Web/SVG)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

