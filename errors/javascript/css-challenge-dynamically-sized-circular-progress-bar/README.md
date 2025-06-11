# 🐞 CSS Challenge:  Dynamically Sized Circular Progress Bar


This challenge involves creating a circular progress bar using only CSS. The bar should dynamically adjust its size based on a percentage value, providing a visually appealing and responsive progress indicator.  We'll use only CSS, leveraging techniques like `clip-path` and `transform` for the animation.  No JavaScript is required!

**Description of the Styling:**

The progress bar will be a circle divided into two parts: a filled segment representing the progress and an unfilled segment.  The filled segment's arc length will be proportional to the percentage value.  The styling will aim for a clean, modern look, easily customizable through CSS variables.


**Full Code (CSS only):**

```css
:root {
  --progress: 75; /* Customizable progress percentage (0-100) */
  --size: 100px; /* Customizable size of the circle */
  --stroke-width: 10px; /* Customizable width of the progress bar */
  --primary-color: #007bff; /* Customizable primary color */
  --secondary-color: #e9ecef; /* Customizable secondary color */
}

.progress-ring {
  width: var(--size);
  height: var(--size);
  position: relative;
}

.progress-ring__circle {
  width: 100%;
  height: 100%;
  border-radius: 50%;
  border: var(--stroke-width) solid var(--secondary-color);
  position: relative;
  display: flex;
  justify-content: center;
  align-items: center;
}

.progress-ring__circle::before {
  content: "";
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 100%;
  height: 100%;
  border-radius: 50%;
  clip-path: polygon(50% 50%, 100% 50%, 100% calc(50% - var(--stroke-width)), 50% calc(50% - var(--stroke-width)));
  background-color: var(--primary-color);
  transform: rotate(calc(var(--progress) * 3.6deg)); /* 360deg / 100 */
}

.progress-ring__percentage {
  position: absolute;
  font-size: 0.7em;
  color: var(--primary-color);
}
```

**HTML (Example):**

To use this CSS, you'll need a simple HTML structure like this:

```html
<div class="progress-ring">
  <div class="progress-ring__circle">
    <div class="progress-ring__percentage">
      <span>75%</span>
    </div>
  </div>
</div>
```


**Explanation:**

* **CSS Variables:**  Using `:root` allows for easy customization of colors, size, and stroke width.
* **`clip-path`:** This property creates the circular segment. The polygon shape is dynamically calculated to form an arc.
* **`transform: rotate()`:** This rotates the filled segment based on the `--progress` variable, creating the progress effect.  The calculation `calc(var(--progress) * 3.6deg)` converts the percentage to degrees (360 degrees in a full circle).
* **HTML Structure:** The nested divs provide a clear structure for the progress ring, circle, and percentage display.


**Links to Resources to Learn More:**

* **MDN Web Docs - `clip-path`:** [https://developer.mozilla.org/en-US/docs/Web/CSS/clip-path](https://developer.mozilla.org/en-US/docs/Web/CSS/clip-path)
* **MDN Web Docs - `transform`:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transform](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
* **CSS Tricks - Working with `clip-path`:** [Search for "CSS Tricks clip-path" on Google; many helpful tutorials are available]


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

