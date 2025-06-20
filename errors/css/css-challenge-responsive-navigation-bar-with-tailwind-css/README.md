# 🐞 CSS Challenge: Responsive Navigation Bar with Tailwind CSS


This challenge involves creating a responsive navigation bar using Tailwind CSS.  The navigation bar should adapt smoothly to different screen sizes, collapsing into a hamburger menu on smaller screens.  We'll include a logo, several navigation links, and a button.

**Description of the Styling:**

The navigation bar will be a fixed-top element, meaning it stays visible as the user scrolls.  On larger screens (e.g., desktops), the navigation links will be displayed inline.  On smaller screens (e.g., mobile phones), the links will be hidden behind a hamburger menu icon that, when clicked, will reveal the navigation links in a dropdown.  We'll use Tailwind's responsive modifiers to achieve this.  The overall style will be clean and modern.

**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Responsive Navigation Bar</title>
  <script src="https://cdn.tailwindcss.com"></script>
</head>
<body class="bg-gray-100">

  <nav class="bg-white shadow-lg fixed w-full top-0 z-10">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="flex justify-between h-16">
        <div class="flex-shrink-0 flex items-center">
          <a href="#" class="text-xl font-bold text-indigo-600">Logo</a>
        </div>
        <div class="flex items-center">
          <div class="hidden md:block">
            <div class="ml-10 flex space-x-4">
              <a href="#" class="text-gray-700 hover:text-indigo-500 px-3 py-2 rounded-md text-sm font-medium">Home</a>
              <a href="#" class="text-gray-700 hover:text-indigo-500 px-3 py-2 rounded-md text-sm font-medium">About</a>
              <a href="#" class="text-gray-700 hover:text-indigo-500 px-3 py-2 rounded-md text-sm font-medium">Services</a>
              <a href="#" class="text-gray-700 hover:text-indigo-500 px-3 py-2 rounded-md text-sm font-medium">Contact</a>
            </div>
          </div>
          <div class="md:hidden">
            <button class="inline-flex items-center justify-center p-2 rounded-md text-gray-400 hover:text-gray-500 hover:bg-gray-100 focus:outline-none focus:ring-2 focus:ring-inset focus:ring-indigo-500">
              <svg class="h-6 w-6" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor" aria-hidden="true">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16" />
              </svg>
            </button>
          </div>
        </div>
      </div>
    </div>
  </nav>


  <div class="p-8">
    <!-- Main content here -->
  </div>

</body>
</html>
```

**Explanation:**

* **`fixed w-full top-0 z-10`**: This makes the navigation bar fixed to the top, full width, and with a high z-index to ensure it's always on top.
* **`max-w-7xl mx-auto px-4 sm:px-6 lg:px-8`**: This uses Tailwind's responsive padding and maximum width classes for better layout control.
* **`hidden md:block`**: This hides the navigation links on smaller screens (up to `md` breakpoint) and shows them on medium and larger screens.
* **`md:hidden`**: This shows the hamburger menu icon only on smaller screens.  The SVG is a simple hamburger icon.
* The rest of the classes style the elements using Tailwind's pre-defined utility classes for spacing, colors, fonts, etc.


**Links to Resources to Learn More:**

* **Tailwind CSS Documentation:** [https://tailwindcss.com/docs](https://tailwindcss.com/docs)
* **Learn Tailwind CSS (various tutorials available on YouTube and other platforms):** Search "Learn Tailwind CSS" on YouTube or your preferred learning platform.


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

