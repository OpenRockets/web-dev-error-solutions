# 🐞 CSS Challenge:  Responsive Pricing Table with Tailwind CSS


This challenge focuses on creating a responsive pricing table using Tailwind CSS.  The goal is to build a clean, visually appealing table that adapts seamlessly to different screen sizes, offering three different pricing tiers.

**Description of the Styling:**

The pricing table will feature three columns representing different pricing plans (e.g., Basic, Pro, Premium).  Each column will contain:

* **A plan title:**  Clearly labeled (e.g., "Basic", "Pro", "Premium").
* **A price:** Displayed prominently.
* **A list of features:** Bulleted list of included features.
* **A call to action button:**  (e.g., "Choose Plan").

The styling will utilize Tailwind CSS classes for rapid development and responsiveness.  The design will emphasize clear visual separation between plans, good use of whitespace, and a mobile-first approach.


**Full Code:**

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
      <h3 class="text-xl font-bold mb-4">Basic</h3>
      <p class="text-4xl font-bold text-blue-500 mb-4">$9</p>
      <ul class="list-disc list-inside mb-4">
        <li>10 GB Storage</li>
        <li>1 User</li>
        <li>Basic Support</li>
      </ul>
      <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">Choose Plan</button>
    </div>

    <!-- Pro Plan -->
    <div class="bg-white rounded-lg shadow-md p-6">
      <h3 class="text-xl font-bold mb-4">Pro</h3>
      <p class="text-4xl font-bold text-blue-500 mb-4">$49</p>
      <ul class="list-disc list-inside mb-4">
        <li>100 GB Storage</li>
        <li>5 Users</li>
        <li>Priority Support</li>
        <li>Advanced Features</li>
      </ul>
      <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">Choose Plan</button>
    </div>

    <!-- Premium Plan -->
    <div class="bg-white rounded-lg shadow-md p-6">
      <h3 class="text-xl font-bold mb-4">Premium</h3>
      <p class="text-4xl font-bold text-blue-500 mb-4">$99</p>
      <ul class="list-disc list-inside mb-4">
        <li>Unlimited Storage</li>
        <li>10 Users</li>
        <li>24/7 Support</li>
        <li>All Features</li>
      </ul>
      <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">Choose Plan</button>
    </div>
  </div>
</div>

</body>
</html>
```

**Explanation:**

The code uses Tailwind CSS's grid system (`grid grid-cols-1 md:grid-cols-3`) to create a responsive layout.  On smaller screens (mobile), the pricing plans stack vertically.  On medium-sized screens and larger (desktops), they arrange themselves in three columns.  Other classes are used for styling elements like background color, shadows, padding, text sizes, and button styles.  The `hover` modifier adds interactive effects to the buttons.


**Links to Resources to Learn More:**

* **Tailwind CSS Documentation:** [https://tailwindcss.com/docs](https://tailwindcss.com/docs)
* **Learn CSS Grid:** [https://css-tricks.com/snippets/css/complete-guide-grid/](https://css-tricks.com/snippets/css/complete-guide-grid/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

