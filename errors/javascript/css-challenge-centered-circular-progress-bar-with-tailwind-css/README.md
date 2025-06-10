# 🐞 CSS Challenge:  Centered Circular Progress Bar with Tailwind CSS


This challenge involves creating a visually appealing circular progress bar centered on the page using Tailwind CSS.  The progress bar should be visually dynamic, clearly showing the percentage complete.  We'll utilize Tailwind's utility classes for efficient styling and layout.


**Description of the Styling:**

The progress bar will be a circle with a gradient background.  A smaller, inner circle will represent the progress, filled with a solid color that changes based on the percentage. The percentage will be displayed in the center of the inner circle. The overall design aims for a clean, modern aesthetic.


**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Circular Progress Bar</title>
  <script src="https://cdn.tailwindcss.com"></script>
</head>
<body class="bg-gray-100 flex items-center justify-center h-screen">

  <div class="relative w-64 h-64">
    <svg class="absolute top-0 left-0 w-full h-full" viewBox="0 0 100 100">
      <circle cx="50" cy="50" r="40" fill="transparent" stroke="#e0e0e0" stroke-width="10" />
      <circle cx="50" cy="50" r="40" fill="transparent" stroke="linear-gradient(to right, #007bff, #00c853)" stroke-width="10" stroke-dasharray="251.327" stroke-dashoffset="0" id="progress-circle"/>
    </svg>
    <div class="absolute top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2 text-2xl font-bold text-center">
      <span id="percentage">75</span>%
    </div>
  </div>

  <script>
    const percentage = 75; //Change this value to adjust the progress
    const progressCircle = document.getElementById('progress-circle');
    const percentageSpan = document.getElementById('percentage');

    const circumference = 2 * Math.PI * 40;
    progressCircle.style.strokeDashoffset = circumference - (percentage / 100) * circumference;
    percentageSpan.textContent = percentage;
  </script>

</body>
</html>
```


**Explanation:**

* **Tailwind Classes:**  We use Tailwind classes like `bg-gray-100`, `flex`, `items-center`, `justify-center`, `h-screen`, `relative`, `absolute`, `top-0`, `left-0`, `w-full`, `h-full`, `transform`, `-translate-x-1/2`, `-translate-y-1/2`, `text-2xl`, `font-bold`, `text-center` for easy styling and responsive layout.
* **SVG for Progress:** An SVG circle is used to create the progress bar. The outer circle is a light gray, providing the base. The inner circle is dynamically filled based on the percentage.
* **`stroke-dasharray` and `stroke-dashoffset`:** These SVG attributes are key to creating the circular progress effect.  `stroke-dasharray` sets the total length of the dash, and `stroke-dashoffset` controls how much of the dash is hidden, creating the progress.
* **JavaScript for Dynamic Update:** The JavaScript code calculates the `strokeDashoffset` based on the percentage and updates the display.


**Links to Resources to Learn More:**

* **Tailwind CSS Documentation:** [https://tailwindcss.com/docs](https://tailwindcss.com/docs)
* **SVG Tutorial:** [https://developer.mozilla.org/en-US/docs/Web/SVG](https://developer.mozilla.org/en-US/docs/Web/SVG)
* **Understanding `stroke-dasharray` and `stroke-dashoffset`:**  Search for these terms on MDN Web Docs or similar resources for in-depth explanations.


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

