# 🐞 CSS Challenge:  Responsive Navigation Bar with Tailwind CSS


This challenge focuses on creating a responsive navigation bar using Tailwind CSS. The navigation bar should adapt seamlessly to different screen sizes, collapsing into a hamburger menu on smaller screens.  We'll incorporate some basic styling for visual appeal.

**Description of the Styling:**

The navigation bar will contain a logo on the left and a list of navigation links on the right. On larger screens (e.g., above 768px), the links will be displayed inline. On smaller screens, the links will be hidden behind a hamburger menu icon that, when clicked, reveals the links in a dropdown menu.  We'll use Tailwind's responsive modifiers to achieve this. The overall style will be clean and modern.


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
    <div class="container mx-auto px-4 py-3 flex justify-between items-center">
      <a href="#" class="text-xl font-bold text-indigo-600">My Logo</a>

      <div class="md:flex md:items-center md:space-x-4 hidden">
        <a href="#" class="py-2 px-4 text-gray-700 hover:bg-indigo-100 rounded">Home</a>
        <a href="#" class="py-2 px-4 text-gray-700 hover:bg-indigo-100 rounded">About</a>
        <a href="#" class="py-2 px-4 text-gray-700 hover:bg-indigo-100 rounded">Services</a>
        <a href="#" class="py-2 px-4 text-gray-700 hover:bg-indigo-100 rounded">Contact</a>
      </div>

      <!-- Hamburger Menu -->
      <div class="md:hidden">
        <button id="menuButton" class="text-gray-700 hover:text-indigo-600 focus:outline-none">
          <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16" />
          </svg>
        </button>
      </div>

    </div>
  </nav>


  <div id="mobileMenu" class="md:hidden fixed top-0 left-0 w-full h-screen bg-gray-800 bg-opacity-75 z-50">
    <div class="container mx-auto px-4 py-8">
      <a href="#" class="text-2xl font-bold text-white mb-6">My Logo</a>
      <ul class="space-y-4 text-white">
        <li><a href="#" class="block px-4 py-2 hover:bg-indigo-200 hover:text-gray-900">Home</a></li>
        <li><a href="#" class="block px-4 py-2 hover:bg-indigo-200 hover:text-gray-900">About</a></li>
        <li><a href="#" class="block px-4 py-2 hover:bg-indigo-200 hover:text-gray-900">Services</a></li>
        <li><a href="#" class="block px-4 py-2 hover:bg-indigo-200 hover:text-gray-900">Contact</a></li>
      </ul>
    </div>
  </div>

  <script>
    const menuButton = document.getElementById('menuButton');
    const mobileMenu = document.getElementById('mobileMenu');

    menuButton.addEventListener('click', () => {
      mobileMenu.classList.toggle('hidden');
    });
  </script>


</body>
</html>
```

**Explanation:**

* **Tailwind Classes:** The code extensively uses Tailwind CSS classes for styling. For instance, `bg-white` sets the background color to white, `flex` enables flexbox layout, `justify-between` distributes items between the ends, and `md:hidden` hides elements on medium screens and larger.  The responsive modifiers (e.g., `md:`, `lg:`) control the layout based on screen size.
* **Hamburger Menu:** A simple hamburger menu icon is implemented using an SVG. JavaScript is used to toggle the visibility of the mobile menu when the button is clicked.  The `z-50` class ensures the mobile menu appears above other content.
* **Responsiveness:**  Tailwind's responsive modifiers (`md:`, `sm:`, etc.) effortlessly handle the different screen sizes.


**Links to Resources to Learn More:**

* **Tailwind CSS Documentation:** [https://tailwindcss.com/docs/](https://tailwindcss.com/docs/) - The official Tailwind CSS documentation.  This is an excellent resource for learning about all the available classes and utilities.
* **Learn CSS Grid:** [https://css-tricks.com/snippets/css/complete-guide-grid/](https://css-tricks.com/snippets/css/complete-guide-grid/) - While not directly used in this example, understanding CSS Grid is beneficial for advanced layout techniques. (Consider adding other resources as well, like a Tailwind CSS tutorial)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

