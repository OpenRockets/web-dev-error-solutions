# 🐞 CSS Challenge: Responsive Navigation Bar with Tailwind CSS


This challenge involves creating a responsive navigation bar using Tailwind CSS.  The navigation bar should be horizontally aligned on larger screens and vertically stacked on smaller screens (mobile). It will include a logo on the left, navigation links in the center, and a button on the right. The styling should be clean and modern.

**Description of the Styling:**

The navigation bar will use Tailwind's responsive utility classes to achieve the desired layout.  On larger screens (e.g., `lg` breakpoint and up), the logo, links, and button will be arranged horizontally using `flex` and `justify-between`. On smaller screens, the links will be stacked vertically using a mobile-first approach.  We'll utilize Tailwind's hover effects and padding for visual appeal.  The logo will be an image (you'll need to replace `logo.png` with your actual logo).

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
    <div class="container mx-auto px-6 py-4 flex justify-between items-center">
      <a href="#" class="flex">
        <img src="logo.png" alt="Logo" class="h-8 w-auto">
      </a>
      <div class="hidden lg:flex space-x-6">
        <a href="#" class="text-gray-600 hover:text-gray-800 font-medium">Home</a>
        <a href="#" class="text-gray-600 hover:text-gray-800 font-medium">About</a>
        <a href="#" class="text-gray-600 hover:text-gray-800 font-medium">Services</a>
        <a href="#" class="text-gray-600 hover:text-gray-800 font-medium">Contact</a>
      </div>
      <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">
        Button
      </button>
    </div>
  </nav>

  <div class="container mx-auto p-8">
      <!-- Main content here -->
  </div>

</body>
</html>
```

**Explanation:**

* **`container mx-auto px-6 py-4`**: Centers the navigation bar and adds padding.
* **`flex justify-between items-center`**: Creates a flexible container, aligns items to the left and right, and vertically centers them.
* **`hidden lg:flex`**: Hides the navigation links on smaller screens and shows them on larger screens (lg and above).
* **`space-x-6`**: Adds spacing between the navigation links.
* **`text-gray-600 hover:text-gray-800`**: Sets the text color and hover effect for the links.
* **`bg-blue-500 hover:bg-blue-700`**: Sets the background color and hover effect for the button.


**Links to Resources to Learn More:**

* **Tailwind CSS Documentation:** [https://tailwindcss.com/docs](https://tailwindcss.com/docs)
* **Tailwind CSS Cheat Sheet:** [Search for "Tailwind CSS Cheat Sheet" on Google for many options]
* **MDN Web Docs (CSS):** [https://developer.mozilla.org/en-US/docs/Web/CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

