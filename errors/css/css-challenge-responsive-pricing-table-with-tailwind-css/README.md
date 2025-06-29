# 🐞 CSS Challenge: Responsive Pricing Table with Tailwind CSS


This challenge focuses on creating a responsive pricing table using Tailwind CSS.  The goal is to build a clean, visually appealing table that adapts seamlessly to different screen sizes.  We'll use Tailwind's utility classes to achieve efficient and maintainable styling.

## Description of the Styling

The pricing table will consist of three plans: Basic, Pro, and Premium. Each plan will have a title, a list of features, and a price.  The table will be responsive, adjusting its layout based on the screen size.  It will utilize Tailwind's grid system for layout and its color palette for visual appeal.  We'll aim for a clean, modern aesthetic.

## Full Code

```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Responsive Pricing Table</title>
  <script src="https://cdn.tailwindcss.com"></script>
</head>
<body class="bg-gray-100">

  <div class="container mx-auto p-8">
    <h1 class="text-3xl font-bold text-center mb-8">Choose Your Plan</h1>
    <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
      <div class="bg-white rounded-lg shadow-md p-6">
        <h2 class="text-xl font-bold mb-4">Basic</h2>
        <ul class="list-disc list-inside mb-4">
          <li>Feature 1</li>
          <li>Feature 2</li>
          <li>Feature 3</li>
        </ul>
        <p class="text-2xl font-bold text-green-500">$9/month</p>
        <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">Sign Up</button>
      </div>
      <div class="bg-white rounded-lg shadow-md p-6">
        <h2 class="text-xl font-bold mb-4">Pro</h2>
        <ul class="list-disc list-inside mb-4">
          <li>Feature 1</li>
          <li>Feature 2</li>
          <li>Feature 3</li>
          <li>Feature 4</li>
          <li>Feature 5</li>
        </ul>
        <p class="text-2xl font-bold text-green-500">$19/month</p>
        <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">Sign Up</button>
      </div>
      <div class="bg-white rounded-lg shadow-md p-6">
        <h2 class="text-xl font-bold mb-4">Premium</h2>
        <ul class="list-disc list-inside mb-4">
          <li>Feature 1</li>
          <li>Feature 2</li>
          <li>Feature 3</li>
          <li>Feature 4</li>
          <li>Feature 5</li>
          <li>Feature 6</li>
          <li>Feature 7</li>
        </ul>
        <p class="text-2xl font-bold text-green-500">$29/month</p>
        <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">Sign Up</button>
      </div>
    </div>
  </div>

</body>
</html>
```

## Explanation

The code utilizes Tailwind CSS's utility classes for styling.  `grid` and `grid-cols` create the responsive layout.  `bg-white`, `rounded-lg`, `shadow-md`, etc., handle the visual aspects.  Media queries are implicitly handled by Tailwind's responsive modifiers (e.g., `md:grid-cols-3`).  The code is concise and easy to understand due to Tailwind's declarative nature.


## Links to Resources to Learn More

* **Tailwind CSS Documentation:** [https://tailwindcss.com/docs](https://tailwindcss.com/docs) -  The official Tailwind CSS documentation is an excellent resource for learning about its features and utility classes.
* **Tailwind CSS Cheat Sheet:**  Search for "Tailwind CSS cheat sheet" on Google to find numerous helpful cheat sheets summarizing common utility classes.


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

