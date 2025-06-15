# 🐞 CSS Challenge:  Responsive Pricing Table with Tailwind CSS


This challenge involves creating a responsive pricing table using Tailwind CSS.  The table will display three different pricing plans (Basic, Pro, and Premium) with their respective features and prices.  The design should be clean, modern, and adapt seamlessly to different screen sizes.  We'll utilize Tailwind's utility classes for efficient and rapid styling.


**Description of the Styling:**

The pricing table will be structured as a grid, with each plan occupying a column. Each plan will have a card-like appearance with a header showing the plan name, a list of features, the price, and a call-to-action button.  We will use Tailwind's responsive modifiers to ensure appropriate spacing and layout on various screen sizes (e.g., mobile, tablet, desktop).  A subtle shadow and hover effect will be added to enhance the visual appeal.


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
  <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
    <!-- Basic Plan -->
    <div class="bg-white shadow-md rounded-lg p-6">
      <h2 class="text-xl font-bold mb-4">Basic</h2>
      <ul class="list-disc list-inside mb-4">
        <li>10GB Storage</li>
        <li>1 User</li>
        <li>Basic Support</li>
      </ul>
      <p class="text-2xl font-bold mb-4">$9/month</p>
      <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">Sign Up</button>
    </div>

    <!-- Pro Plan -->
    <div class="bg-white shadow-md rounded-lg p-6">
      <h2 class="text-xl font-bold mb-4">Pro</h2>
      <ul class="list-disc list-inside mb-4">
        <li>100GB Storage</li>
        <li>5 Users</li>
        <li>Priority Support</li>
      </ul>
      <p class="text-2xl font-bold mb-4">$49/month</p>
      <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">Sign Up</button>
    </div>

    <!-- Premium Plan -->
    <div class="bg-white shadow-md rounded-lg p-6">
      <h2 class="text-xl font-bold mb-4">Premium</h2>
      <ul class="list-disc list-inside mb-4">
        <li>Unlimited Storage</li>
        <li>Unlimited Users</li>
        <li>Dedicated Support</li>
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

* **`grid grid-cols-1 md:grid-cols-3 gap-6`:** This creates a responsive grid.  On smaller screens (mobile), it's a single column. On medium screens and larger (tablets and desktops), it becomes a three-column grid with a gap of 6 units between columns.
* **`bg-white shadow-md rounded-lg p-6`:** These are Tailwind classes for background color, shadow, rounded corners, and padding.
* **Other Tailwind classes:**  The code utilizes many other Tailwind classes for typography (`text-3xl`, `font-bold`), lists (`list-disc`, `list-inside`), and button styling.


**Links to Resources to Learn More:**

* **Tailwind CSS Documentation:** [https://tailwindcss.com/docs](https://tailwindcss.com/docs)
* **Learn CSS Grid:** [https://css-tricks.com/snippets/css/complete-guide-grid/](https://css-tricks.com/snippets/css/complete-guide-grid/) (While this example uses Tailwind's grid implementation, understanding CSS Grid is beneficial)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

