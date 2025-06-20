# 🐞 CSS Challenge:  Animated Circular Progress Bar


This challenge involves creating an animated circular progress bar using pure CSS. We'll achieve this effect using a combination of `border-radius`, `transform`, `animation`, and some clever pseudo-elements. The final result will be a visually appealing and smoothly animated progress indicator.  This example utilizes plain CSS; however, it could easily be adapted to use a framework like Tailwind CSS for utility class-based styling.

**Description of the Styling:**

The progress bar is built upon a circular base element.  A pseudo-element (`::before`) creates the actual progress indicator, which is a circular segment.  The animation is achieved by manipulating the `stroke-dasharray` and `stroke-dashoffset` properties to control the length of the visible portion of the circle.  We use CSS variables to easily customize the progress bar's color, size, and thickness.

**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>Animated Circular Progress Bar</title>
<style>
  .progress-ring {
    width: 150px;
    height: 150px;
    border-radius: 50%;
    background-color: #f2f2f2; /* Background color */
    position: relative;
    display: flex;
    justify-content: center;
    align-items: center;
  }

  .progress-ring::before {
    content: "";
    position: absolute;
    width: 100%;
    height: 100%;
    border-radius: 50%;
    border: 10px solid transparent; /* Adjust thickness here */
    border-top-color: #007bff; /* Progress bar color */
    animation: progress-bar 2s linear forwards; /* Adjust animation speed */
  }

  @keyframes progress-bar {
    to {
      stroke-dashoffset: 0;
    }
  }
  .progress-ring{
    --progress: 75; /* Adjust the progress percentage here */
  }
  .progress-ring::before {
    stroke-dasharray: calc(2 * 3.14159 * 75); /* Radius * 2 * pi */
    stroke-dashoffset: calc(2 * 3.14159 * 75 * (1 - var(--progress) / 100));
  }

</style>
</head>
<body>

<div class="progress-ring"></div>

</body>
</html>
```


**Explanation:**

* **`stroke-dasharray`**: This property creates dashes in the border.  We calculate its value based on the circumference of the circle (2 * π * radius).
* **`stroke-dashoffset`**: This property controls the starting point of the dashes. We dynamically calculate it to show the correct percentage of progress.  A value of 0 shows the full circle, while a value equal to the circumference hides the entire circle.  The calculation is performed based on `var(--progress)` which allows to easily change the percentage.
* **`animation`**: The `progress-bar` animation smoothly changes the `stroke-dashoffset` to create the animation.
* **CSS Variables:** Using `var(--progress)` allows for easy customization of the progress percentage.

**Resources to Learn More:**

* **MDN Web Docs - CSS Animations:** [https://developer.mozilla.org/en-US/docs/Web/CSS/animation](https://developer.mozilla.org/en-US/docs/Web/CSS/animation)
* **MDN Web Docs - CSS Transforms:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transform](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
* **CSS-Tricks - SVG Progress Rings:** (Search for relevant tutorials on CSS-Tricks, as their articles frequently cover this topic)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

