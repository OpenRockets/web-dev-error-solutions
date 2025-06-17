# 🐞 CSS Challenge:  Building a Simple Pricing Table with Tailwind CSS


This challenge focuses on creating a clean and responsive pricing table using Tailwind CSS.  The goal is to build a table with three different pricing plans, each with its own features and price, presented in a visually appealing and easy-to-understand manner. We'll use Tailwind's utility classes for rapid development and responsive design.


**Description of the Styling:**

The pricing table will be structured as a grid, with each plan occupying its own column. Each plan will have a card-like structure, containing a header (plan name), a list of features, a price, and a call-to-action button. We will employ Tailwind's responsive design capabilities to ensure the table looks good on various screen sizes.  The design will aim for a modern, clean aesthetic, using a consistent color palette and spacing.


**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Pricing Table</title>
  <script src="https://cdn.tailwindcss.com"></script>
</head>
<body class="bg-gray-100">

  <div class="container mx-auto py-12 px-4">
    <h2 class="text-3xl font-bold text-center mb-8">Choose Your Plan</h2>
    <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
      <!-- Plan 1 -->
      <div class="bg-white shadow-md rounded-lg p-6">
        <h3 class="text-xl font-bold mb-4">Basic</h3>
        <ul class="list-disc list-inside mb-4">
          <li>10GB Storage</li>
          <li>1 User</li>
          <li>Basic Support</li>
        </ul>
        <p class="text-2xl font-bold text-blue-500 mb-4">$9/month</p>
        <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">
          Sign Up
        </button>
      </div>

      <!-- Plan 2 -->
      <div class="bg-white shadow-md rounded-lg p-6">
        <h3 class="text-xl font-bold mb-4">Pro</h3>
        <ul class="list-disc list-inside mb-4">
          <li>50GB Storage</li>
          <li>5 Users</li>
          <li>Priority Support</li>
        </ul>
        <p class="text-2xl font-bold text-blue-500 mb-4">$49/month</p>
        <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">
          Sign Up
        </button>
      </div>

      <!-- Plan 3 -->
      <div class="bg-white shadow-md rounded-lg p-6">
        <h3 class="text-xl font-bold mb-4">Enterprise</h3>
        <ul class="list-disc list-inside mb-4">
          <li>Unlimited Storage</li>
          <li>Unlimited Users</li>
          <li>Dedicated Support</li>
        </ul>
        <p class="text-2xl font-bold text-blue-500 mb-4">$99/month</p>
        <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">
          Sign Up
        </button>
      </div>
    </div>
  </div>

</body>
</html>
```

**Explanation:**

The code utilizes Tailwind's grid system (`grid`, `grid-cols`, `gap`) to create the three-column layout.  The `bg-white`, `shadow-md`, `rounded-lg`, and `p-6` classes style each plan card.  Heading styles are controlled with `text-xl`, `font-bold`, etc.  Lists are styled using `list-disc` and `list-inside`.  The buttons use `bg-blue-500`, `hover:bg-blue-700`, etc., for styling and hover effects.  Responsiveness is achieved using Tailwind's media query features implicitly built into the grid system.  The `md:grid-cols-3` class changes the grid layout to three columns on medium-sized screens and above, adapting to smaller screens automatically.


**Links to Resources to Learn More:**

* **Tailwind CSS Official Documentation:** [https://tailwindcss.com/docs](https://tailwindcss.com/docs)
* **Tailwind CSS Grid System:** [https://tailwindcss.com/docs/grid](https://tailwindcss.com/docs/grid)
* **Learn CSS Grid:** [https://css-tricks.com/snippets/css/complete-guide-grid/](https://css-tricks.com/snippets/css/complete-guide-grid/) (General CSS Grid info, helpful even if using Tailwind)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

