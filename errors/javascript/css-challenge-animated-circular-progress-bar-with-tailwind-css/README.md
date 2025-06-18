# 🐞 CSS Challenge:  Animated Circular Progress Bar with Tailwind CSS


This challenge focuses on creating an animated circular progress bar using Tailwind CSS.  The bar will visually represent a percentage value (we'll use 75% for this example), animating from 0% to the target percentage. We'll achieve the animation using CSS only, leveraging Tailwind's utility classes for efficient styling.

**Description of the Styling:**

The progress bar will be a circle composed of two overlapping SVG elements: a background circle and a foreground circle representing the progress.  The foreground circle will be animated to increase its stroke-dasharray value, creating the filling effect. Tailwind will handle the sizing, colors, and positioning.


**Full Code:**

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
    transform: rotate(-90deg); /* Start at the top */
  }

  .progress-ring__circle {
    stroke-width: 10;
    stroke-linecap: round;
    transition: stroke-dashoffset 0.5s ease-in-out; /* Smooth animation */
  }
</style>
</head>
<body class="bg-gray-100 flex justify-center items-center h-screen">

<svg class="progress-ring w-48 h-48" viewBox="0 0 100 100">
  <circle class="progress-ring__circle text-gray-300" cx="50" cy="50" r="40" fill="transparent" stroke-dasharray="251.327" stroke-dashoffset="251.327"></circle>
  <circle class="progress-ring__circle text-blue-500" cx="50" cy="50" r="40" fill="transparent" stroke-dasharray="251.327" stroke-dashoffset="62.83175" style="stroke-dashoffset: calc(251.327 - 251.327 * 0.75);"></circle>
</svg>


</body>
</html>
```

**Explanation:**

* **HTML Structure:**  We use an SVG `<circle>` element for the background and another for the progress.  The `viewBox` attribute defines the SVG's coordinate system.
* **CSS Styling:** Tailwind classes (`w-48`, `h-48`, `text-gray-300`, `text-blue-500`) control the size and colors. The `stroke-dasharray` property sets the total length of the circle's circumference.  `stroke-dashoffset` controls the starting point of the stroke.  The initial `stroke-dashoffset` equals the `stroke-dasharray`, making the circle invisible at the start.  The animation is done by changing this offset.
* **Animation:** The Javascript portion calculates the `stroke-dashoffset` dynamically based on the percentage (75% in this case).   The `transition` property ensures a smooth animation.  Note that the example has the percentage hardcoded, but this can easily be made dynamic with Javascript.
* **Tailwind's Role:** Tailwind simplifies the styling by providing ready-to-use classes for colors, sizes, and spacing.


**Links to Resources to Learn More:**

* **Tailwind CSS Documentation:** [https://tailwindcss.com/docs](https://tailwindcss.com/docs)
* **SVG Tutorial:** [https://developer.mozilla.org/en-US/docs/Web/SVG](https://developer.mozilla.org/en-US/docs/Web/SVG)
* **CSS Animations:** [https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations/Using_CSS_animations](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations/Using_CSS_animations)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

