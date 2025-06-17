# 🐞 CSS Challenge:  Centered Circular Progress Bar


This challenge involves creating a visually appealing circular progress bar using only CSS. The progress bar will be centered on the page and display a percentage value within the circle.  We'll use CSS variables for easy customization.  This example utilizes standard CSS, but the concepts could easily be adapted to a framework like Tailwind CSS.


## Description of the Styling:

The progress bar consists of a circular track and a circular fill. The fill's size represents the percentage.  We'll use `conic-gradient` for the circular fill, giving a smooth and visually pleasing progress indicator. The percentage is displayed in the center of the circle using a pseudo-element.  The styling aims for a clean, modern look, easily adaptable to different color schemes.

## Full Code:

```html
<!DOCTYPE html>
<html>
<head>
<title>Circular Progress Bar</title>
<style>
  .progress-ring {
    width: 150px;
    height: 150px;
    border-radius: 50%;
    display: flex;
    justify-content: center;
    align-items: center;
    position: relative;
  }

  .progress-ring::before {
    content: '';
    position: absolute;
    width: 100%;
    height: 100%;
    border-radius: 50%;
    border: 5px solid #ddd; /* Track color */
    box-sizing: border-box;
  }

  .progress-ring::after {
    content: attr(data-percentage)'%';
    position: absolute;
    font-size: 1.2em;
    font-weight: bold;
  }

  .progress-ring.filled {
      --progress: 75; /* Adjust this value to change the progress percentage */
      --color: #007bff; /* Progress bar color */
      
      /* The magic - conic gradient creates the filled circle */
      background: conic-gradient(
          var(--color) var(--progress)%,
          #ddd var(--progress)%
      );
  }

</style>
</head>
<body>

<div class="progress-ring filled" data-percentage="75"></div>

</body>
</html>
```


## Explanation:

* **`progress-ring`**: This class sets the dimensions, shape, and centering of the progress bar.  `display: flex` and `justify-content/align-items` are used for easy centering.
* **`::before` pseudo-element**: Creates the circular track.
* **`::after` pseudo-element**: Displays the percentage value.  `attr(data-percentage)` accesses the data attribute from the main element.
* **`filled` class**:  This class holds the magic: the `conic-gradient` function creates the circular fill. `var(--progress)` dynamically adjusts the fill's size based on the CSS variable. `var(--color)` controls the color of the filled section.
* **CSS Variables**: `--progress` and `--color` make it easy to change the percentage and color.


## Links to Resources to Learn More:

* **CSS Gradients:**  [MDN Web Docs - CSS Gradients](https://developer.mozilla.org/en-US/docs/Web/CSS/linear-gradient) (Look at the `conic-gradient` section)
* **CSS Pseudo-elements:** [MDN Web Docs - Pseudo-elements](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements)
* **CSS Variables (Custom Properties):** [MDN Web Docs - CSS Variables](https://developer.mozilla.org/en-US/docs/Web/CSS/Using_CSS_custom_properties)

## Adapting to Tailwind CSS:

To adapt this to Tailwind CSS, you would replace the custom CSS with Tailwind classes. For example, you could use `w-48 h-48` for size, `rounded-full` for border radius, and Tailwind's utility classes for colors and spacing.  The `conic-gradient` would still be needed as a custom CSS declaration within a `style` attribute or a separate CSS file.


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

