# 🐞 CSS Challenge: Responsive Pricing Table with Tailwind CSS


This challenge focuses on building a responsive pricing table using Tailwind CSS. The goal is to create a clean, visually appealing table that adapts seamlessly to different screen sizes.  We'll utilize Tailwind's utility classes for efficient and rapid styling.

**Description of the Styling:**

The pricing table will feature three different pricing plans: Basic, Pro, and Premium. Each plan will have a distinct color scheme (using Tailwind's color palette) and will clearly display the plan's name, price, and a list of features.  The table will be responsive, meaning it will adjust its layout beautifully on smaller screens (e.g., mobile devices) by stacking the columns vertically.  We'll add some subtle hover effects for improved user experience.


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
    <h2 class="text-3xl font-bold text-center mb-8">Choose Your Plan</h2>
    <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
      <!-- Basic Plan -->
      <div class="bg-white rounded-lg shadow-md p-6">
        <h3 class="text-xl font-bold text-blue-500 mb-4">Basic</h3>
        <p class="text-4xl font-bold text-gray-800 mb-4">$9<span class="text-xl">/month</span></p>
        <ul class="list-disc list-inside text-gray-600">
          <li>1 User</li>
          <li>10 GB Storage</li>
          <li>Basic Support</li>
        </ul>
        <button class="mt-4 bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">
          Sign Up
        </button>
      </div>

      <!-- Pro Plan -->
      <div class="bg-white rounded-lg shadow-md p-6">
        <h3 class="text-xl font-bold text-green-500 mb-4">Pro</h3>
        <p class="text-4xl font-bold text-gray-800 mb-4">$49<span class="text-xl">/month</span></p>
        <ul class="list-disc list-inside text-gray-600">
          <li>5 Users</li>
          <li>100 GB Storage</li>
          <li>Priority Support</li>
          <li>Advanced Features</li>
        </ul>
        <button class="mt-4 bg-green-500 hover:bg-green-700 text-white font-bold py-2 px-4 rounded">
          Sign Up
        </button>
      </div>

      <!-- Premium Plan -->
      <div class="bg-white rounded-lg shadow-md p-6">
        <h3 class="text-xl font-bold text-purple-500 mb-4">Premium</h3>
        <p class="text-4xl font-bold text-gray-800 mb-4">$99<span class="text-xl">/month</span></p>
        <ul class="list-disc list-inside text-gray-600">
          <li>Unlimited Users</li>
          <li>Unlimited Storage</li>
          <li>Dedicated Support</li>
          <li>All Features</li>
        </ul>
        <button class="mt-4 bg-purple-500 hover:bg-purple-700 text-white font-bold py-2 px-4 rounded">
          Sign Up
        </button>
      </div>
    </div>
  </div>

</body>
</html>
```

**Explanation:**

* **Tailwind Classes:** The code heavily relies on Tailwind CSS utility classes for styling.  Classes like `grid`, `grid-cols`, `bg-white`, `text-xl`, `font-bold`, `rounded-lg`, `shadow-md`, etc., are used to quickly style the elements.  Refer to the Tailwind CSS documentation for a complete list of utility classes.
* **Responsiveness:** The `grid` system with `grid-cols-1 md:grid-cols-3` makes the table responsive. On smaller screens (mobile), it defaults to a single column, and on medium screens and above, it switches to a three-column layout.
* **Hover Effects:** The `hover:bg-blue-700`, `hover:bg-green-700`, and `hover:bg-purple-700` classes add subtle hover effects to the buttons.

**Links to Resources to Learn More:**

* **Tailwind CSS Documentation:** [https://tailwindcss.com/docs](https://tailwindcss.com/docs)
* **Tailwind CSS Cheat Sheet:** [Search for "Tailwind CSS Cheat Sheet" on Google - many helpful resources exist]


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

