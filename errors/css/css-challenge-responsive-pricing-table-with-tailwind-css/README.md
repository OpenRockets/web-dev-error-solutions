# 🐞 CSS Challenge: Responsive Pricing Table with Tailwind CSS


This challenge involves creating a responsive pricing table using Tailwind CSS. The table will feature three pricing plans (Basic, Pro, and Enterprise) with different pricing and features.  The design should be clean, modern, and adapt seamlessly to different screen sizes.

**Description of the Styling:**

The pricing table will use cards for each plan, arranged horizontally on larger screens and vertically on smaller screens.  Each card will include:

* **Plan Name:** (e.g., Basic, Pro, Enterprise) displayed prominently.
* **Price:**  Clearly shown with the currency symbol.
* **Feature List:** A bulleted list of included features.
* **Call to Action Button:** A button to select the plan (e.g., "Choose Plan").

Tailwind's responsive modifiers will be used to adjust the layout based on screen size.  We'll leverage Tailwind's utility classes for styling elements like padding, margins, text size, colors, and button styles.


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

  <div class="container mx-auto px-4 py-8">
    <h2 class="text-3xl font-bold text-center mb-8">Choose Your Plan</h2>
    <div class="grid grid-cols-1 md:grid-cols-3 gap-6">

      <!-- Basic Plan -->
      <div class="bg-white rounded-lg shadow-md p-6">
        <h3 class="text-xl font-bold mb-4">Basic</h3>
        <p class="text-4xl font-bold text-blue-500 mb-4">$9</p>
        <ul class="list-disc list-inside mb-4">
          <li>10GB Storage</li>
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
          <li>100GB Storage</li>
          <li>5 Users</li>
          <li>Priority Support</li>
          <li>Advanced Features</li>
        </ul>
        <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">Choose Plan</button>
      </div>

      <!-- Enterprise Plan -->
      <div class="bg-white rounded-lg shadow-md p-6">
        <h3 class="text-xl font-bold mb-4">Enterprise</h3>
        <p class="text-4xl font-bold text-blue-500 mb-4">$99</p>
        <ul class="list-disc list-inside mb-4">
          <li>Unlimited Storage</li>
          <li>Unlimited Users</li>
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

The code utilizes Tailwind's grid system (`grid`, `grid-cols`, `gap`) for responsive layout.  The `md:grid-cols-3` class ensures three columns on medium-sized screens and above.  Other classes handle styling like background color (`bg-white`), shadows (`shadow-md`), padding (`p-6`), text styles (`text-xl`, `font-bold`), and button styles.  The responsive behavior is inherent in Tailwind's class names.


**Links to Resources to Learn More:**

* **Tailwind CSS Documentation:** [https://tailwindcss.com/docs](https://tailwindcss.com/docs)
* **Tailwind CSS Grid System:** [https://tailwindcss.com/docs/grid](https://tailwindcss.com/docs/grid)
* **Learn CSS Grid:** [https://css-tricks.com/snippets/css/complete-guide-grid/](https://css-tricks.com/snippets/css/complete-guide-grid/) (for a deeper understanding of the underlying grid concept)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

