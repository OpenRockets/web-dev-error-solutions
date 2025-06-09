# 🐞 CSS Challenge:  Responsive Pricing Table with Tailwind CSS


This challenge focuses on building a responsive pricing table using Tailwind CSS.  The goal is to create a clean, visually appealing table that adapts seamlessly to different screen sizes.  We'll utilize Tailwind's utility classes to streamline the styling process.

**Description of the Styling:**

The pricing table will feature three pricing tiers: Basic, Pro, and Premium. Each tier will have its own card displaying the plan name, price, features (using a bulleted list), and a call-to-action button.  The table will be responsive, adjusting its layout to remain user-friendly on both large and small screens. We'll use Tailwind's built-in responsive modifiers to achieve this.  The design will prioritize clarity and readability.


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
    <h2 class="text-3xl font-bold text-center mb-8">Choose Your Plan</h2>
    <div class="grid grid-cols-1 sm:grid-cols-3 gap-8">

      <div class="bg-white shadow-md rounded-lg p-6">
        <h3 class="text-xl font-bold mb-4 text-center">Basic</h3>
        <p class="text-4xl font-bold text-center mb-4">$9<span class="text-base">/month</span></p>
        <ul class="list-disc list-inside mb-4">
          <li>1 User</li>
          <li>10 GB Storage</li>
          <li>Basic Support</li>
        </ul>
        <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">Sign Up</button>
      </div>

      <div class="bg-white shadow-md rounded-lg p-6">
        <h3 class="text-xl font-bold mb-4 text-center">Pro</h3>
        <p class="text-4xl font-bold text-center mb-4">$49<span class="text-base">/month</span></p>
        <ul class="list-disc list-inside mb-4">
          <li>5 Users</li>
          <li>100 GB Storage</li>
          <li>Priority Support</li>
          <li>Advanced Features</li>
        </ul>
        <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">Sign Up</button>
      </div>

      <div class="bg-white shadow-md rounded-lg p-6">
        <h3 class="text-xl font-bold mb-4 text-center">Premium</h3>
        <p class="text-4xl font-bold text-center mb-4">$99<span class="text-base">/month</span></p>
        <ul class="list-disc list-inside mb-4">
          <li>Unlimited Users</li>
          <li>Unlimited Storage</li>
          <li>Dedicated Support</li>
          <li>All Features</li>
        </ul>
        <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">Sign Up</button>
      </div>

    </div>
  </div>

</body>
</html>
```

**Explanation:**

* **`grid` and `grid-cols`:**  These Tailwind classes create a responsive grid layout.  `grid-cols-1` makes it a single column by default, while `sm:grid-cols-3` switches to three columns on small screens and up (using Tailwind's responsive modifiers).
* **`bg-white`, `shadow-md`, `rounded-lg`, etc.:** These are utility classes for background color, shadow, rounded corners, and padding.
* **`text-3xl`, `font-bold`, etc.:** These control text size, font weight, and other text styles.
* **Responsive Modifiers:** The `sm:` prefix in `sm:grid-cols-3` makes the styling apply only to screens with a minimum width of 640px (the `sm` breakpoint in Tailwind's default configuration).


**Links to Resources to Learn More:**

* **Tailwind CSS Documentation:** [https://tailwindcss.com/docs](https://tailwindcss.com/docs)
* **Tailwind CSS Grid System:** [https://tailwindcss.com/docs/grid](https://tailwindcss.com/docs/grid)
* **Learn CSS Grid:** [https://css-tricks.com/snippets/css/complete-guide-grid/](https://css-tricks.com/snippets/css/complete-guide-grid/) (Helpful for understanding the underlying concepts)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

