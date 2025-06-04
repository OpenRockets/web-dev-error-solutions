# 🐞 Creating a CSS-Only Circular Progress Bar


This document details how to create a circular progress bar using only CSS.  No JavaScript is required. This example uses CSS variables for easy customization.

**Description of the Styling:**

This technique leverages CSS's `conic-gradient` function to create the circular progress bar.  The gradient's angle is dynamically controlled by a custom property (`--progress`) representing the percentage of completion.  A background circle provides a clean visual frame.  We use CSS variables to make it easily customizable.

**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>CSS Circular Progress Bar</title>
<style>
  .progress-ring {
    --progress: 75; /* Adjust this value to change the progress */
    --size: 100px; /* Adjust this value to change the size */
    width: var(--size);
    height: var(--size);
    position: relative;
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
      #4CAF50 var(--progress)deg, 
      #ddd 0
    );
    border: 2px solid #ddd;
  }
</style>
</head>
<body>

  <div class="progress-ring"></div>

</body>
</html>
```

**Explanation:**

* **`--progress`:** This CSS variable controls the progress percentage.  It's directly used within the `conic-gradient` function. A value of 75 means the progress bar will fill 75% of the circle.
* **`--size`:** This variable controls the size of the progress bar.  Adjusting this value changes the overall dimensions.
* **`conic-gradient()`:** This CSS function creates a gradient that radiates from the center of the element.  The first color (`#4CAF50` in this case – green) fills the arc defined by `var(--progress)deg`, while the second color (`#ddd`) fills the rest.
* **`border-radius: 50%`:** This creates the circular shape.
* **`translate(-50%, -50%)`:** This centers the inner circle within the outer container.

**Links to Resources to Learn More:**

* **MDN Web Docs on `conic-gradient()`:** [https://developer.mozilla.org/en-US/docs/Web/CSS/conic-gradient](https://developer.mozilla.org/en-US/docs/Web/CSS/conic-gradient)
* **CSS Tricks on Circular Progress Bars (Various Techniques):** Search "CSS Circular Progress Bar" on [https://css-tricks.com/](https://css-tricks.com/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

