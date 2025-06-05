# 🐞 Creating a CSS-Only Circular Progress Bar


This document details how to create a circular progress bar using only CSS.  We'll leverage CSS's `clip-path` property and some clever calculations to achieve this effect without relying on JavaScript.


**Description of the Styling:**

This technique uses a circle as a base, then uses the `clip-path` property to create a "pie slice" representing the progress.  We manipulate the `clip-path` value dynamically with a CSS variable to control the progress percentage.  The styling includes a background circle for the track and a foreground circle for the progress fill.  We use some subtle shadows to add depth and visual appeal.


**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>CSS Circular Progress Bar</title>
<style>
.progress-ring {
  width: 150px;
  height: 150px;
  position: relative;
}

.progress-ring .circle {
  width: 100%;
  height: 100%;
  border-radius: 50%;
  border: 10px solid #e0e0e0; /* Track color */
  position: absolute;
  top: 0;
  left: 0;
}

.progress-ring .circle::before {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  border-radius: 50%;
  clip-path: circle(50% at 50% 50%); /* Base circle */
  background-color: #4CAF50; /* Progress color */
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.2); /* Add shadow for depth */
  transform: rotate(-90deg); /* Start at top */
}

.progress-ring[data-progress="75"] .circle::before {
  clip-path: polygon(50% 0%, 75% 50%, 50% 100%, 25% 50%); /* Example for 75% progress */
}

/* Dynamically change clip-path using CSS variable */
:root {
  --progress: 75; /* You can change this value */
}

.progress-ring .circle::before {
  --progress: var(--progress);
  --rotate: calc(var(--progress) * 3.6deg);
  clip-path: polygon(50% 50%, calc(50% + 50% * cos(var(--rotate))) calc(50% - 50% * sin(var(--rotate))), 50% 50%, calc(50% + 50% * cos(var(--rotate))) calc(50% + 50% * sin(var(--rotate))));
}


</style>
</head>
<body>

<div class="progress-ring" data-progress="75">
  <div class="circle"></div>
</div>

</body>
</html>
```

**Explanation:**

1. **Base Structure:**  We create a container (`progress-ring`) and an inner element (`circle`) for the track.
2. **Pseudo-element:** The `::before` pseudo-element creates the progress fill.  It initially has a full circle `clip-path`.
3. **Dynamic Clip-Path:** The `:root` element defines a CSS variable `--progress`  that determines the percentage. We use a calculation to convert the percentage to degrees for rotation (360 degrees / 100% = 3.6deg).  The `clip-path: polygon()` then dynamically creates the pie slice based on this calculated rotation.
4. **Responsive Design:**  The size of the progress bar can be easily adjusted by changing the `width` and `height` of the `.progress-ring` class.

**Resources to Learn More:**

* **MDN Web Docs on `clip-path`:** [https://developer.mozilla.org/en-US/docs/Web/CSS/clip-path](https://developer.mozilla.org/en-US/docs/Web/CSS/clip-path)
* **Understanding CSS Variables (Custom Properties):** [https://developer.mozilla.org/en-US/docs/Web/CSS/Using_CSS_custom_properties](https://developer.mozilla.org/en-US/docs/Web/CSS/Using_CSS_custom_properties)

Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

