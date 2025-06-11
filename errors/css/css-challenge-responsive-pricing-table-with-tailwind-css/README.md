# 🐞 CSS Challenge:  Responsive Pricing Table with Tailwind CSS


This challenge involves creating a responsive pricing table using Tailwind CSS.  The table will feature three different pricing plans (Basic, Pro, and Enterprise), each with its own set of features and a clear visual distinction. The design should be clean, modern, and adapt seamlessly to different screen sizes.

**Description of the Styling:**

The pricing table will use a card-based layout, with each plan occupying its own card.  Tailwind's utility classes will be used extensively for styling, ensuring efficient and maintainable code.  Key styling elements include:

* **Responsive layout:** The table should adjust gracefully to different screen sizes, potentially switching from a three-column layout to a one-column layout on smaller screens.
* **Clear visual distinctions:** Each pricing plan (Basic, Pro, Enterprise) will be visually differentiated using distinct background colors and text styles.
* **Feature list:**  Each plan will have a clearly defined list of features, presented in a consistent and readable manner.
* **Call to action:**  Each plan will include a prominent "Buy Now" button.


**Full Code:**

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

<div class="container mx-auto px-4 py-8">
  <h1 class="text-3xl font-bold text-center mb-8">Choose Your Plan</h1>
  <div class="grid grid-cols-1 md:grid-cols-3 gap-8">

    <!-- Basic Plan -->
    <div class="bg-white shadow-md rounded-lg p-6">
      <h2 class="text-xl font-bold mb-4">Basic</h2>
      <p class="text-gray-700 mb-6 text-2xl font-bold">$9/month</p>
      <ul class="list-disc list-inside mb-6">
        <li>Feature 1</li>
        <li>Feature 2</li>
        <li>Feature 3</li>
      </ul>
      <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">Buy Now</button>
    </div>

    <!-- Pro Plan -->
    <div class="bg-white shadow-md rounded-lg p-6">
      <h2 class="text-xl font-bold mb-4">Pro</h2>
      <p class="text-gray-700 mb-6 text-2xl font-bold">$49/month</p>
      <ul class="list-disc list-inside mb-6">
        <li>Feature 1</li>
        <li>Feature 2</li>
        <li>Feature 3</li>
        <li>Feature 4</li>
        <li>Feature 5</li>
      </ul>
      <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">Buy Now</button>
    </div>

    <!-- Enterprise Plan -->
    <div class="bg-white shadow-md rounded-lg p-6">
      <h2 class="text-xl font-bold mb-4">Enterprise</h2>
      <p class="text-gray-700 mb-6 text-2xl font-bold">$99/month</p>
      <ul class="list-disc list-inside mb-6">
        <li>Feature 1</li>
        <li>Feature 2</li>
        <li>Feature 3</li>
        <li>Feature 4</li>
        <li>Feature 5</li>
        <li>Feature 6</li>
        <li>Feature 7</li>
      </ul>
      <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">Buy Now</button>
    </div>
  </div>
</div>

</body>
</html>
```

**Explanation:**

The code uses Tailwind CSS's grid system (`grid grid-cols-1 md:grid-cols-3`) to create a responsive layout.  On smaller screens (mobile), it defaults to a single column. On medium and larger screens (tablets and desktops), it switches to a three-column layout.  Other Tailwind classes handle styling like background colors, shadows, padding, margins, text styles, and button styling.  The `hover` modifier adds interactive effects.

**Links to Resources to Learn More:**

* **Tailwind CSS Documentation:** [https://tailwindcss.com/docs](https://tailwindcss.com/docs)
* **Tailwind CSS Cheat Sheet:**  Search for "Tailwind CSS Cheat Sheet" on Google for numerous helpful resources.


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

