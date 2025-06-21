# 🐞 CSS Challenge: Responsive Pricing Table with Tailwind CSS


This challenge involves creating a responsive pricing table using Tailwind CSS. The table should display three different pricing plans (Basic, Pro, and Premium) with their respective features and prices.  The design should be clean, visually appealing, and adapt seamlessly to different screen sizes.


## Styling Description

The pricing table will be structured using Tailwind's grid system for easy layout management. Each pricing plan will be represented by a card with a distinct background color.  Key features will be listed using unordered lists, and the price will be prominently displayed.  Hover effects will be added for an interactive experience.  Responsiveness will be achieved using Tailwind's responsive modifiers.


## Full Code

```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Responsive Pricing Table</title>
  <link href="https://cdn.jsdelivr.net/npm/tailwindcss@2.2.19/dist/tailwind.min.css" rel="stylesheet">
</head>
<body class="bg-gray-100">

  <div class="container mx-auto px-4 py-8">
    <h1 class="text-3xl font-bold text-center mb-8">Pricing Plans</h1>

    <div class="grid grid-cols-1 md:grid-cols-3 gap-8">

      <div class="bg-white shadow-md rounded-lg p-6">
        <h2 class="text-xl font-bold mb-4 text-center">Basic</h2>
        <p class="text-center text-gray-600 mb-6">Perfect for beginners</p>
        <p class="text-4xl font-bold text-center text-blue-500 mb-4">$9<span class="text-base">/month</span></p>
        <ul class="list-disc list-inside">
          <li>1GB Storage</li>
          <li>1 User</li>
          <li>Limited Support</li>
        </ul>
        <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded mt-4">Sign Up</button>
      </div>

      <div class="bg-white shadow-md rounded-lg p-6">
        <h2 class="text-xl font-bold mb-4 text-center">Pro</h2>
        <p class="text-center text-gray-600 mb-6">For growing businesses</p>
        <p class="text-4xl font-bold text-center text-green-500 mb-4">$49<span class="text-base">/month</span></p>
        <ul class="list-disc list-inside">
          <li>10GB Storage</li>
          <li>5 Users</li>
          <li>Priority Support</li>
          <li>Advanced Features</li>
        </ul>
        <button class="bg-green-500 hover:bg-green-700 text-white font-bold py-2 px-4 rounded mt-4">Sign Up</button>
      </div>

      <div class="bg-white shadow-md rounded-lg p-6">
        <h2 class="text-xl font-bold mb-4 text-center">Premium</h2>
        <p class="text-center text-gray-600 mb-6">Ultimate power for enterprises</p>
        <p class="text-4xl font-bold text-center text-purple-500 mb-4">$99<span class="text-base">/month</span></p>
        <ul class="list-disc list-inside">
          <li>Unlimited Storage</li>
          <li>Unlimited Users</li>
          <li>24/7 Support</li>
          <li>All Features Included</li>
        </ul>
        <button class="bg-purple-500 hover:bg-purple-700 text-white font-bold py-2 px-4 rounded mt-4">Sign Up</button>
      </div>

    </div>
  </div>

</body>
</html>
```


## Explanation

The code utilizes Tailwind's pre-defined classes to style the elements quickly.  `grid` and `grid-cols` create the responsive grid layout.  Classes like `bg-white`, `shadow-md`, `rounded-lg`, and `p-6` handle basic styling.  Text sizes and colors are controlled using classes like `text-3xl`, `font-bold`, `text-center`, `text-blue-500`, etc.  Hover effects are implemented using `hover` modifiers.  The responsive behavior is managed implicitly by Tailwind's responsive modifiers (e.g., `md:grid-cols-3`).


## Resources to Learn More

* **Tailwind CSS Official Website:** [https://tailwindcss.com/](https://tailwindcss.com/) - The official documentation for Tailwind CSS.  This is your primary resource for learning all aspects of the framework.
* **Tailwind CSS Cheat Sheet:**  Search online for "Tailwind CSS Cheat Sheet" – Many helpful cheat sheets are available to quickly look up classes.
* **Learn CSS Grid:** Search online for "Learn CSS Grid" to understand the fundamentals of CSS Grid, which Tailwind leverages for layout.



Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

