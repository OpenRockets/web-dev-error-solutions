# 🐞 CSS Challenge: Responsive Navigation Bar with Tailwind CSS


This challenge involves creating a responsive navigation bar using Tailwind CSS.  The navbar should be fixed at the top of the viewport, collapse into a hamburger menu on smaller screens, and have a clean, modern aesthetic.

**Description of the Styling:**

The navigation bar will consist of a logo on the left and a list of navigation links on the right.  On larger screens (e.g., above 768px), the navigation links will be displayed inline.  On smaller screens, the links will be hidden behind a hamburger menu icon, which, when clicked, will toggle the visibility of the links.  We'll use Tailwind's responsive modifiers and its built-in utility classes to achieve this.  The styling will be clean and minimalist, adhering to best practices for accessibility and usability.

**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Responsive Navbar</title>
  <script src="https://cdn.tailwindcss.com"></script>
</head>
<body class="bg-gray-100">

  <nav class="bg-white shadow-lg fixed w-full top-0 z-50">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="flex items-center justify-between h-16">
        <div class="flex items-center">
          <a href="#" class="flex-shrink-0">
            <img class="h-8 w-8" src="your-logo.svg" alt="Logo">
          </a>
          <div class="hidden md:block">
            <div class="ml-10 flex items-baseline space-x-4">
              <a href="#" class="text-gray-700 hover:text-gray-900 px-3 py-2 rounded-md text-sm font-medium">Home</a>
              <a href="#" class="text-gray-700 hover:text-gray-900 px-3 py-2 rounded-md text-sm font-medium">About</a>
              <a href="#" class="text-gray-700 hover:text-gray-900 px-3 py-2 rounded-md text-sm font-medium">Services</a>
              <a href="#" class="text-gray-700 hover:text-gray-900 px-3 py-2 rounded-md text-sm font-medium">Contact</a>
            </div>
          </div>
        </div>
        <div class="hidden md:block">
          <a href="#" class="text-gray-700 hover:text-gray-900 px-3 py-2 rounded-md text-sm font-medium">Login</a>
        </div>
        <div class="-mr-2 flex md:hidden">
          <!-- Mobile menu button -->
          <button class="inline-flex items-center justify-center p-2 rounded-md text-gray-400 hover:text-gray-500 hover:bg-gray-100 focus:outline-none focus:ring-2 focus:ring-inset focus:ring-indigo-500">
            <span class="sr-only">Open main menu</span>
            <!-- Heroicon name: outline/menu -->
            <svg class="h-6 w-6" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor" aria-hidden="true">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16" />
            </svg>
          </button>
        </div>
      </div>
    </div>

    <!-- Mobile menu, show/hide based on menu state. -->
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

Remember to replace `"your-logo.svg"` with the actual path to your logo.  This code utilizes Tailwind's pre-built classes for styling, making it concise and easy to read.  You will need to include the Tailwind CDN link in your `<head>` as shown.

**Explanation:**

The code utilizes Tailwind's responsive design features.  The `md:hidden` and `hidden md:block` classes control the visibility of elements based on screen size.  The hamburger menu is only visible on smaller screens, while the full navigation links are only visible on larger screens.  The `flex`, `items-center`, and `justify-between` classes are used for layout and alignment.


**Links to Resources to Learn More:**

* **Tailwind CSS Documentation:** [https://tailwindcss.com/docs/](https://tailwindcss.com/docs/)
* **Learn Tailwind CSS:** [Numerous tutorials available on YouTube and other platforms. Search for "Learn Tailwind CSS"](Search "Learn Tailwind CSS" on YouTube or your preferred learning platform)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

