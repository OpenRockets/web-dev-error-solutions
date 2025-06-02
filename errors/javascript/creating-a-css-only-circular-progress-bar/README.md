# 🐞 Creating a CSS-only Circular Progress Bar


This document details how to create a circular progress bar using only CSS.  This avoids the need for JavaScript, making it lightweight and efficient. We'll leverage CSS's `conic-gradient` function for a clean and modern look.


**Description of the Styling:**

This styling creates a circular progress bar using a `conic-gradient`. The gradient starts at the top and sweeps clockwise. The percentage of the circle filled is controlled by the `--progress` custom property.  We use a combination of pseudo-elements (`::before` and `::after`) to create the background circle and the progress indicator. The visual effect is enhanced using shadows to give it a three-dimensional appearance.

**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>CSS Circular Progress Bar</title>
<style>
.progress-ring {
  --progress: 75; /* Adjust this value to change the progress */
  width: 150px;
  height: 150px;
  border-radius: 50%;
  background-color: #f0f0f0; /* Light gray background */
  position: relative;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.2); /* Add a subtle shadow */
}

.progress-ring::before {
  content: "";
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 100%;
  height: 100%;
  border-radius: 50%;
  background: conic-gradient(
    #4CAF50 var(--progress)%,
    #f0f0f0 var(--progress)%
  );
  /*#4CAF50 is the progress color. Change as needed*/
}

.progress-ring::after {
    content: attr(data-progress) '%';
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    font-size: 1.2rem;
    font-weight: bold;
    color: #333;
}

</style>
</head>
<body>

<div class="progress-ring" data-progress="75"></div>

</body>
</html>
```

**Explanation:**

* **`--progress`:**  This custom property dynamically controls the progress percentage. Change its value (between 0 and 100) to adjust the filled portion of the circle.
* **`conic-gradient`:** This function creates a circular gradient.  The first color (#4CAF50 in this case, a green) fills the percentage defined by `var(--progress)`. The rest is filled with the second color (#f0f0f0, light gray).
* **Pseudo-elements:** `::before` creates the circular progress indicator using the gradient. `::after` displays the progress percentage in the center.
* **Positioning and Transformations:** `position: absolute`, `top: 50%`, `left: 50%`, and `transform: translate(-50%, -50%)` are used to center the pseudo-elements within the parent container.


**Links to Resources to Learn More:**

* **MDN Web Docs - conic-gradient():** [https://developer.mozilla.org/en-US/docs/Web/CSS/conic-gradient](https://developer.mozilla.org/en-US/docs/Web/CSS/conic-gradient)
* **CSS Tricks - conic-gradient():** (Search for "conic-gradient" on the CSS Tricks website)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

