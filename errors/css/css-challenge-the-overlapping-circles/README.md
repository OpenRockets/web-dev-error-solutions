# 🐞 CSS Challenge:  The Overlapping Circles


This challenge involves creating a visually appealing design using overlapping circles of varying sizes and colors. We'll leverage CSS's `position` property, `border-radius`, and `box-shadow` to achieve a modern and stylish look.  This example uses plain CSS3; adapting it to Tailwind would involve replacing the inline styles with Tailwind classes.

## Description of the Styling

The design consists of three circles of different sizes. The largest circle is in the background, followed by a medium-sized circle partially overlapping it, and finally a smaller circle overlapping both.  Each circle has a unique color and a subtle box shadow to give it depth.  The overall effect is a visually engaging composition.

## Full Code (CSS3)

```css
body {
  background-color: #f0f0f0; /* Light gray background */
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 100vh;
}

.circle-container {
  position: relative;
  width: 200px;
  height: 200px;
}

.circle {
  position: absolute;
  border-radius: 50%;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.2); /* Subtle shadow */
}

.circle-large {
  width: 200px;
  height: 200px;
  background-color: #673AB7; /* Purple */
  left: 0;
  top: 0;
}

.circle-medium {
  width: 150px;
  height: 150px;
  background-color: #FF9800; /* Orange */
  left: 25px;
  top: 25px;
}

.circle-small {
  width: 100px;
  height: 100px;
  background-color: #03A9F4; /* Blue */
  left: 50px;
  top: 50px;
}
```

To see this in action, you'll need to include this CSS in a `<style>` tag within your HTML file, or in a separate `.css` file linked to your HTML.  Wrap the circles in a container div with the class `circle-container`.


```html
<!DOCTYPE html>
<html>
<head>
<title>Overlapping Circles</title>
<style>
/* Paste the CSS code here */
</style>
</head>
<body>
  <div class="circle-container">
    <div class="circle circle-large"></div>
    <div class="circle circle-medium"></div>
    <div class="circle circle-small"></div>
  </div>
</body>
</html>

```


## Explanation

* **`position: relative` on the container:** This allows us to absolutely position the circles within the container.
* **`position: absolute` on circles:** This makes the circles positioned relative to their parent container (`circle-container`).
* **`border-radius: 50%`:** Creates the perfect circle shape.
* **`box-shadow`:** Adds a subtle shadow for a 3D effect.
* **`left` and `top` properties:** Control the position of each circle to create the overlap.

## Resources to Learn More

* **MDN Web Docs - CSS Positioning:** [https://developer.mozilla.org/en-US/docs/Web/CSS/position](https://developer.mozilla.org/en-US/docs/Web/CSS/position)
* **MDN Web Docs - `border-radius`:** [https://developer.mozilla.org/en-US/docs/Web/CSS/border-radius](https://developer.mozilla.org/en-US/docs/Web/CSS/border-radius)
* **MDN Web Docs - `box-shadow`:** [https://developer.mozilla.org/en-US/docs/Web/CSS/box-shadow](https://developer.mozilla.org/en-US/docs/Web/CSS/box-shadow)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

