# 🐞 CSS Challenge: Responsive Navigation Bar with Tailwind CSS


This challenge involves creating a responsive navigation bar using Tailwind CSS. The navigation bar should adapt seamlessly to different screen sizes, collapsing into a hamburger menu on smaller screens.  We'll focus on a clean, modern design with subtle animations.


## Description of the Styling:

The navigation bar will consist of a logo on the left, navigation links in the center, and a button for the mobile menu on the right (visible only on smaller screens). On larger screens, the navigation links will be displayed inline.  The overall styling will be minimalist, using Tailwind's pre-defined classes for ease and consistency.  We'll incorporate hover effects and a smooth transition for the mobile menu.

## Full Code:

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
<body class="bg-gray-100">

  <nav class="bg-white shadow-lg">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="flex justify-between items-center h-16">
        <div class="flex items-center">
          <a href="#" class="flex-shrink-0">
            <img class="h-8 w-8" src="logo.svg" alt="Logo">
          </a>
          <div class="hidden md:block">
            <div class="ml-10 flex space-x-4">
              <a href="#" class="text-gray-700 hover:text-gray-900 font-medium px-3 py-2 rounded-md">Home</a>
              <a href="#" class="text-gray-700 hover:text-gray-900 font-medium px-3 py-2 rounded-md">About</a>
              <a href="#" class="text-gray-700 hover:text-gray-900 font-medium px-3 py-2 rounded-md">Services</a>
              <a href="#" class="text-gray-700 hover:text-gray-900 font-medium px-3 py-2 rounded-md">Contact</a>
            </div>
          </div>
        </div>
        <div class="hidden md:block">
          <a href="#" class="text-gray-700 hover:text-gray-900 font-medium px-3 py-2 rounded-md">Login</a>
        </div>
        <div class="-mr-2 flex md:hidden">
          <button class="inline-flex items-center justify-center p-2 rounded-md text-gray-400 hover:text-gray-500 hover:bg-gray-100 focus:outline-none focus:ring-2 focus:ring-inset focus:ring-indigo-500">
            <svg class="h-6 w-6" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor" aria-hidden="true">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16"/>
            </svg>
          </button>
        </div>
      </div>
    </div>
  </nav>

</body>
</html>
```

Remember to replace `"logo.svg"` with the actual path to your logo.


## Explanation:

* **`bg-white shadow-lg`**:  Sets the background color to white and adds a subtle shadow.
* **`max-w-7xl mx-auto px-4 sm:px-6 lg:px-8`**: Controls the maximum width and padding of the navigation bar, adapting to different screen sizes.
* **`flex justify-between items-center h-16`**: Arranges the logo, links, and button using flexbox.
* **`hidden md:block`**: Hides elements on smaller screens (md and below) and shows them on medium screens and larger.
* **Tailwind utility classes** (`text-gray-700`, `hover:text-gray-900`, etc.):  These classes provide quick styling for text color, hover effects, padding, and more.
* **The SVG icon**:  This is a simple hamburger menu icon.

## Links to Resources to Learn More:

* **Tailwind CSS Documentation:** [https://tailwindcss.com/docs](https://tailwindcss.com/docs)
* **Learn Tailwind CSS:**  Search for "Learn Tailwind CSS" on YouTube or your preferred learning platform.  Many excellent tutorials are available.


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

