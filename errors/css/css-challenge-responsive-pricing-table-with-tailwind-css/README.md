# 🐞 CSS Challenge: Responsive Pricing Table with Tailwind CSS


This challenge focuses on creating a responsive pricing table using Tailwind CSS.  The table will feature three pricing plans (Basic, Pro, and Premium) with different pricing and features, all displayed neatly and responsively across various screen sizes.  We'll leverage Tailwind's utility classes for efficient and concise styling.

**Description of the Styling:**

The pricing table will be composed of three card-like components, each representing a pricing plan. Each card will contain:

* A plan title (Basic, Pro, Premium).
* A monthly price prominently displayed.
* A list of included features.
* A call-to-action button ("Choose Plan").

The styling will ensure:

* **Responsiveness:** The table adapts gracefully to different screen sizes, stacking vertically on smaller screens.
* **Visual appeal:** Clean design with clear visual hierarchy and consistent spacing.
* **Accessibility:**  Sufficient color contrast and semantic HTML.

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
    <div class="grid grid-cols-1 md:grid-cols-3 gap-8">

      <!-- Basic Plan -->
      <div class="bg-white rounded-lg shadow-md p-6">
        <h3 class="text-xl font-bold mb-4">Basic</h3>
        <p class="text-4xl font-bold text-blue-500 mb-4">$9/month</p>
        <ul class="list-disc list-inside mb-4">
          <li>1 User</li>
          <li>5GB Storage</li>
          <li>Basic Support</li>
        </ul>
        <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">Choose Plan</button>
      </div>

      <!-- Pro Plan -->
      <div class="bg-white rounded-lg shadow-md p-6">
        <h3 class="text-xl font-bold mb-4">Pro</h3>
        <p class="text-4xl font-bold text-blue-500 mb-4">$29/month</p>
        <ul class="list-disc list-inside mb-4">
          <li>5 Users</li>
          <li>50GB Storage</li>
          <li>Priority Support</li>
          <li>Advanced Features</li>
        </ul>
        <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">Choose Plan</button>
      </div>

      <!-- Premium Plan -->
      <div class="bg-white rounded-lg shadow-md p-6">
        <h3 class="text-xl font-bold mb-4">Premium</h3>
        <p class="text-4xl font-bold text-blue-500 mb-4">$99/month</p>
        <ul class="list-disc list-inside mb-4">
          <li>Unlimited Users</li>
          <li>Unlimited Storage</li>
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

The code utilizes Tailwind CSS classes for styling.  `grid` and `grid-cols` handle the responsive layout.  `bg-white`, `rounded-lg`, `shadow-md`, etc., control the appearance.  The `md:grid-cols-3` class ensures that on medium-sized screens and larger, the grid becomes three columns.  The rest of the classes style the text, buttons, and lists.


**Links to Resources to Learn More:**

* **Tailwind CSS Documentation:** [https://tailwindcss.com/docs](https://tailwindcss.com/docs)
* **Learn CSS Grid:** [https://css-tricks.com/snippets/css/complete-guide-grid/](https://css-tricks.com/snippets/css/complete-guide-grid/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

