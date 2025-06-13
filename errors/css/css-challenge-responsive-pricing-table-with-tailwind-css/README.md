# 🐞 CSS Challenge:  Responsive Pricing Table with Tailwind CSS


This challenge focuses on creating a responsive pricing table using Tailwind CSS.  The goal is to build a clean, visually appealing table that adapts seamlessly to different screen sizes.  We'll use Tailwind's utility classes to style the table efficiently and ensure responsiveness.

## Description of the Styling

The pricing table will consist of three columns representing different pricing plans (e.g., Basic, Pro, Premium). Each column will include:

*   A plan title (e.g., "Basic").
*   A price (e.g., "$9/month").
*   A list of features included in the plan.
*   A call-to-action button (e.g., "Sign Up").

The styling will incorporate:

*   Clean and modern design.
*   Responsive layout adapting to different screen sizes (using Tailwind's responsive modifiers).
*   Clear visual separation between pricing plans.
*   Consistent font sizes and colors.
*   Visually appealing buttons.


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
  <h2 class="text-3xl font-bold mb-8 text-center">Choose Your Plan</h2>
  <div class="grid grid-cols-1 md:grid-cols-3 gap-8">

    <!-- Basic Plan -->
    <div class="bg-white rounded-lg shadow-md p-6">
      <h3 class="text-xl font-bold mb-4 text-center">Basic</h3>
      <p class="text-4xl font-bold text-center mb-4">$9<span class="text-base">/month</span></p>
      <ul class="list-disc list-inside mb-4">
        <li>10GB Storage</li>
        <li>1 User</li>
        <li>Email Support</li>
      </ul>
      <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">Sign Up</button>
    </div>

    <!-- Pro Plan -->
    <div class="bg-white rounded-lg shadow-md p-6">
      <h3 class="text-xl font-bold mb-4 text-center">Pro</h3>
      <p class="text-4xl font-bold text-center mb-4">$29<span class="text-base">/month</span></p>
      <ul class="list-disc list-inside mb-4">
        <li>50GB Storage</li>
        <li>5 Users</li>
        <li>Priority Email Support</li>
        <li>Chat Support</li>
      </ul>
      <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">Sign Up</button>
    </div>

    <!-- Premium Plan -->
    <div class="bg-white rounded-lg shadow-md p-6">
      <h3 class="text-xl font-bold mb-4 text-center">Premium</h3>
      <p class="text-4xl font-bold text-center mb-4">$99<span class="text-base">/month</span></p>
      <ul class="list-disc list-inside mb-4">
        <li>Unlimited Storage</li>
        <li>10 Users</li>
        <li>24/7 Support</li>
        <li>Dedicated Account Manager</li>
      </ul>
      <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">Sign Up</button>
    </div>

  </div>
</div>

</body>
</html>
```

## Explanation

The code utilizes Tailwind CSS's grid system (`grid grid-cols-1 md:grid-cols-3`) to create a responsive layout.  On smaller screens (mobile), the pricing plans are stacked vertically. On medium screens and larger (desktops), they are arranged in three columns.  Other Tailwind classes handle styling like background colors, shadows, spacing, text styles, and button appearance.  The code is well-structured and easy to understand thanks to Tailwind's intuitive class names.


## Links to Resources to Learn More

*   **Tailwind CSS Official Documentation:** [https://tailwindcss.com/docs](https://tailwindcss.com/docs)  This is the primary resource for learning about Tailwind CSS and its utility classes.
*   **Learn CSS Grid:** [https://css-tricks.com/snippets/css/complete-guide-grid/](https://css-tricks.com/snippets/css/complete-guide-grid/) (While the example uses Tailwind's grid implementation, understanding CSS Grid is beneficial.)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

