# 🐞 CSS Challenge:  Building a Simple Navigation Bar with Tailwind CSS


This challenge focuses on building a clean and responsive navigation bar using Tailwind CSS.  The goal is to create a horizontal navigation bar with multiple links, styled consistently across different screen sizes.  We'll leverage Tailwind's utility classes for quick and efficient styling.

**Description of the Styling:**

The navigation bar will be positioned at the top of the page.  It will have a dark background and light-colored text. Links within the navigation bar will be styled with padding, hover effects, and will maintain consistent spacing. The navigation bar will remain responsive, adapting neatly to smaller screens.

**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Navigation Bar</title>
  <script src="https://cdn.tailwindcss.com"></script>
</head>
<body class="bg-gray-100">

  <nav class="bg-gray-800">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="flex items-center justify-between h-16">
        <div class="flex items-center">
          <a href="#" class="flex-shrink-0 text-white font-bold text-xl">My Website</a>
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
  </nav>

</body>
</html>
```

**Explanation:**

* **`bg-gray-800`:** Sets the background color of the navigation bar to dark gray.
* **`max-w-7xl mx-auto px-4 sm:px-6 lg:px-8`:** Controls the maximum width and padding of the navigation bar, adapting to different screen sizes.
* **`flex items-center justify-between h-16`:** Uses flexbox for layout, centering items vertically and horizontally.  `h-16` sets the height.
* **`text-gray-300 hover:bg-gray-700 hover:text-white`:** Styles the links with light gray text, changing to white on hover with a darker gray background.
* **`px-3 py-2 rounded-md text-sm font-medium`:** Adds padding, rounded corners, and sets font size and weight.
* **`hidden md:block`:** Hides the navigation links on smaller screens (below medium size) for a mobile-first approach.  This allows for a hamburger menu implementation (not included in this basic example).
* **`space-x-8`:** Adds spacing between the navigation links.

**Links to Resources to Learn More:**

* **Tailwind CSS Documentation:** [https://tailwindcss.com/docs](https://tailwindcss.com/docs) - The official Tailwind CSS documentation is an invaluable resource.
* **Tailwind CSS Cheat Sheet:** [Search for "Tailwind CSS Cheat Sheet" on Google](Search engines often provide updated cheat sheet links.)  Many cheat sheets are available online to quickly look up utility classes.
* **Learn CSS (general):** [MDN Web Docs CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) - A comprehensive resource for learning CSS fundamentals.


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

