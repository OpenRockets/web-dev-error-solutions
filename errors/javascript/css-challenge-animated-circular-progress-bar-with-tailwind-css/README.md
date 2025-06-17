# 🐞 CSS Challenge:  Animated Circular Progress Bar with Tailwind CSS


This challenge involves creating an animated circular progress bar using Tailwind CSS.  The bar will visually represent a percentage, smoothly filling the circle as the percentage increases.  We'll leverage Tailwind's utility classes for quick styling and CSS animations for the dynamic effect.


## Description of the Styling

The progress bar will be a circle with a background color and a colored arc that represents the progress. The arc will animate, growing from 0% to the specified percentage.  We'll use Tailwind's `relative`, `overflow-hidden`, and `rounded-full` classes to create the circular shape and manage the animation's visibility. The animation itself will be a CSS keyframes animation controlling the stroke-dasharray and stroke-dashoffset properties of an SVG circle.

## Full Code

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Circular Progress Bar</title>
<script src="https://cdn.tailwindcss.com"></script>
<style>
  .progress-ring {
    transform: rotate(-90deg); /* Start the animation from the top */
  }
  .progress-ring circle {
    transition: stroke-dashoffset 0.5s linear; /* Smooth animation */
  }
  .progress-ring.animate {
    animation: progress 0.5s linear forwards; /* Trigger the animation */
  }
  @keyframes progress {
    to {
      stroke-dashoffset: 0; /* Complete circle at the end */
    }
  }
</style>
</head>
<body class="bg-gray-100">

<div class="container mx-auto p-8">
  <div class="flex justify-center items-center">
    <div class="w-48 h-48 relative">
      <svg class="progress-ring animate" width="100%" height="100%" viewBox="0 0 100 100">
        <circle class="stroke-gray-300 stroke-2" cx="50" cy="50" r="40" fill="none" />
        <circle class="stroke-blue-500 stroke-2" cx="50" cy="50" r="40" fill="none"
                stroke-dasharray="251.327" stroke-dashoffset="251.327" stroke-linecap="round"/>
      </svg>
      <div class="absolute inset-0 flex justify-center items-center text-lg font-medium">
        <span id="percentage">75%</span>
      </div>
    </div>
  </div>
</div>
<script>
  const percentage = 75; // Change this value to adjust the progress
  const circumference = 2 * Math.PI * 40;
  const offset = circumference - (percentage/100) * circumference;
  const circle = document.querySelector('.progress-ring circle:nth-child(2)');
  circle.style.strokeDashoffset = offset;
  document.getElementById('percentage').innerText = percentage + '%';


</script>


</body>
</html>
```

## Explanation

1. **HTML Structure:** We create a simple HTML structure using a `<div>` to center the progress bar.  An SVG `<circle>` element represents the progress bar itself, with two circles – one for the background and one for the animated progress arc.  A `<span>` displays the percentage.


2. **Tailwind CSS:** We use Tailwind classes for styling, like `bg-gray-100` (background color), `w-48 h-48` (size), and `rounded-full` (shape).


3. **CSS Animation:**  The `progress` keyframes animation smoothly decreases `stroke-dashoffset` from the initial value (full circle) to 0, creating the filling animation.  `stroke-dasharray` is set to the circumference of the circle, allowing us to control the visible portion of the arc. `stroke-linecap="round"` makes the ends of the arc rounded.


4. **JavaScript (Optional):** The JavaScript part calculates the `stroke-dashoffset` based on the desired percentage and updates the percentage display.  You can easily modify the `percentage` variable to change the progress level.


## Links to Resources to Learn More

* **Tailwind CSS Documentation:** [https://tailwindcss.com/docs/](https://tailwindcss.com/docs/)
* **SVG Tutorial:** [https://developer.mozilla.org/en-US/docs/Web/SVG](https://developer.mozilla.org/en-US/docs/Web/SVG)
* **CSS Animations:** [https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations/Using_CSS_animations](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations/Using_CSS_animations)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

