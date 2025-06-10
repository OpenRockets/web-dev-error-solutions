# 🐞 CSS Challenge:  Responsive Pricing Table with Tailwind CSS


This challenge focuses on building a responsive pricing table using Tailwind CSS. The table will display three different pricing plans (Basic, Pro, and Premium) with their respective features and prices.  The design emphasizes clarity, readability, and responsiveness across various screen sizes.

**Description of the Styling:**

The pricing table will be structured as a card with three columns representing the different plans. Each plan will have a distinct background color (subtle variations). Key features will be listed using a bullet point list. The price will be prominently displayed, using larger font size and a different color.  The call-to-action button will be styled to be visually appealing and easily clickable.  Responsiveness ensures the table adapts gracefully to smaller screens, possibly stacking the columns vertically on mobile.


**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Pricing Table</title>
  <link href="https://cdn.jsdelivr.net/npm/tailwindcss@2.2.19/dist/tailwind.min.css" rel="stylesheet">
</head>
<body class="bg-gray-100">
  <div class="container mx-auto p-8">
    <h1 class="text-3xl font-bold mb-8 text-center">Pricing Plans</h1>
    <div class="bg-white shadow-md rounded-lg overflow-hidden">
      <div class="flex flex-col md:flex-row">
        <div class="p-6 border-r border-gray-200 md:w-1/3">
          <h2 class="text-xl font-semibold mb-4">Basic</h2>
          <p class="text-gray-700 mb-6">Perfect for individuals</p>
          <ul class="list-disc list-inside mb-6">
            <li>1 User</li>
            <li>10 GB Storage</li>
            <li>Basic Support</li>
          </ul>
          <p class="text-2xl font-bold text-blue-600 mb-4">$9/month</p>
          <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">
            Sign Up
          </button>
        </div>
        <div class="p-6 border-r border-gray-200 md:w-1/3 bg-gray-50">
          <h2 class="text-xl font-semibold mb-4">Pro</h2>
          <p class="text-gray-700 mb-6">Ideal for small teams</p>
          <ul class="list-disc list-inside mb-6">
            <li>5 Users</li>
            <li>50 GB Storage</li>
            <li>Priority Support</li>
          </ul>
          <p class="text-2xl font-bold text-blue-600 mb-4">$49/month</p>
          <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">
            Sign Up
          </button>
        </div>
        <div class="p-6 md:w-1/3">
          <h2 class="text-xl font-semibold mb-4">Premium</h2>
          <p class="text-gray-700 mb-6">Best for large organizations</p>
          <ul class="list-disc list-inside mb-6">
            <li>Unlimited Users</li>
            <li>Unlimited Storage</li>
            <li>Dedicated Support</li>
          </ul>
          <p class="text-2xl font-bold text-blue-600 mb-4">$99/month</p>
          <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">
            Sign Up
          </button>
        </div>
      </div>
    </div>
  </div>
</body>
</html>
```

**Explanation:**

The code utilizes Tailwind CSS classes for styling.  `flex` and `flex-col`/`flex-row` control the layout, making it responsive.  `md:w-1/3` sets the width to one-third on medium screens and above, while it stacks vertically on smaller screens.  Classes like `bg-white`, `shadow-md`, `rounded-lg`, `p-6`, and others handle background, shadow, border-radius, padding, and other visual aspects. The use of utility classes makes the code concise and readable.


**Links to Resources to Learn More:**

* **Tailwind CSS Documentation:** [https://tailwindcss.com/docs](https://tailwindcss.com/docs)  - The official documentation is an excellent resource to learn about all the utility classes.
* **Learn CSS Grid:** [https://css-tricks.com/snippets/css/complete-guide-grid/](https://css-tricks.com/snippets/css/complete-guide-grid/) - While not used here extensively, understanding CSS Grid is helpful for more advanced layouts.
* **Learn Responsive Design:** [https://developer.mozilla.org/en-US/docs/Learn/Responsive_web_design](https://developer.mozilla.org/en-US/docs/Learn/Responsive_web_design) - Understanding responsive design principles is crucial for creating websites that work well on all devices.


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

