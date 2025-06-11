# 🐞 CSS Challenge:  Responsive Pricing Table with Tailwind CSS


This challenge focuses on creating a responsive pricing table using Tailwind CSS.  The goal is to build a clean, visually appealing table that adapts seamlessly to different screen sizes.  We'll use Tailwind's utility classes for efficient styling and responsive design.

**Description of the Styling:**

The pricing table will consist of three plans: Basic, Pro, and Premium. Each plan will have a title, a list of features, and a price.  We'll use card-like elements for each plan to visually separate them. The table will be responsive, adjusting its layout for smaller screens (e.g., stacking the plans vertically on mobile). We will leverage Tailwind's built-in responsive modifiers (e.g., `md:`, `lg:`) to achieve this.

**Full Code:**

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

  <div class="container mx-auto px-4 py-8">
    <h1 class="text-3xl font-bold text-center mb-8">Choose Your Plan</h1>
    <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
      <!-- Basic Plan -->
      <div class="bg-white shadow-md rounded-lg p-6">
        <h2 class="text-xl font-bold mb-4">Basic</h2>
        <ul class="list-disc list-inside mb-4">
          <li>Feature 1</li>
          <li>Feature 2</li>
          <li>Feature 3</li>
        </ul>
        <p class="text-2xl font-bold">$9/month</p>
        <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">Sign Up</button>
      </div>

      <!-- Pro Plan -->
      <div class="bg-white shadow-md rounded-lg p-6">
        <h2 class="text-xl font-bold mb-4">Pro</h2>
        <ul class="list-disc list-inside mb-4">
          <li>Feature 1</li>
          <li>Feature 2</li>
          <li>Feature 3</li>
          <li>Feature 4</li>
          <li>Feature 5</li>
        </ul>
        <p class="text-2xl font-bold">$19/month</p>
        <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">Sign Up</button>
      </div>

      <!-- Premium Plan -->
      <div class="bg-white shadow-md rounded-lg p-6">
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
        <p class="text-2xl font-bold">$29/month</p>
        <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">Sign Up</button>
      </div>
    </div>
  </div>

</body>
</html>
```

**Explanation:**

*   **`grid` utility:**  Creates a grid layout for the plans.  `grid-cols-1` makes it a single column by default. `md:grid-cols-3` changes it to three columns on medium screens and larger.
*   **`gap-8`:** Adds spacing between the grid items.
*   **`bg-white`, `shadow-md`, `rounded-lg`, `p-6`:**  These classes style the card-like containers for each plan.
*   **Responsive Modifiers:**  Tailwind's responsive modifiers (e.g., `md:`) allow styles to be applied only above certain breakpoints.


**Links to Resources to Learn More:**

*   **Tailwind CSS Documentation:** [https://tailwindcss.com/docs](https://tailwindcss.com/docs)
*   **Learn CSS Grid:** [https://css-tricks.com/snippets/css/complete-guide-grid/](https://css-tricks.com/snippets/css/complete-guide-grid/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

