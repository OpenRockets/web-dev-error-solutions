# 🐞 CSS Challenge:  Responsive Hamburger Menu with Tailwind CSS


This challenge focuses on building a responsive hamburger menu using Tailwind CSS. The menu should be neatly stacked vertically on smaller screens and transition smoothly to a horizontal navigation bar on larger screens.  We'll leverage Tailwind's utility classes for efficient styling and responsiveness.


**Description of the Styling:**

The menu will consist of a hamburger icon that toggles the visibility of a navigation list.  The list items will be styled with consistent spacing and padding.  On larger screens (above `md` breakpoint), the menu items will be displayed inline, creating a horizontal navigation bar.  We will utilize Tailwind's responsive modifiers to achieve this layout.  The hamburger icon will be hidden on larger screens.  The overall design aims for a clean and modern look.


**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <script src="https://cdn.tailwindcss.com"></script>
  <title>Responsive Hamburger Menu</title>
</head>
<body class="bg-gray-100">

  <nav class="bg-gray-800">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="flex items-center justify-between h-16">
        <div class="flex items-center">
          <a href="#" class="text-white font-bold text-xl">My Website</a>
        </div>
        <div class="flex items-center md:hidden">
          <button class="inline-flex items-center justify-center p-2 rounded-md text-gray-400 hover:text-white hover:bg-gray-700 focus:outline-none focus:ring-2 focus:ring-inset focus:ring-white" aria-expanded="false">
            <svg class="block h-6 w-6" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor" aria-hidden="true">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16"/>
            </svg>
            <svg class="hidden h-6 w-6" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor" aria-hidden="true">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12"/>
            </svg>
          </button>
        </div>
        <div class="hidden md:block">
          <div class="flex space-x-8">
            <a href="#" class="text-gray-300 hover:bg-gray-700 hover:text-white px-3 py-2 rounded-md text-sm font-medium">Home</a>
            <a href="#" class="text-gray-300 hover:bg-gray-700 hover:text-white px-3 py-2 rounded-md text-sm font-medium">About</a>
            <a href="#" class="text-gray-300 hover:bg-gray-700 hover:text-white px-3 py-2 rounded-md text-sm font-medium">Services</a>
            <a href="#" class="text-gray-300 hover:bg-gray-700 hover:text-white px-3 py-2 rounded-md text-sm font-medium">Contact</a>
          </div>
        </div>
      </div>
    </div>

    <!-- Mobile menu -->
    <div class="md:hidden">
      <div class="px-2 pt-2 pb-3 space-y-1">
        <a href="#" class="bg-gray-700 text-white block px-3 py-2 rounded-md text-base font-medium">Home</a>
        <a href="#" class="bg-gray-700 text-white block px-3 py-2 rounded-md text-base font-medium">About</a>
        <a href="#" class="bg-gray-700 text-white block px-3 py-2 rounded-md text-base font-medium">Services</a>
        <a href="#" class="bg-gray-700 text-white block px-3 py-2 rounded-md text-base font-medium">Contact</a>
      </div>
    </div>
  </nav>

</body>
</html>
```

**Explanation:**

* **Tailwind Classes:** The code heavily uses Tailwind CSS utility classes for styling.  For instance, `bg-gray-800` sets the background color, `flex` enables flexbox layout, `items-center` centers items vertically, and `justify-between` distributes space between items horizontally.
* **Responsiveness:**  `md:hidden` and `hidden md:block` are responsive modifiers that control the visibility of elements based on the screen size (using Tailwind's breakpoint system).
* **Hamburger Icon:**  The SVG code creates the hamburger icon, and JavaScript (not included here for simplicity but easily added) would be needed to toggle its state (open/close) and the visibility of the mobile menu.
* **Structure:** The code is structured to clearly separate the desktop navigation and the mobile menu, making it maintainable and easy to understand.


**Links to Resources to Learn More:**

* **Tailwind CSS Documentation:** [https://tailwindcss.com/docs](https://tailwindcss.com/docs)
* **Learn CSS Grid:** [Various online tutorials available](Search "Learn CSS Grid" on your preferred search engine)  (While this example doesn't use grid, understanding grid is valuable for layout)
* **Learn Responsive Web Design:** [Various online tutorials available](Search "Responsive Web Design" on your preferred search engine)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

