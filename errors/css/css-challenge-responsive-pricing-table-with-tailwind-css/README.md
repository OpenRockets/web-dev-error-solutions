# 🐞 CSS Challenge: Responsive Pricing Table with Tailwind CSS


This challenge involves creating a responsive pricing table using Tailwind CSS.  The table should display three pricing plans (Basic, Pro, and Enterprise) with different features and prices, adapting seamlessly to various screen sizes.  We'll use Tailwind's utility classes for efficient and rapid styling.


## Description of the Styling

The pricing table will be structured using a card-like design. Each plan will have its own card containing:

* **Plan Name:**  Displayed prominently as a heading.
* **Price:** Clearly shown with the currency symbol.
* **Features:** A bulleted list of included features.
* **Button:** A call to action button ("Choose Plan").

The table will be responsive, adjusting its layout smoothly from desktop to mobile views, potentially switching from a three-column layout to a one-column layout.  We'll employ Tailwind's responsive modifiers (`md:`, `lg:`, etc.) to achieve this.  A consistent visual style will be maintained across all plans and screen sizes using Tailwind's pre-defined styles.


## Full Code

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

  <div class="container mx-auto px-4 py-10">
    <h1 class="text-3xl font-bold text-center mb-10">Choose Your Plan</h1>
    <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
      <!-- Basic Plan -->
      <div class="bg-white rounded-lg shadow-md p-6">
        <h2 class="text-xl font-bold mb-4">Basic</h2>
        <p class="text-4xl font-bold mb-4">$9<span class="text-base">/month</span></p>
        <ul class="list-disc list-inside mb-4">
          <li>1 User</li>
          <li>10 GB Storage</li>
          <li>Basic Support</li>
        </ul>
        <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">Choose Plan</button>
      </div>

      <!-- Pro Plan -->
      <div class="bg-white rounded-lg shadow-md p-6">
        <h2 class="text-xl font-bold mb-4">Pro</h2>
        <p class="text-4xl font-bold mb-4">$49<span class="text-base">/month</span></p>
        <ul class="list-disc list-inside mb-4">
          <li>5 Users</li>
          <li>100 GB Storage</li>
          <li>Priority Support</li>
          <li>Advanced Features</li>
        </ul>
        <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">Choose Plan</button>
      </div>

      <!-- Enterprise Plan -->
      <div class="bg-white rounded-lg shadow-md p-6">
        <h2 class="text-xl font-bold mb-4">Enterprise</h2>
        <p class="text-4xl font-bold mb-4">$99<span class="text-base">/month</span></p>
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


## Explanation

The code utilizes Tailwind's grid system (`grid`, `grid-cols`, `gap`) to create the responsive layout.  The `md:grid-cols-3` class ensures a three-column layout on medium-sized screens and above.  On smaller screens, it defaults to a single column.  Other Tailwind classes handle styling aspects like background color, padding, shadows, text styles, and button styling.  The responsive behavior is handled implicitly by Tailwind's built-in responsiveness.


## Resources to Learn More

* **Tailwind CSS Documentation:** [https://tailwindcss.com/docs](https://tailwindcss.com/docs)  - The official Tailwind CSS documentation is an excellent resource for learning about all its features and utility classes.
* **Tailwind CSS Cheat Sheet:** Search online for "Tailwind CSS cheat sheet" to find readily available quick-reference guides.
* **CSS Grid Layout:** [https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout) - Understanding CSS Grid will enhance your ability to create complex layouts.


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

