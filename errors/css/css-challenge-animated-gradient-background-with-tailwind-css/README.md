# 🐞 CSS Challenge:  Animated Gradient Background with Tailwind CSS


This challenge involves creating a dynamically animated background using CSS gradients and Tailwind CSS for efficient styling.  The animation will smoothly transition between two predefined gradient colors, creating a visually appealing effect. We'll leverage Tailwind's utility classes to streamline the process and improve code readability.

**Description of the Styling:**

The background will be a full-screen, horizontally oriented gradient. The gradient will smoothly transition between a teal (#00ADB5) and a light purple (#C177E3) color over a period of 10 seconds. The animation will loop continuously.  We'll use Tailwind's `bg-gradient-to-r` class to specify the direction, and its responsive design capabilities to ensure the background covers the entire viewport regardless of screen size.

**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Animated Gradient Background</title>
  <script src="https://cdn.tailwindcss.com"></script>
</head>
<body class="h-screen w-screen bg-gradient-to-r from-[#00ADB5] to-[#C177E3] animate-gradient">
  <!-- Your content here -->
</body>
</html>
```

```css
/* Add this to your stylesheet or within a <style> tag if not using CDN */
@keyframes gradient {
  0% {
    background-position: 0% 50%;
  }
  50% {
    background-position: 100% 50%;
  }
  100% {
    background-position: 0% 50%;
  }
}

.animate-gradient {
  animation: gradient 10s ease infinite;
}
```

**Explanation:**

* **`h-screen w-screen`:**  These Tailwind classes make the body element take up the full height and width of the viewport.
* **`bg-gradient-to-r`:** This Tailwind utility creates a gradient that transitions from left to right.
* **`from-[#00ADB5]` and `to-[#C177E3]`:** These specify the starting and ending colors of the gradient using hexadecimal color codes.  The square brackets allow for custom colors in Tailwind.
* **`animate-gradient`:** This custom CSS class applies the `gradient` animation.
* **`@keyframes gradient`:** This CSS rule defines the animation, smoothly shifting the background position to create the animated effect.  `ease` provides a smooth transition, and `infinite` ensures continuous looping.


**Links to Resources to Learn More:**

* **Tailwind CSS Documentation:** [https://tailwindcss.com/docs](https://tailwindcss.com/docs)  (Essential for understanding Tailwind utility classes)
* **CSS Gradients:** [https://developer.mozilla.org/en-US/docs/Web/CSS/linear-gradient](https://developer.mozilla.org/en-US/docs/Web/CSS/linear-gradient) (Learn more about creating and manipulating CSS gradients)
* **CSS Animations:** [https://developer.mozilla.org/en-US/docs/Web/CSS/animation](https://developer.mozilla.org/en-US/docs/Web/CSS/animation) (In-depth information about CSS animations)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

