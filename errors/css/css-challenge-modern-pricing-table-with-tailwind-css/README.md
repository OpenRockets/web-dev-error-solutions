# 🐞 CSS Challenge:  Modern Pricing Table with Tailwind CSS


This challenge involves creating a clean and modern pricing table using Tailwind CSS. The table will feature three pricing plans (Basic, Pro, and Premium) with different features and pricing, clearly displayed in a visually appealing manner.  We'll leverage Tailwind's utility classes to efficiently style the table and maintain consistent design.

**Description of the Styling:**

The pricing table will be responsive, adapting to different screen sizes. Each plan will be contained within a separate card, using Tailwind's card components.  Key features will be presented using a bulleted list.  The pricing will be prominently displayed with a clear visual hierarchy.  A call-to-action button will be included for each plan.  We'll use a clean, modern color palette and appropriate spacing to ensure readability and visual appeal.


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

<div class="container mx-auto p-8">
  <h1 class="text-3xl font-bold mb-8 text-center">Choose Your Plan</h1>
  <div class="grid grid-cols-1 md:grid-cols-3 gap-8">

    <div class="bg-white rounded-lg shadow-md p-6">
      <h2 class="text-xl font-bold mb-4">Basic</h2>
      <p class="text-gray-700 mb-4">Perfect for individuals.</p>
      <p class="text-4xl font-bold text-blue-500 mb-4">$9<span class="text-xl">/month</span></p>
      <ul class="list-disc list-inside text-gray-600">
        <li>1 User</li>
        <li>1 GB Storage</li>
        <li>Basic Support</li>
      </ul>
      <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded mt-4">Sign Up</button>
    </div>

    <div class="bg-white rounded-lg shadow-md p-6">
      <h2 class="text-xl font-bold mb-4">Pro</h2>
      <p class="text-gray-700 mb-4">Best for small teams.</p>
      <p class="text-4xl font-bold text-blue-500 mb-4">$29<span class="text-xl">/month</span></p>
      <ul class="list-disc list-inside text-gray-600">
        <li>5 Users</li>
        <li>5 GB Storage</li>
        <li>Priority Support</li>
        <li>Advanced Features</li>
      </ul>
      <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded mt-4">Sign Up</button>
    </div>

    <div class="bg-white rounded-lg shadow-md p-6">
      <h2 class="text-xl font-bold mb-4">Premium</h2>
      <p class="text-gray-700 mb-4">Suitable for large organizations.</p>
      <p class="text-4xl font-bold text-blue-500 mb-4">$99<span class="text-xl">/month</span></p>
      <ul class="list-disc list-inside text-gray-600">
        <li>Unlimited Users</li>
        <li>Unlimited Storage</li>
        <li>Dedicated Support</li>
        <li>All Features</li>
      </ul>
      <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded mt-4">Sign Up</button>
    </div>

  </div>
</div>

</body>
</html>
```

**Explanation:**

The code utilizes Tailwind CSS classes for layout, styling, and responsiveness.  `grid` and `grid-cols` are used for the responsive three-column layout.  Classes like `bg-white`, `rounded-lg`, `shadow-md`, `text-xl`, `font-bold`, and many others directly style the elements without the need for custom CSS.  This makes the code concise and easy to maintain.  The use of semantic HTML elements further enhances readability and accessibility.


**Links to Resources to Learn More:**

* **Tailwind CSS Official Documentation:** [https://tailwindcss.com/docs](https://tailwindcss.com/docs) - The comprehensive guide to Tailwind CSS.
* **Tailwind CSS Playgrounds:** Various online playgrounds allow you to experiment with Tailwind classes and see the results in real-time.


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

