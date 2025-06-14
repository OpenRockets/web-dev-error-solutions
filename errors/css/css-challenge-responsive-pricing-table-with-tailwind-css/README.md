# 🐞 CSS Challenge:  Responsive Pricing Table with Tailwind CSS


This challenge involves creating a responsive pricing table using Tailwind CSS. The table should clearly display different pricing plans with their features and costs, adapting seamlessly to different screen sizes.  We'll focus on creating a clean, modern design that is easily understandable and visually appealing.

## Description of the Styling

The pricing table will consist of three distinct pricing plans: Basic, Pro, and Premium. Each plan will be represented by a card containing:

* **Plan Name:** Displayed prominently as a heading.
* **Price:**  Clearly shown with currency symbol.
* **Features:** A bulleted list of included features.
* **Call to Action Button:** A button to subscribe or learn more.

The overall design will use Tailwind's responsive utility classes to ensure the table looks good on desktops, tablets, and mobile devices. We'll aim for a clean, modern aesthetic with subtle shadows and gradients for visual appeal.


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

<div class="container mx-auto p-8">
  <h1 class="text-3xl font-bold text-center mb-8">Choose Your Plan</h1>
  <div class="grid grid-cols-1 md:grid-cols-3 gap-8">

    <!-- Basic Plan -->
    <div class="bg-white shadow-md rounded-lg p-6">
      <h2 class="text-xl font-bold mb-4">Basic</h2>
      <p class="text-4xl font-bold mb-4">$9.99/month</p>
      <ul class="list-disc list-inside mb-4">
        <li>10GB Storage</li>
        <li>1 User</li>
        <li>Basic Support</li>
      </ul>
      <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">
        Subscribe
      </button>
    </div>

    <!-- Pro Plan -->
    <div class="bg-white shadow-md rounded-lg p-6">
      <h2 class="text-xl font-bold mb-4">Pro</h2>
      <p class="text-4xl font-bold mb-4">$29.99/month</p>
      <ul class="list-disc list-inside mb-4">
        <li>50GB Storage</li>
        <li>5 Users</li>
        <li>Priority Support</li>
        <li>Advanced Features</li>
      </ul>
      <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">
        Subscribe
      </button>
    </div>

    <!-- Premium Plan -->
    <div class="bg-white shadow-md rounded-lg p-6">
      <h2 class="text-xl font-bold mb-4">Premium</h2>
      <p class="text-4xl font-bold mb-4">$99.99/month</p>
      <ul class="list-disc list-inside mb-4">
        <li>Unlimited Storage</li>
        <li>Unlimited Users</li>
        <li>Dedicated Support</li>
        <li>All Features</li>
      </ul>
      <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">
        Subscribe
      </button>
    </div>

  </div>
</div>

</body>
</html>
```


## Explanation

The code utilizes Tailwind CSS classes for styling.  `grid` and `grid-cols` handle the responsive layout, adapting to different screen sizes.  Classes like `bg-white`, `shadow-md`, `rounded-lg`, etc., provide the visual styling.  The code is well-structured and easy to understand, making it maintainable and adaptable.


## Links to Resources to Learn More

* **Tailwind CSS Documentation:** [https://tailwindcss.com/docs](https://tailwindcss.com/docs)  - Comprehensive documentation for Tailwind CSS.
* **Tailwind CSS PlayGround:** [https://play.tailwindcss.com/](https://play.tailwindcss.com/) - Interactive playground to experiment with Tailwind classes.
* **Learn CSS Grid:** [https://css-tricks.com/snippets/css/complete-guide-grid/](https://css-tricks.com/snippets/css/complete-guide-grid/) - A good resource for learning about CSS Grid, which is used in this example.


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

