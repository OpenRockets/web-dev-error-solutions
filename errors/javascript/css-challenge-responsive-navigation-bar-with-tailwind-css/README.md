# 🐞 CSS Challenge:  Responsive Navigation Bar with Tailwind CSS


This challenge involves creating a responsive navigation bar using Tailwind CSS. The navbar should be sticky at the top, adapt to different screen sizes, and feature a hamburger menu for smaller screens.  The styling will incorporate a modern, clean aesthetic.

**Description of the Styling:**

The navigation bar will have a dark background with light-colored text.  On larger screens (e.g., above 992px), the navigation links will be displayed inline.  On smaller screens, a hamburger menu icon will appear, revealing the navigation links upon click.  The design will use Tailwind's pre-defined utility classes for efficient and responsive styling.

**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Responsive Navbar</title>
<link href="https://cdn.jsdelivr.net/npm/tailwindcss@2.2.19/dist/tailwind.min.css" rel="stylesheet">
<script src="https://cdn.tailwindcss.com"></script>
</head>
<body class="bg-gray-100">

<nav class="bg-gray-800 shadow-lg sticky top-0 z-10">
  <div class="container mx-auto px-6 py-4 flex justify-between items-center">
    <a href="#" class="text-white text-2xl font-bold">My Website</a>
    <div class="md:hidden">
      <button id="hamburger" class="text-white focus:outline-none">
        <svg class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16" />
        </svg>
      </button>
    </div>
    <div class="hidden md:flex space-x-6 text-white">
      <a href="#" class="hover:text-gray-300">Home</a>
      <a href="#" class="hover:text-gray-300">About</a>
      <a href="#" class="hover:text-gray-300">Services</a>
      <a href="#" class="hover:text-gray-300">Contact</a>
    </div>
  </div>
</nav>

<div id="mobileMenu" class="hidden md:hidden bg-gray-800 absolute top-16 right-0 w-64 py-4 shadow-lg">
  <a href="#" class="block text-white px-4 py-2 hover:bg-gray-700">Home</a>
  <a href="#" class="block text-white px-4 py-2 hover:bg-gray-700">About</a>
  <a href="#" class="block text-white px-4 py-2 hover:bg-gray-700">Services</a>
  <a href="#" class="block text-white px-4 py-2 hover:bg-gray-700">Contact</a>
</div>

<script>
  const hamburger = document.getElementById('hamburger');
  const mobileMenu = document.getElementById('mobileMenu');

  hamburger.addEventListener('click', () => {
    mobileMenu.classList.toggle('hidden');
  });
</script>

</body>
</html>
```

**Explanation:**

* **Tailwind CSS:** The code leverages Tailwind's utility classes for rapid styling.  Classes like `bg-gray-800`, `text-white`, `flex`, `justify-between`, `items-center`, `md:hidden`, etc., control layout and appearance.
* **Responsiveness:**  The `md:hidden` class conditionally hides elements on medium-sized screens and larger, while the JavaScript toggles the visibility of the mobile menu.
* **Hamburger Menu:**  A simple SVG icon is used as the hamburger menu, and JavaScript handles its click event to show/hide the mobile navigation.
* **Sticky Navigation:** The `sticky top-0 z-10` classes ensure the navbar remains fixed at the top of the viewport.


**Links to Resources to Learn More:**

* **Tailwind CSS Documentation:** [https://tailwindcss.com/docs](https://tailwindcss.com/docs)
* **Learn CSS Grid:** [https://css-tricks.com/snippets/css/complete-guide-grid/](https://css-tricks.com/snippets/css/complete-guide-grid/)  (While not directly used here, understanding CSS Grid is beneficial for advanced layout techniques).
* **JavaScript Basics:** Numerous tutorials are available online, such as those on MDN Web Docs ([https://developer.mozilla.org/en-US/docs/Web/JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript)).


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

