# 🐞 CSS Challenge: Responsive Pricing Table with Tailwind CSS


This challenge focuses on creating a responsive pricing table using Tailwind CSS. The goal is to build a clean, visually appealing table that adapts seamlessly to different screen sizes.  We'll use Tailwind's utility classes for efficient styling and responsiveness.

**Description of the Styling:**

The pricing table will have three columns representing different pricing plans (Basic, Pro, Enterprise). Each plan will have a title, a list of features, a price, and a call-to-action button.  The table will be responsive, adjusting its layout to accommodate smaller screens by stacking the columns vertically.  We'll use Tailwind's `bg-gray-100`, `p-4`, `rounded-lg`, `shadow-md`, and similar classes for styling and layout.

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

<div class="container mx-auto p-8">
  <h1 class="text-3xl font-bold mb-8 text-center">Pricing Plans</h1>
  <div class="grid grid-cols-1 md:grid-cols-3 gap-8">

    <!-- Basic Plan -->
    <div class="bg-white p-6 rounded-lg shadow-md">
      <h2 class="text-xl font-bold mb-4">Basic</h2>
      <ul class="list-disc list-inside mb-4">
        <li>Feature 1</li>
        <li>Feature 2</li>
        <li>Feature 3</li>
      </ul>
      <p class="text-2xl font-bold mb-4">$9/month</p>
      <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">Sign Up</button>
    </div>

    <!-- Pro Plan -->
    <div class="bg-white p-6 rounded-lg shadow-md">
      <h2 class="text-xl font-bold mb-4">Pro</h2>
      <ul class="list-disc list-inside mb-4">
        <li>Feature 1</li>
        <li>Feature 2</li>
        <li>Feature 3</li>
        <li>Feature 4</li>
        <li>Feature 5</li>
      </ul>
      <p class="text-2xl font-bold mb-4">$29/month</p>
      <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">Sign Up</button>
    </div>

    <!-- Enterprise Plan -->
    <div class="bg-white p-6 rounded-lg shadow-md">
      <h2 class="text-xl font-bold mb-4">Enterprise</h2>
      <ul class="list-disc list-inside mb-4">
        <li>Feature 1</li>
        <li>Feature 2</li>
        <li>Feature 3</li>
        <li>Feature 4</li>
        <li>Feature 5</li>
        <li>Feature 6</li>
      </ul>
      <p class="text-2xl font-bold mb-4">$99/month</p>
      <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">Sign Up</button>
    </div>

  </div>
</div>

</body>
</html>
```

**Explanation:**

* The code uses Tailwind's grid system (`grid`, `grid-cols`, `gap`) for layout.  `grid-cols-1` makes it a single column on small screens, while `md:grid-cols-3` switches to three columns on medium screens and larger.
* Utility classes like `bg-white`, `p-6`, `rounded-lg`, `shadow-md` provide styling quickly.
* Responsive behavior is achieved through Tailwind's responsive modifiers (e.g., `md:`).
* The `container` class centers the content.


**Links to Resources to Learn More:**

* **Tailwind CSS Documentation:** [https://tailwindcss.com/docs](https://tailwindcss.com/docs)
* **Tailwind CSS Grid System:** [https://tailwindcss.com/docs/grid](https://tailwindcss.com/docs/grid)
* **Learn CSS Grid:** [https://css-tricks.com/snippets/css/complete-guide-grid/](https://css-tricks.com/snippets/css/complete-guide-grid/) (Helpful even if using Tailwind)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

