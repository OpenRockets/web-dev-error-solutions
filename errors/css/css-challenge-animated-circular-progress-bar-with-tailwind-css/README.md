# 🐞 CSS Challenge:  Animated Circular Progress Bar with Tailwind CSS


This challenge involves creating an animated circular progress bar using Tailwind CSS. The progress bar will be a circle that fills up gradually, representing a percentage value.  We'll leverage CSS custom properties (variables) and animations for a smooth and customizable effect.


## Description of the Styling

The progress bar will be a circle with a customizable percentage fill.  The filled portion will be a different color than the background.  An animation will smoothly fill the circle from 0% to the specified percentage. The design will utilize Tailwind CSS classes for rapid styling and responsiveness.  We'll aim for a clean, modern aesthetic.


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
  .circular-progress {
    width: 150px;
    height: 150px;
    border-radius: 50%;
    background-color: #f0f0f0; /* Light gray background */
    position: relative;
  }

  .circular-progress::before {
    content: "";
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    width: 100%;
    height: 100%;
    border-radius: 50%;
    background-color: var(--progress-color); /* Use CSS variable for color */
    clip-path: polygon(50% 0%, 100% 50%, 50% 100%, 0% 50%); /* Start at right */
    animation: fill 2s linear forwards; /* Animate the fill */
  }

  @keyframes fill {
    to {
      clip-path: polygon(50% 0%, 100% 50%, 50% 100%, 0% 50%, 0% 0%, 0% 0%); /* Full circle */
    }
  }
</style>
</head>
<body class="bg-gray-100 flex items-center justify-center h-screen">
  <div class="circular-progress" style="--progress-color: #22c55e; --progress-percentage: 75%;"> </div>
  <div class="mt-4 text-center">
        <p>Progress: <span class="text-xl font-bold">75%</span></p>
    </div>


</body>
</html>
```

## Explanation

1. **HTML Structure:** A simple `div` with the class `circular-progress` acts as the container for the progress bar. We are also including a span to display the percentage for better user experience.

2. **CSS Styling:**
    * `circular-progress`: Sets the basic dimensions, border-radius, and background color of the circle.
    * `circular-progress::before`: Creates a pseudo-element that will be the filled portion of the circle.  `clip-path` is used to initially create a half-circle that we animate.
    * `--progress-color`: A CSS custom property (variable) allows easy customization of the fill color.
    * `--progress-percentage`: A CSS custom property to control the final percentage.  This is not used directly in the animation, but could be used to adjust the animation duration for a more complex, percentage-based animation.
    * `@keyframes fill`: Defines the animation that gradually changes the `clip-path` from a half circle to a full circle to simulate filling the progress bar.


3. **Tailwind CSS:** The example uses Tailwind's classes for basic layout (`bg-gray-100`, `flex`, `items-center`, `justify-center`, `h-screen`) and text styling (`mt-4`, `text-center`, `text-xl`, `font-bold`). You can customize these to match your design preferences.


## Links to Resources to Learn More

* **Tailwind CSS Documentation:** [https://tailwindcss.com/docs](https://tailwindcss.com/docs)
* **CSS Animations:** [https://developer.mozilla.org/en-US/docs/Web/CSS/animation](https://developer.mozilla.org/en-US/docs/Web/CSS/animation)
* **CSS Custom Properties (Variables):** [https://developer.mozilla.org/en-US/docs/Web/CSS/Using_CSS_custom_properties](https://developer.mozilla.org/en-US/docs/Web/CSS/Using_CSS_custom_properties)
* **Clip-path:** [https://developer.mozilla.org/en-US/docs/Web/CSS/clip-path](https://developer.mozilla.org/en-US/docs/Web/CSS/clip-path)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

