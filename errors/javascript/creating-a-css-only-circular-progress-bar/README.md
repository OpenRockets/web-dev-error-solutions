# 🐞 Creating a CSS-Only Circular Progress Bar


This document details how to create a circular progress bar using only CSS.  We'll leverage CSS's `clip-path` property and some clever calculations to achieve this without any JavaScript.


## Description of the Styling

This circular progress bar uses a combination of pseudo-elements (`::before` and `::after`) and the `clip-path` property to create the circular effect. The `::before` element creates the background circle, while the `::after` element creates the progress bar itself.  We'll use variables for easy customization of the color and percentage.

## Full Code

```html
<div class="progress-bar" data-progress="75">
  <span>75%</span>
</div>

```

```css
.progress-bar {
  width: 150px;
  height: 150px;
  position: relative;
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: #e0e0e0; /* Background Color */
  border-radius: 50%;
}

.progress-bar::before {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  border-radius: 50%;
  background-color: #fff; /* Circle Background Color */
  z-index: -1; /*Ensures it sits behind the progress*/
}

.progress-bar::after {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  border-radius: 50%;
  background-color: #007bff; /* Progress Bar Color */
  clip-path: circle(50% at 50% 50%); /* Initial clip path */
  transform: rotate(-90deg); /* Start at the top */
  z-index:1;

}

.progress-bar[data-progress]::after {
  --progress: attr(data-progress);
  --rotate: calc(var(--progress) * 3.6deg); /* Calculate rotation based on percentage */
  clip-path: polygon(
    50% 50%,
    calc(50% + 50% * cos(var(--rotate))) calc(50% - 50% * sin(var(--rotate))),
    50% 50%
  );
  transition: clip-path 0.5s ease;  /* Add smooth animation*/
  transform: rotate(calc(var(--rotate) - 90deg));
}


.progress-bar span{
  position: relative;
  z-index: 2;
  font-size: 1.2em;
  font-weight: bold;
  color: #333;
}

```

## Explanation

1. **HTML Structure:** A simple `div` with a `data-progress` attribute to hold the percentage is used.

2. **CSS Variables:**  CSS custom properties (`--progress` and `--rotate`) allow dynamic calculation of the rotation angle based on the `data-progress` attribute.

3. **`clip-path`:** The `clip-path` property is used to create the circular progress effect.  Initially, it's a full circle. We then dynamically modify the `clip-path` to a polygon that forms a partial circle based on the progress percentage.

4. **Calculation:** `calc(var(--progress) * 3.6deg)` converts the percentage to degrees (360 degrees in a full circle).

5. **`transform: rotate()`:**  Rotates the progress bar element to start at the top and then rotates further based on the progress.


## Links to Resources to Learn More

* **MDN Web Docs on `clip-path`:** [https://developer.mozilla.org/en-US/docs/Web/CSS/clip-path](https://developer.mozilla.org/en-US/docs/Web/CSS/clip-path)
* **CSS Tricks:** Search for "CSS progress bar" on [https://css-tricks.com/](https://css-tricks.com/) for various examples and techniques.


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

