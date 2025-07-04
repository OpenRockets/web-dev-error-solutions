# 🐞 CSS Challenge:  Building a Simple Pricing Table with Tailwind CSS


This challenge focuses on building a clean and responsive pricing table using Tailwind CSS.  The goal is to create three pricing tiers (Basic, Pro, and Enterprise) with distinct features and pricing, all while maintaining a consistent and visually appealing design. We'll leverage Tailwind's utility classes for efficient styling.


**Description of the Styling:**

The pricing table will consist of three columns, each representing a different pricing tier. Each column will include:

* A title (e.g., "Basic," "Pro," "Enterprise")
* A price displayed prominently.
* A list of features offered in that tier.
* A call-to-action button (e.g., "Get Started").

The styling will emphasize clean lines, clear visual separation between tiers, and a modern aesthetic achieved through Tailwind's pre-built classes.  We'll utilize responsive design principles to ensure the table adapts gracefully to different screen sizes.


**Full Code:**

```html
<div class="bg-gray-100 p-8 rounded-lg shadow-md">
  <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
    <div class="bg-white rounded-lg shadow-md p-6">
      <h3 class="text-2xl font-bold mb-4">Basic</h3>
      <p class="text-4xl font-bold text-gray-800 mb-4">$9/month</p>
      <ul class="text-gray-600">
        <li>Feature 1</li>
        <li>Feature 2</li>
        <li>Feature 3</li>
      </ul>
      <button class="mt-4 bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">Get Started</button>
    </div>
    <div class="bg-white rounded-lg shadow-md p-6">
      <h3 class="text-2xl font-bold mb-4">Pro</h3>
      <p class="text-4xl font-bold text-gray-800 mb-4">$49/month</p>
      <ul class="text-gray-600">
        <li>Feature 1</li>
        <li>Feature 2</li>
        <li>Feature 3</li>
        <li>Feature 4</li>
        <li>Feature 5</li>
      </ul>
      <button class="mt-4 bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">Get Started</button>
    </div>
    <div class="bg-white rounded-lg shadow-md p-6">
      <h3 class="text-2xl font-bold mb-4">Enterprise</h3>
      <p class="text-4xl font-bold text-gray-800 mb-4">$99/month</p>
      <ul class="text-gray-600">
        <li>Feature 1</li>
        <li>Feature 2</li>
        <li>Feature 3</li>
        <li>Feature 4</li>
        <li>Feature 5</li>
        <li>Feature 6</li>
        <li>Feature 7</li>
      </ul>
      <button class="mt-4 bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">Get Started</button>
    </div>
  </div>
</div>
```

**Explanation:**

The code utilizes Tailwind's grid system (`grid`, `grid-cols`, `gap`) for layout.  Classes like `bg-white`, `rounded-lg`, `shadow-md`, `text-2xl`, `font-bold`, etc., handle styling.  The `hover` modifier adds interactivity to the buttons.  Media queries (implicitly handled by Tailwind's responsive modifiers like `md:grid-cols-3`)  ensure the table adapts to different screen sizes.


**Links to Resources to Learn More:**

* **Tailwind CSS Documentation:** [https://tailwindcss.com/docs/](https://tailwindcss.com/docs/)  (Official documentation – highly recommended)
* **Tailwind CSS Cheat Sheet:**  Search for "Tailwind CSS Cheat Sheet" on Google – many helpful cheat sheets are available.


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

