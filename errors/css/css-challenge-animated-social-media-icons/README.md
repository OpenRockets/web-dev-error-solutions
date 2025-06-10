# 🐞 CSS Challenge:  Animated Social Media Icons


This challenge involves creating a set of animated social media icons using CSS.  The icons will be arranged in a row, and upon hovering over each icon, it will smoothly scale up and change color.  We'll use CSS transitions and transforms to achieve the animation effect.


## Description of Styling

The styling will use a simple grid layout to arrange the icons horizontally. Each icon will be a square with a colored background representing the social media platform.  The animation will involve scaling the icon up by 10% and changing its background color to a slightly lighter shade upon hover.  We will use Tailwind CSS for rapid styling and utility classes.


## Full Code (Tailwind CSS)

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Animated Social Media Icons</title>
<link href="https://cdn.jsdelivr.net/npm/tailwindcss@2.2.19/dist/tailwind.min.css" rel="stylesheet">
<style>
  .icon {
    transition: transform 0.3s ease, background-color 0.3s ease; /* Smooth transition for transform and color */
    width: 50px;
    height: 50px;
    margin: 10px;
    border-radius: 50%; /* Makes icons circular */
    display: flex;
    justify-content: center;
    align-items: center;
    cursor: pointer;
  }

  .icon:hover {
    transform: scale(1.1); /* Scales up on hover */
  }
</style>
</head>
<body class="bg-gray-100 flex justify-center items-center h-screen">

<div class="flex">
  <div class="icon bg-blue-500 text-white">
    <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
      <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 10h18M7 15h1m4-4h1m-10 4h1m-6-10v18m-1-0h18"/>
    </svg>
  </div>
  <div class="icon bg-red-500 text-white">
      <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 6.253v13m0-13C10.832 5.477 9.246 5 7.5 5S4.168 5.477 3 6.253v13C4.168 18.477 5.754 19 7.5 19s3.332-0.523 4.5-1.253m-4.5-11.747h9"/>
      </svg>
  </div>
  <div class="icon bg-green-500 text-white">
      <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor" >
        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M16 8v8m-4-5v5m-4 0v5M6 18l12-12"/>
      </svg>
  </div>
</div>

</body>
</html>
```

## Explanation

* **Tailwind CSS:** We utilize Tailwind's utility classes for quick styling (e.g., `bg-blue-500`, `text-white`, `flex`, `justify-center`, etc.).  This significantly reduces the amount of custom CSS needed.
* **CSS Transitions:** The `transition` property smoothly animates the `transform` and `background-color` properties over 0.3 seconds using an ease timing function.
* **CSS Transforms:** The `transform: scale(1.1);` in the hover state scales the icon up by 10%.
* **SVG Icons:**  Simple SVG icons are included for the social media platforms (replace these with your preferred icons).  You can find free SVG icons on websites like [Font Awesome](https://fontawesome.com/) or [The Noun Project](https://thenounproject.com/).
* **Grid Layout:**  The `flex` class arranges the icons in a horizontal row.

## Resources to Learn More

* **Tailwind CSS Documentation:** [https://tailwindcss.com/docs](https://tailwindcss.com/docs)
* **CSS Transitions and Transforms:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transition](https://developer.mozilla.org/en-US/docs/Web/CSS/transition), [https://developer.mozilla.org/en-US/docs/Web/CSS/transform](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
* **SVG Tutorials:** Search for "SVG tutorials" on YouTube or your preferred learning platform.


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

