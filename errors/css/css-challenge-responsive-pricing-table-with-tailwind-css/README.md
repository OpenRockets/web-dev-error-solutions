# 🐞 CSS Challenge: Responsive Pricing Table with Tailwind CSS


This challenge involves creating a responsive pricing table using Tailwind CSS. The table should display three different pricing plans (Basic, Pro, and Premium) with clear visual distinctions and responsiveness across various screen sizes.  We'll leverage Tailwind's utility classes for efficient styling.

**Description of the Styling:**

The pricing table will consist of three columns, each representing a pricing plan. Each column will contain:

* **Plan Name:** (e.g., Basic, Pro, Premium) displayed prominently.
* **Price:**  Clearly shown with the currency symbol.
* **Features:** A bulleted list of features included in each plan.
* **Button:** A call-to-action button (e.g., "Choose Plan")

The styling will emphasize visual clarity and separation between plans using Tailwind's spacing, color, and border utilities.  Responsiveness will be achieved using Tailwind's breakpoint modifiers.


**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<script src="https://cdn.tailwindcss.com"></script>
<title>Responsive Pricing Table</title>
</head>
<body class="bg-gray-100">

<div class="container mx-auto p-8">
  <h2 class="text-3xl font-bold mb-8 text-center">Pricing Plans</h2>
  <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
    <!-- Basic Plan -->
    <div class="bg-white shadow-md rounded-lg p-6">
      <h3 class="text-xl font-bold mb-4">Basic</h3>
      <p class="text-4xl font-bold mb-4 text-blue-500">$9<span class="text-base">/month</span></p>
      <ul class="list-disc list-inside mb-6">
        <li>10GB Storage</li>
        <li>1 User</li>
        <li>Basic Support</li>
      </ul>
      <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">Choose Plan</button>
    </div>

    <!-- Pro Plan -->
    <div class="bg-white shadow-md rounded-lg p-6">
      <h3 class="text-xl font-bold mb-4">Pro</h3>
      <p class="text-4xl font-bold mb-4 text-blue-500">$29<span class="text-base">/month</span></p>
      <ul class="list-disc list-inside mb-6">
        <li>100GB Storage</li>
        <li>5 Users</li>
        <li>Priority Support</li>
        <li>Advanced Features</li>
      </ul>
      <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">Choose Plan</button>
    </div>

    <!-- Premium Plan -->
    <div class="bg-white shadow-md rounded-lg p-6">
      <h3 class="text-xl font-bold mb-4">Premium</h3>
      <p class="text-4xl font-bold mb-4 text-blue-500">$99<span class="text-base">/month</span></p>
      <ul class="list-disc list-inside mb-6">
        <li>Unlimited Storage</li>
        <li>10 Users</li>
        <li>Dedicated Support</li>
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

The code utilizes Tailwind's grid system (`grid`, `grid-cols`, `gap`) for layout.  Classes like `bg-white`, `shadow-md`, `rounded-lg`, `p-6`, `text-xl`, `font-bold`, etc., handle styling. Breakpoints (`md:grid-cols-3`) ensure responsiveness.  The code is well-structured and easy to understand, demonstrating the power and efficiency of Tailwind CSS.

**Links to Resources to Learn More:**

* **Tailwind CSS Documentation:** [https://tailwindcss.com/docs](https://tailwindcss.com/docs)
* **Tailwind CSS Cheat Sheet:** [Many available online, search "Tailwind CSS Cheat Sheet"]


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

