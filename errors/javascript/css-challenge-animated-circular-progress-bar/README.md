# 🐞 CSS Challenge:  Animated Circular Progress Bar


This challenge involves creating an animated circular progress bar using only CSS.  We'll target a specific percentage (let's say 75%) and animate the filling of the circle. This example uses only CSS, no Javascript required.  We'll leverage CSS animations and transforms to achieve the effect.


**Description of the Styling:**

The progress bar consists of a circle track and a circle fill. The track is a simple circle with a border.  The fill is another circle overlaid on top, rotated to represent the progress percentage.  The animation smoothly rotates the fill circle to show the progress.  We use CSS variables (custom properties) for easy customization of colors and size.


**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>Circular Progress Bar</title>
<style>
:root {
  --progress-size: 200px;
  --progress-track-color: #e0e0e0;
  --progress-fill-color: #4CAF50;
}

.progress-ring {
  width: var(--progress-size);
  height: var(--progress-size);
  position: relative;
  border-radius: 50%;
}

.progress-ring::before {
  content: "";
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: var(--progress-size);
  height: var(--progress-size);
  border-radius: 50%;
  border: 10px solid var(--progress-track-color);
  border-right-color: transparent; /*This creates the circular look*/
}

.progress-ring::after {
  content: "";
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%) rotate(270deg); /*Start at the top*/
  width: var(--progress-size);
  height: var(--progress-size);
  border-radius: 50%;
  border: 10px solid var(--progress-fill-color);
  border-right-color: transparent;
  animation: progress 2s linear forwards;
}


@keyframes progress {
  to {
    transform: translate(-50%, -50%) rotate(calc(360deg * 75% - 90deg)); /*Calculate rotation based on percentage*/
  }
}
</style>
</head>
<body>

<div class="progress-ring"></div>

</body>
</html>
```

**Explanation:**

* **`--progress-size`, `--progress-track-color`, `--progress-fill-color`:** CSS variables for easy customization.
* **`.progress-ring::before`:** Creates the track circle using a `::before` pseudo-element.  `border-right-color: transparent;` is key to making it a circular track.
* **`.progress-ring::after`:** Creates the fill circle using a `::after` pseudo-element.  The initial `rotate(270deg)` starts the fill at the top.
* **`@keyframes progress`:** Defines the animation. The `calc(360deg * 75% - 90deg)` calculates the rotation needed for 75% progress. The `-90deg` offset adjusts for the starting position.  Change `75%` to modify the progress percentage.


**Links to Resources to Learn More:**

* **CSS Animations:** [MDN Web Docs - CSS Animations](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations/Using_CSS_animations)
* **CSS Transforms:** [MDN Web Docs - CSS Transforms](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
* **CSS Variables:** [MDN Web Docs - CSS Custom Properties](https://developer.mozilla.org/en-US/docs/Web/CSS/--*)
* **Pseudo-elements:** [MDN Web Docs - Pseudo-elements](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

