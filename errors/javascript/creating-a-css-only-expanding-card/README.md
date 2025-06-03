# 🐞 Creating a CSS-Only Expanding Card


This document details a CSS-only solution for creating an expanding card effect.  The card expands vertically when hovered over, revealing hidden content. This technique utilizes CSS transitions and the `:hover` pseudo-class for a smooth and interactive user experience.  No JavaScript is required.

**Description of the Styling:**

The card is composed of two main parts: a header and a content section. The content section is initially hidden using `max-height: 0` and `overflow: hidden`.  On hover, the `max-height` is dynamically adjusted to allow the content to become visible.  Smooth transitions are achieved using CSS transitions on `max-height`.  We'll use Tailwind CSS for rapid styling.

**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Expanding Card</title>
  <script src="https://cdn.tailwindcss.com"></script>
</head>
<body>

<div class="w-64 bg-white rounded-lg shadow-md overflow-hidden mx-auto my-8">
  <div class="p-4 bg-gray-200">
    <h2 class="text-lg font-semibold">Card Title</h2>
  </div>
  <div class="p-4 transition-max-h duration-300 ease-in-out overflow-hidden max-h-0">
    <p class="text-gray-700">This is the hidden content of the card.  It will expand when you hover over the card.  Add as much text as you need to see the expanding effect.</p>
    <p class="text-gray-700">More hidden content here...</p>
  </div>
</div>


</body>
</html>
```

**Explanation:**

* **`w-64`**: Sets the card width to 64 units (Tailwind's default unit is usually relative to the parent element).
* **`bg-white`**: Sets the background color to white.
* **`rounded-lg`**: Adds rounded corners.
* **`shadow-md`**: Adds a medium shadow.
* **`overflow-hidden`**: Prevents content from overflowing the card's boundaries.
* **`max-h-0`**:  Initially sets the maximum height of the content section to 0, hiding it.
* **`transition-max-h duration-300 ease-in-out`**: This is crucial for the animation. It applies a transition to the `max-height` property, taking 300 milliseconds with an ease-in-out timing function.
* **`:hover` (Implicit in the HTML structure):** The inner `<div>` with the content only expands its `max-height` when the outer `div` (the entire card) is hovered over.  Tailwind handles this implicitly by applying the styles to the inner `div` only on hover of the parent.  You could also do this explicitly with `:hover > div`. To make the content expand to its natural height on hover, remove the `max-h-0` class and dynamically adjust the `max-height` in your CSS.  This is an advanced technique, and the simple solution above suffices for many use cases.

**Links to Resources to Learn More:**

* **Tailwind CSS Documentation:** [https://tailwindcss.com/docs](https://tailwindcss.com/docs)  - Learn more about Tailwind CSS utility classes.
* **CSS Transitions:** [https://developer.mozilla.org/en-US/docs/Web/CSS/transition](https://developer.mozilla.org/en-US/docs/Web/CSS/transition) -  Learn more about CSS transitions.
* **CSS Pseudo-classes:** [https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes) - Learn more about CSS pseudo-classes like `:hover`.


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

