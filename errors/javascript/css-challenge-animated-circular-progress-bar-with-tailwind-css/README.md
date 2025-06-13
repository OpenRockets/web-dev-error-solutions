# 🐞 CSS Challenge:  Animated Circular Progress Bar with Tailwind CSS


This challenge involves creating an animated circular progress bar using Tailwind CSS. The bar will visually represent a percentage value (e.g., representing download progress, task completion, etc.), animating smoothly from 0% to the specified value.  We'll achieve the circular effect using an SVG and CSS animations.

## Styling Description:

The progress bar will be a circle with a thicker ring representing the progress. The ring will fill in clockwise from 0% to the specified percentage value.  We'll use Tailwind CSS classes for styling and layout, keeping the code concise and maintainable.  The animation will be smooth and visually appealing.  The final output should resemble a loading or progress indicator commonly seen in web applications.

## Full Code:

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Circular Progress Bar</title>
<link href="https://cdn.jsdelivr.net/npm/tailwindcss@2.2.19/dist/tailwind.min.css" rel="stylesheet">
<style>
.progress-ring {
  stroke-dasharray: 283; /* Circumference of the circle */
  stroke-dashoffset: 283; /* Initially hides the progress */
  transition: stroke-dashoffset 0.5s ease-in-out; /* Smooth animation */
}
</style>
</head>
<body class="bg-gray-100">
  <div class="flex items-center justify-center h-screen">
    <svg class="w-48 h-48" viewBox="0 0 100 100">
      <circle class="progress-ring text-gray-300" cx="50" cy="50" r="40" fill="transparent" stroke-width="10"/>
      <circle class="progress-ring text-blue-500 fill-current" cx="50" cy="50" r="40" fill="transparent" stroke-width="10" stroke-dasharray="283" stroke-dashoffset="0" style="stroke-dashoffset: 141.5;"></circle>  <!-- Adjust style for initial progress -->
    </svg>
  </div>

  <script>
    const percentage = 50; // Adjust percentage as needed.
    const circle = document.querySelector('.fill-current');
    const offset = 283 - (283 * (percentage / 100));
    circle.style.strokeDashoffset = offset;
  </script>
</body>
</html>
```


## Explanation:

* **HTML Structure:** We use an SVG to create the circular progress bar.  Two circles are used: one for the background track (gray) and one for the filled progress (blue).
* **Tailwind CSS:** Tailwind provides utility classes for easy styling (`w-48`, `h-48`, `text-gray-300`, `text-blue-500`, `bg-gray-100`, etc.).
* **SVG Properties:**
    * `stroke-dasharray`: Sets the total length of the dash (circumference).  We calculate it as 2πr (radius = 40), approximating to 283.
    * `stroke-dashoffset`: Controls the starting point of the dash, effectively creating the animation.  We adjust it based on the percentage.
    * `transition`:  Ensures a smooth animation when the `stroke-dashoffset` changes.
* **JavaScript:** The JavaScript dynamically calculates the `stroke-dashoffset` based on the `percentage` variable and updates the SVG element accordingly.


## Resources to Learn More:

* **Tailwind CSS Documentation:** [https://tailwindcss.com/docs](https://tailwindcss.com/docs)
* **SVG Tutorial:** [https://developer.mozilla.org/en-US/docs/Web/SVG](https://developer.mozilla.org/en-US/docs/Web/SVG)
* **CSS Animations:** [https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations/Using_CSS_animations](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations/Using_CSS_animations)

Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

