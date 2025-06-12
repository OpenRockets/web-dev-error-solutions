# 🐞 CSS Challenge:  Responsive Pricing Table with Tailwind CSS


This challenge focuses on building a responsive pricing table using Tailwind CSS.  The goal is to create a clean, visually appealing table that adapts seamlessly to different screen sizes, showcasing three pricing plans with clear distinctions.

**Description of the Styling:**

The pricing table will feature three columns representing different pricing plans (e.g., Basic, Pro, Premium). Each column will include a plan name, a monthly price, a list of features, and a call-to-action button.  We'll use Tailwind's utility classes for responsive design, ensuring the table remains readable on both desktop and mobile devices.  The styling will emphasize visual clarity and hierarchy, using appropriate colors, spacing, and typography.  We'll aim for a modern, clean aesthetic.

**Full Code:**

```html
<div class="container mx-auto p-8">
  <div class="bg-white shadow-md rounded-lg overflow-hidden">
    <table class="w-full border-collapse">
      <thead>
        <tr>
          <th class="p-4 bg-gray-100 text-left text-gray-600 font-medium">Plan</th>
          <th class="p-4 bg-gray-100 text-center text-gray-600 font-medium">Price</th>
          <th class="p-4 bg-gray-100 text-center text-gray-600 font-medium">Features</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td class="p-4 border-b border-gray-200">Basic</td>
          <td class="p-4 border-b border-gray-200 text-center">$9/month</td>
          <td class="p-4 border-b border-gray-200">
            <ul class="list-disc list-inside">
              <li>Feature 1</li>
              <li>Feature 2</li>
            </ul>
          </td>
        </tr>
        <tr>
          <td class="p-4 border-b border-gray-200">Pro</td>
          <td class="p-4 border-b border-gray-200 text-center">$29/month</td>
          <td class="p-4 border-b border-gray-200">
            <ul class="list-disc list-inside">
              <li>Feature 1</li>
              <li>Feature 2</li>
              <li>Feature 3</li>
              <li>Feature 4</li>
            </ul>
          </td>
        </tr>
        <tr>
          <td class="p-4 border-b border-gray-200">Premium</td>
          <td class="p-4 border-b border-gray-200 text-center">$49/month</td>
          <td class="p-4 border-b border-gray-200">
            <ul class="list-disc list-inside">
              <li>Feature 1</li>
              <li>Feature 2</li>
              <li>Feature 3</li>
              <li>Feature 4</li>
              <li>Feature 5</li>
              <li>Feature 6</li>
            </ul>
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</div>
```


**Explanation:**

* **`container mx-auto p-8`:** Centers the table horizontally and adds padding.
* **`bg-white shadow-md rounded-lg overflow-hidden`:** Styles the container with a white background, shadow, rounded corners, and prevents content overflow.
* **`w-full`:** Makes the table occupy the full width of its parent container.
* **`border-collapse`:** Collapses the borders of table cells for a cleaner look.
* **`p-4 bg-gray-100 text-left text-gray-600 font-medium`:** Styles the table header cells.
* **`text-center`:** Centers text within cells.
* **`border-b border-gray-200`:** Adds a bottom border to table rows.
* **`list-disc list-inside`:** Styles the unordered lists within the features column.

This code uses Tailwind CSS classes for styling.  Remember to include the Tailwind CSS stylesheet in your project.


**Links to Resources to Learn More:**

* **Tailwind CSS Documentation:** [https://tailwindcss.com/docs](https://tailwindcss.com/docs)
* **MDN Web Docs (CSS):** [https://developer.mozilla.org/en-US/docs/Web/CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

