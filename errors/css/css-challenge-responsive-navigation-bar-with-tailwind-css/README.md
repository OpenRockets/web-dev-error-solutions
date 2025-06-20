# 🐞 CSS Challenge: Responsive Navigation Bar with Tailwind CSS


This challenge involves creating a responsive navigation bar using Tailwind CSS.  The navigation bar should adapt seamlessly to different screen sizes, collapsing into a hamburger menu on smaller screens.  We'll utilize Tailwind's pre-built classes for a rapid development process.


**Description of the Styling:**

The navigation bar will contain a logo on the left and a list of navigation links on the right. On larger screens (e.g., desktops), the links will be displayed inline. On smaller screens (e.g., mobile), the links will be hidden behind a hamburger menu icon that, when clicked, toggles the visibility of the links.  The styling will be clean, modern, and consistent with Tailwind's design philosophy.

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
      <div class="flex justify-between h-16">
        <div class="flex">
          <div class="flex-shrink-0 flex items-center">
            <a href="#" class="text-xl font-bold text-indigo-600">My Logo</a>
          </div>
        </div>
        <div class="flex items-center">
          <button class="lg:hidden inline-flex items-center justify-center p-2 rounded-md text-gray-400 hover:text-gray-500 hover:bg-gray-100 focus:outline-none focus:bg-gray-100 focus:text-gray-500">
            <svg class="h-6 w-6" stroke="currentColor" fill="none" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16"/>
            </svg>
          </button>

          <div class="hidden lg:flex space-x-8">
            <a href="#" class="text-gray-700 hover:text-gray-900">Home</a>
            <a href="#" class="text-gray-700 hover:text-gray-900">About</a>
            <a href="#" class="text-gray-700 hover:text-gray-900">Services</a>
            <a href="#" class="text-gray-700 hover:text-gray-900">Contact</a>
          </div>
        </div>
      </div>
    </div>
  </nav>

</body>
</html>
```


**Explanation:**

* **`bg-gray-100`:** Sets the background color of the body to a light gray.
* **`bg-white shadow-lg`:** Styles the navigation bar with a white background and a subtle shadow.
* **`max-w-7xl mx-auto px-4 sm:px-6 lg:px-8`:** Controls the maximum width and padding of the navigation bar.  It uses responsive modifiers (`sm:`, `lg:`) to adjust padding at different screen sizes.
* **`flex justify-between h-16`:**  Makes the navigation bar a flex container, aligning items to the left and right, and setting its height to 16 units.
* **`lg:hidden`:** Hides the hamburger menu button on larger screens.
* **`hidden lg:flex`:** Hides the navigation links on smaller screens and shows them on larger screens.
* **`space-x-8`:** Adds spacing between the navigation links.


**Links to Resources to Learn More:**

* **Tailwind CSS Documentation:** [https://tailwindcss.com/docs](https://tailwindcss.com/docs) -  The official Tailwind CSS documentation is an excellent resource for learning about its features and usage.
* **Tailwind CSS Cheat Sheet:**  Search for "Tailwind CSS cheat sheet" on Google – Many helpful cheat sheets are available to quickly reference Tailwind classes.


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

