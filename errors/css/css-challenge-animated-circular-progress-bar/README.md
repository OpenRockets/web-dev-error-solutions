# 🐞 CSS Challenge:  Animated Circular Progress Bar


This challenge involves creating an animated circular progress bar using pure CSS.  The bar will visually represent a percentage, updating smoothly from 0% to a specified value. We'll use CSS variables and animations for a clean and efficient solution.


## Description of the Styling

The progress bar will be a circle with a background color.  A semi-circle overlay will represent the progress percentage, dynamically changing its size based on the specified value.  The percentage will be displayed as text within the circle.  A smooth animation will accompany the filling of the semi-circle.


## Full Code

```html
<!DOCTYPE html>
<html>
<head>
<title>Circular Progress Bar</title>
<style>
.container {
  width: 200px;
  height: 200px;
  position: relative;
}

.circle {
  width: 100%;
  height: 100%;
  border-radius: 50%;
  background-color: #f0f0f0; /* Background color of the circle */
  position: relative;
}

.progress {
  width: 100%;
  height: 100%;
  border-radius: 50%;
  position: absolute;
  top: 0;
  left: 0;
  clip: rect(0, 100px, 200px, 0); /* Initially, only half is visible */
  background-color: #4CAF50; /* Progress bar color */
  transform-origin: 50% 100%; /* Adjust animation origin */
  animation: progress-animation 1s linear forwards; /* Animate the progress */
}

@keyframes progress-animation {
  to {
    transform: rotate(180deg); /* Rotate by 180 deg to fill the semi-circle */
    clip: rect(0, 200px, 200px, 0); /* show the complete circle after animation complete*/
  }
}

.percentage {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  font-size: 1.2em;
  color: white;
}

/* Using CSS variables to make it dynamic */
.container {
    --progress: 75; /*Change this value to change the progress percentage*/
}

.progress {
  transform: rotate(calc(var(--progress) * 1.8deg)); /* Calculate rotation based on percentage */
}

.percentage {
  content: var(--progress) "%";
}

</style>
</head>
<body>

<div class="container">
  <div class="circle">
    <div class="progress"></div>
    <div class="percentage"></div>
  </div>
</div>

</body>
</html>
```


## Explanation

1. **Structure:**  We use nested divs to create the circular structure. The outer `container` sets dimensions. The `circle` acts as the background, and the `progress` div forms the semi-circular progress bar. The `percentage` div displays the progress value.

2. **CSS Variables:** The `--progress` variable is used to dynamically control the percentage displayed and the progress bar's rotation. Changing this variable will update the entire progress bar.

3. **`clip` Property:** The `clip` property initially hides half of the `progress` div, creating the semi-circle effect.

4. **`transform: rotate()`:** This CSS property rotates the `progress` div, effectively filling the semi-circle based on the percentage.  The calculation `calc(var(--progress) * 1.8deg)` converts the percentage into the corresponding angle of rotation (360 degrees / 100% = 3.6deg per percent; half circle = 180 degrees, hence 1.8deg).

5. **`animation`:** The `progress-animation` keyframes smoothly rotate the `progress` div to fill the circle over the duration of the animation.

6. **Responsiveness:** This code provides a basic structure; for better responsiveness, media queries would be added to adjust sizes based on the screen width.


## Links to Resources to Learn More

* **MDN Web Docs on CSS Animations:** [https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations/Using_CSS_animations](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations/Using_CSS_animations)
* **MDN Web Docs on CSS Variables:** [https://developer.mozilla.org/en-US/docs/Web/CSS/Using_CSS_variables](https://developer.mozilla.org/en-US/docs/Web/CSS/Using_CSS_variables)
* **CSS-Tricks on Animations:** [https://css-tricks.com/snippets/css/keyframe-animation-syntax/](https://css-tricks.com/snippets/css/keyframe-animation-syntax/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

