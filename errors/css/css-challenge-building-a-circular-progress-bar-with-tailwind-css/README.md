# 🐞 CSS Challenge:  Building a Circular Progress Bar with Tailwind CSS


This challenge focuses on creating a visually appealing circular progress bar using Tailwind CSS.  We'll leverage Tailwind's utility classes to simplify the styling process and achieve a clean, modern look.  The progress bar will be dynamic, allowing you to easily adjust the percentage displayed.

**Description of the Styling:**

The progress bar consists of a circular base and a filled arc representing the progress percentage.  We'll use Tailwind's `relative`, `bg-gray-300`, `rounded-full`, and other utility classes to style the base circle.  The filled arc will be created using an absolutely positioned pseudo-element (`::before`) with a background color, rotated using `transform: rotate()`, and styled to be a semi-circle using `clip-path`.  The percentage will be displayed in the center of the circle.

**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Circular Progress Bar</title>
  <script src="https://cdn.tailwindcss.com"></script>
</head>
<body class="bg-gray-100">

<div class="flex justify-center items-center h-screen">
  <div class="relative w-48 h-48">
    <div class="absolute w-full h-full rounded-full bg-gray-300"></div>
    <div class="absolute w-full h-full rounded-full bg-blue-500" 
         style="clip-path: circle(50% at 50% 100%); transform: rotate(225deg);">
    </div>
    <div class="absolute text-center w-full text-white">
      <span class="text-2xl font-bold">75%</span>
    </div>
  </div>
</div>

</body>
</html>
```

**Explanation:**

* **Outer `div`:** Sets up the container for the progress bar, centering it on the page using Tailwind's flexbox utilities.
* **Inner `divs`:**
    * The first inner `div` creates the base circle using `rounded-full` and a gray background.
    * The second inner `div` (pseudo-element) creates the filled arc.  `clip-path: circle(50% at 50% 100%);` cuts the circle in half, creating a semi-circle.  `transform: rotate(225deg);` rotates this semi-circle to represent the progress (75% in this case, which is 270 degrees * 75/100 = 202.5 degrees.  We use 225 to adjust for starting position).   Adjust the `rotate` value to change the percentage.
    * The third `div` displays the percentage value in the center.


**Links to Resources to Learn More:**

* **Tailwind CSS Documentation:** [https://tailwindcss.com/docs](https://tailwindcss.com/docs) -  Comprehensive documentation on Tailwind CSS.
* **CSS `clip-path` Property:** [https://developer.mozilla.org/en-US/docs/Web/CSS/clip-path](https://developer.mozilla.org/en-US/docs/Web/CSS/clip-path) - Learn more about the `clip-path` property for creating custom shapes.
* **Flexbox in CSS:** [https://css-tricks.com/snippets/css/a-guide-to-flexbox/](https://css-tricks.com/snippets/css/a-guide-to-flexbox/) -  Understanding flexbox for layout.


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

