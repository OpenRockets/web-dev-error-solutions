# 🐞 Creating a Pure CSS Triangle


This document details how to create a triangle using only CSS.  This is a classic CSS trick that demonstrates the power of CSS borders to create shapes beyond simple rectangles and squares. We will achieve this using a single HTML element and some clever CSS styling.

**Description of the Styling:**

We'll leverage the `border` property of CSS. By setting different border widths and colors, and cleverly using transparency (`transparent`), we can create the illusion of a triangle.  One border will form the triangle's hypotenuse, while the other two will be invisible.


**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<title>CSS Triangle</title>
<style>
.triangle {
  width: 0;
  height: 0;
  border-left: 50px solid transparent; /* Left border, invisible */
  border-right: 50px solid transparent; /* Right border, invisible */
  border-bottom: 100px solid blue; /* Bottom border, forms the base */
}
</style>
</head>
<body>

<div class="triangle"></div>

</body>
</html>
```

**Explanation:**

* **`width: 0; height: 0;`**:  This sets the initial dimensions of the div to zero. This is crucial; otherwise, the borders wouldn't form a triangle.
* **`border-left: 50px solid transparent;`**: This creates a transparent left border of 50 pixels.  It's invisible but contributes to the shape.
* **`border-right: 50px solid transparent;`**: This creates a transparent right border of 50 pixels, also invisible but forming part of the triangle's shape.
* **`border-bottom: 100px solid blue;`**: This creates a blue solid border of 100 pixels at the bottom. This acts as the base of our triangle.

The combination of these transparent and colored borders creates the visual effect of a triangle.  You can adjust the border widths and colors to change the size and appearance of the triangle. For example, changing `50px` and `100px` will change the proportions, and changing `blue` will change the fill color.



**Resources to Learn More:**

* **MDN Web Docs on CSS Borders:** [https://developer.mozilla.org/en-US/docs/Web/CSS/border](https://developer.mozilla.org/en-US/docs/Web/CSS/border)  This provides a comprehensive reference for the `border` property.
* **CSS-Tricks:** Search for "CSS triangles" on [https://css-tricks.com/](https://css-tricks.com/)  CSS-Tricks often features articles on creative CSS techniques.


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

