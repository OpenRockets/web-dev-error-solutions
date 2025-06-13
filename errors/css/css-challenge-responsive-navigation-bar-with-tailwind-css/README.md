# 🐞 CSS Challenge:  Responsive Navigation Bar with Tailwind CSS


This challenge focuses on creating a responsive navigation bar using Tailwind CSS. The navbar should be fixed at the top, collapse into a hamburger menu on smaller screens, and feature smooth transitions. We'll leverage Tailwind's utility classes for efficient styling and responsiveness.

**Description of the Styling:**

The navigation bar will consist of a logo on the left, a list of navigation links in the center, and a button for toggling the mobile menu on the right. On larger screens (e.g., above 768px), the navigation links will be displayed inline. On smaller screens, the links will be hidden and revealed via a hamburger menu that appears when the menu button is clicked.  The design emphasizes clean aesthetics and easy mobile usability.

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
<body>

  <nav class="bg-gray-800 shadow-lg">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="flex items-center justify-between h-16">
        <div class="flex-shrink-0">
          <a href="#" class="text-white font-bold text-xl">My Logo</a>
        </div>
        <div class="hidden md:block">
          <div class="ml-10 flex items-baseline space-x-4">
            <a href="#" class="text-gray-300 hover:bg-gray-700 hover:text-white px-3 py-2 rounded-md text-sm font-medium">Home</a>
            <a href="#" class="text-gray-300 hover:bg-gray-700 hover:text-white px-3 py-2 rounded-md text-sm font-medium">About</a>
            <a href="#" class="text-gray-300 hover:bg-gray-700 hover:text-white px-3 py-2 rounded-md text-sm font-medium">Services</a>
            <a href="#" class="text-gray-300 hover:bg-gray-700 hover:text-white px-3 py-2 rounded-md text-sm font-medium">Contact</a>
          </div>
        </div>
        <div class="md:hidden">
          <button class="inline-flex items-center justify-center p-2 rounded-md text-gray-400 hover:text-white hover:bg-gray-700 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-offset-gray-800 focus:ring-white">
            <svg class="block h-6 w-6" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor" aria-hidden="true">
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

**Explanation:**

* **`bg-gray-800 shadow-lg`**: Sets the navbar background color to dark gray and adds a subtle shadow.
* **`max-w-7xl mx-auto px-4 sm:px-6 lg:px-8`**:  Controls the maximum width and padding of the navbar content, adapting to different screen sizes.
* **`hidden md:block`**:  Hides the navigation links on screens smaller than `md` (medium breakpoint).  The `md:` prefix uses Tailwind's responsive modifiers.
* **`md:hidden`**: Hides the hamburger menu button on screens larger than `md`.
* Tailwind's pre-defined classes are used for spacing (`ml-10`, `space-x-4`), text styles (`text-gray-300`, `hover:text-white`), padding (`px-3 py-2`), and more. The SVG is a simple hamburger icon.


**Links to Resources to Learn More:**

* **Tailwind CSS Documentation:** [https://tailwindcss.com/docs/](https://tailwindcss.com/docs/) - The official Tailwind CSS documentation is an excellent resource for learning about its utility classes and features.
* **Learn Tailwind CSS (various tutorials):** Search "Learn Tailwind CSS" on YouTube or your preferred learning platform for various tutorials catering to different skill levels.


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

