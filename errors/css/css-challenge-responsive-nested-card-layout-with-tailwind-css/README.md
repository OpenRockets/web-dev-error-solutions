# 🐞 CSS Challenge:  Responsive Nested Card Layout with Tailwind CSS


This challenge involves creating a responsive layout of nested cards using Tailwind CSS.  The outer cards will contain a title and a smaller inner card showcasing an image. The layout should adapt gracefully to different screen sizes, maintaining a clean and visually appealing presentation.

**Description of the Styling:**

We'll use Tailwind CSS classes to create a grid-based layout.  The outer cards will be relatively large and have rounded corners. The inner cards will be smaller, containing an image that fills its width and maintains aspect ratio.  We'll use responsive modifiers to adjust the number of columns displayed based on screen size.


**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <script src="https://cdn.tailwindcss.com"></script>
  <title>Nested Card Layout</title>
</head>
<body class="bg-gray-100">
  <div class="container mx-auto p-4 grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-4">
    <div class="bg-white rounded-lg shadow-md p-4">
      <h2 class="text-xl font-bold mb-2">Card 1</h2>
      <div class="bg-gray-200 rounded-lg overflow-hidden">
        <img src="https://via.placeholder.com/350x200" alt="Image 1" class="w-full">
      </div>
    </div>
    <div class="bg-white rounded-lg shadow-md p-4">
      <h2 class="text-xl font-bold mb-2">Card 2</h2>
      <div class="bg-gray-200 rounded-lg overflow-hidden">
        <img src="https://via.placeholder.com/350x200" alt="Image 2" class="w-full">
      </div>
    </div>
    <div class="bg-white rounded-lg shadow-md p-4">
      <h2 class="text-xl font-bold mb-2">Card 3</h2>
      <div class="bg-gray-200 rounded-lg overflow-hidden">
        <img src="https://via.placeholder.com/350x200" alt="Image 3" class="w-full">
      </div>
    </div>
    <div class="bg-white rounded-lg shadow-md p-4">
      <h2 class="text-xl font-bold mb-2">Card 4</h2>
      <div class="bg-gray-200 rounded-lg overflow-hidden">
        <img src="https://via.placeholder.com/350x200" alt="Image 4" class="w-full">
      </div>
    </div>
      <!-- Add more cards as needed -->
  </div>
</body>
</html>

```

**Explanation:**

* **`container mx-auto p-4`:** Centers the content and adds padding.
* **`grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-4`:** Creates a responsive grid layout.  One column on small screens, two on medium, and three on large. `gap-4` adds spacing between the cards.
* **`bg-white rounded-lg shadow-md p-4`:** Styles the outer cards with white background, rounded corners, shadow, and padding.
* **`text-xl font-bold mb-2`:** Styles the card titles.
* **`bg-gray-200 rounded-lg overflow-hidden`:** Styles the inner card container. `overflow-hidden` prevents the image from overflowing.
* **`w-full`:** Makes the image fill the width of its container.  The aspect ratio of the placeholder image is maintained automatically.


**Links to Resources to Learn More:**

* **Tailwind CSS Documentation:** [https://tailwindcss.com/docs](https://tailwindcss.com/docs)
* **MDN Web Docs (CSS Grid):** [https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

