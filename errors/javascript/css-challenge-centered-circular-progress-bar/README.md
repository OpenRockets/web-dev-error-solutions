# 🐞 CSS Challenge:  Centered Circular Progress Bar


This challenge involves creating a circular progress bar using only CSS. The progress bar should be centered on the page and visually represent a percentage value (we'll use 75% for this example).  We'll use CSS3 techniques to achieve this, avoiding JavaScript for a purely CSS solution.

**Description of the Styling:**

The progress bar will consist of two concentric circles. The outer circle represents the full 100% and will be a light grey.  The inner circle, a semi-circle, represents the progress (75% in this example) and will be a vibrant blue. We'll use the `clip-path` property to create the semi-circular shape.  The percentage value will be displayed in the center.


**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>Circular Progress Bar</title>
<style>
.container {
  width: 150px;
  height: 150px;
  position: relative;
  margin: 50px auto; /* Center the container */
}

.circle {
  width: 100%;
  height: 100%;
  border-radius: 50%;
  border: 5px solid lightgrey; /* Outer circle */
  position: absolute;
}

.progress {
  width: 100%;
  height: 100%;
  border-radius: 50%;
  position: absolute;
  clip-path: polygon(50% 0%, 100% 50%, 50% 100%, 0% 50%); /* Semi-circle clip-path */
  background-color: blue; /* Progress color */
  transform: rotate(270deg); /* Start at the bottom */
  transform-origin: 50% 50%; /* Rotation origin */
}

.percentage {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  font-size: 20px;
  font-weight: bold;
  color: white;
}

/* Adjust for 75% progress */
.progress-75 {
    clip-path: polygon(50% 0%, 100% 50%, 50% 100%, 0% 50%);
    transform: rotate(270deg) scaleY(-1) rotate(270deg);
    /* calculate rotation based on percentage */
    --rotation: calc(270deg + 75% * 360deg);
    transform: rotate(var(--rotation));
}
</style>
</head>
<body>

<div class="container">
  <div class="circle">
    <div class="progress progress-75"></div>
    <div class="percentage">75%</div>
  </div>
</div>

</body>
</html>
```

**Explanation:**

1. **Container:**  Sets up a relative positioned container for centering.
2. **Circle:** Creates the outer circle using `border-radius`.
3. **Progress:** Creates the inner semi-circle using `clip-path`.  The `transform: rotate` property rotates it to start from the bottom and we use `scaleY(-1)` along with `rotate(270deg)` to ensure the fill starts from 0 degrees.  The `--rotation` custom property calculates the rotation based on the percentage.
4. **Percentage:** Positions the percentage text in the center.
5. **progress-75:** The specific styling for the 75% progress, adjusting the `--rotation` variable.  To change the percentage, simply adjust the `75%` values within `var(--rotation)` and the `percentage` div.

**Links to Resources to Learn More:**

* **CSS `clip-path`:** [MDN Web Docs - clip-path](https://developer.mozilla.org/en-US/docs/Web/CSS/clip-path)
* **CSS Transforms:** [MDN Web Docs - CSS Transforms](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
* **CSS Variables (Custom Properties):** [MDN Web Docs - CSS Variables](https://developer.mozilla.org/en-US/docs/Web/CSS/--* )


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

