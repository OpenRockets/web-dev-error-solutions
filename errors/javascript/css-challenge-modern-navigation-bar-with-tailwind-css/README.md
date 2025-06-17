# 🐞 CSS Challenge:  Modern Navigation Bar with Tailwind CSS


This challenge focuses on creating a modern, responsive navigation bar using Tailwind CSS.  The design emphasizes clean lines, subtle hover effects, and a mobile-first approach. The navbar will include a logo, several navigation links, and a button.

**Description of the Styling:**

The navigation bar will be a fixed-width container centered on the page.  On larger screens, it will display all navigation items inline.  On smaller screens, it will collapse into a hamburger menu, revealing the links when the menu is toggled.  The styling will utilize Tailwind CSS utility classes for efficient and concise code.  The overall aesthetic aims for a minimalist and contemporary feel.

**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Modern Navigation Bar</title>
  <script src="https://cdn.tailwindcss.com"></script>
</head>
<body class="bg-gray-100">

  <nav class="bg-white shadow-md w-full md:w-3/4 lg:w-1/2 xl:w-1/3 mx-auto px-4 py-2">
    <div class="container flex items-center justify-between">
      <a href="#" class="text-xl font-bold text-gray-800">My Logo</a>

      <button id="menu-button" class="block md:hidden focus:outline-none">
        <svg class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16"/>
        </svg>
      </button>

      <div id="menu" class="hidden md:flex md:space-x-4">
        <a href="#" class="text-gray-700 hover:text-gray-900">Home</a>
        <a href="#" class="text-gray-700 hover:text-gray-900">About</a>
        <a href="#" class="text-gray-700 hover:text-gray-900">Services</a>
        <a href="#" class="text-gray-700 hover:text-gray-900">Contact</a>
      </div>
      <button class="hidden md:block bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">
        Get Started
      </button>
    </div>
  </nav>

  <script>
    const menuButton = document.getElementById('menu-button');
    const menu = document.getElementById('menu');

    menuButton.addEventListener('click', () => {
      menu.classList.toggle('hidden');
    });
  </script>

</body>
</html>
```

**Explanation:**

* **`bg-white shadow-md w-full md:w-3/4 lg:w-1/2 xl:w-1/3 mx-auto px-4 py-2`**: This sets the background color, adds a shadow, defines the width (responsive using Tailwind's breakpoint modifiers), centers the nav, and adds padding.
* **`flex items-center justify-between`**:  This uses flexbox to arrange items in a row, vertically center them, and justify them to opposite ends.
* **`hidden md:flex`**: This hides the menu on smaller screens and makes it visible on medium screens and larger.
* **`hover:text-gray-900`**: This is a hover effect, changing the text color on hover.
* **JavaScript:** The JavaScript toggles the `hidden` class on the menu when the hamburger menu button is clicked.


**Links to Resources to Learn More:**

* **Tailwind CSS Documentation:** [https://tailwindcss.com/docs](https://tailwindcss.com/docs)
* **Learn CSS Grid:**  [https://css-tricks.com/snippets/css/complete-guide-grid/](https://css-tricks.com/snippets/css/complete-guide-grid/) (While not directly used here, understanding grid is beneficial for complex layouts).
* **Understanding Flexbox:** [https://css-tricks.com/snippets/css/a-guide-to-flexbox/](https://css-tricks.com/snippets/css/a-guide-to-flexbox/) (Crucial for the layout of this navbar).


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

