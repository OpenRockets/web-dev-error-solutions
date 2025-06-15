# 🐞 CSS Challenge:  Creating a Responsive Navigation Bar with Tailwind CSS


This challenge focuses on building a responsive navigation bar using Tailwind CSS.  The navigation bar will adapt seamlessly to different screen sizes, showcasing the power of Tailwind's utility classes for rapid UI development.  We'll create a clean, modern design that's easy to customize.

**Description of the Styling:**

The navigation bar will consist of a logo on the left, a list of navigation links in the center, and a button (e.g., "Login" or "Sign Up") on the right. On larger screens, all elements will be displayed horizontally. On smaller screens (mobile), the navigation links will collapse into a hamburger menu, revealing themselves on click.

**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Responsive Nav Bar</title>
  <script src="https://cdn.tailwindcss.com"></script>
</head>
<body class="bg-gray-100">

  <nav class="bg-white shadow-lg">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="flex items-center justify-between h-16">
        <div class="flex items-center">
          <a href="#" class="flex-shrink-0">
            <img class="h-8 w-auto" src="your-logo.svg" alt="Your Logo">
          </a>
          <div class="hidden md:block">
            <div class="ml-10 flex space-x-4">
              <a href="#" class="text-gray-700 hover:text-gray-900">Home</a>
              <a href="#" class="text-gray-700 hover:text-gray-900">About</a>
              <a href="#" class="text-gray-700 hover:text-gray-900">Services</a>
              <a href="#" class="text-gray-700 hover:text-gray-900">Contact</a>
            </div>
          </div>
        </div>
        <div class="hidden md:block">
          <a href="#" class="text-gray-700 hover:text-gray-900 px-3 py-2 rounded-md text-sm font-medium">Login</a>
        </div>
        <div class="-mr-2 flex md:hidden">
          <!-- Mobile menu button -->
          <button class="bg-gray-200 inline-flex items-center justify-center p-2 rounded-md text-gray-400 hover:text-gray-500 hover:bg-gray-300 focus:outline-none focus:ring-2 focus:ring-inset focus:ring-indigo-500">
            <svg class="h-6 w-6" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor" aria-hidden="true">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16" />
            </svg>
          </button>
        </div>
      </div>
    </div>

    <!-- Mobile menu -->
    <div class="md:hidden">
      <div class="px-2 pt-2 pb-3 space-y-1">
        <a href="#" class="bg-gray-100 text-gray-700 block px-3 py-2 rounded-md text-base font-medium">Home</a>
        <a href="#" class="bg-gray-100 text-gray-700 block px-3 py-2 rounded-md text-base font-medium">About</a>
        <a href="#" class="bg-gray-100 text-gray-700 block px-3 py-2 rounded-md text-base font-medium">Services</a>
        <a href="#" class="bg-gray-100 text-gray-700 block px-3 py-2 rounded-md text-base font-medium">Contact</a>
      </div>
    </div>
  </nav>

</body>
</html>
```

Remember to replace `"your-logo.svg"` with the actual path to your logo.

**Explanation:**

* **Tailwind Classes:** The code heavily leverages Tailwind's utility classes for styling.  For example, `flex`, `items-center`, `justify-between`, `bg-white`, `shadow-lg`, etc., control layout and appearance.
* **Responsiveness:**  The `md:hidden` and `hidden md:block` classes control the visibility of elements based on screen size (using Tailwind's responsive modifiers).  This ensures the navigation bar adapts well to different devices.
* **Hamburger Menu:** The hamburger menu icon is implemented using an SVG and only shows up on smaller screens.  (Note: You would need to add JavaScript to toggle the mobile menu's visibility when the button is clicked - this example omits the JS for brevity).

**Links to Resources to Learn More:**

* **Tailwind CSS Official Documentation:** [https://tailwindcss.com/docs/](https://tailwindcss.com/docs/)
* **Learn Tailwind CSS (various tutorials available on YouTube and other platforms):** Search "Learn Tailwind CSS" on YouTube or your preferred learning resource.


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

