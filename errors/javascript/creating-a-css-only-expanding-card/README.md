# 🐞 Creating a CSS-only Expanding Card


This document details a CSS-only solution to create an expanding card effect.  The card expands vertically to reveal more content when clicked.  This technique uses CSS transitions and the `:target` pseudo-class for a smooth and elegant animation without JavaScript.


**Description of the Styling:**

The styling utilizes a simple card structure with a hidden content section.  The primary interaction relies on a hidden anchor link that acts as a toggle.  Clicking the card triggers the link, changing the URL fragment, which then targets the hidden content section, revealing it via a CSS transition.  The design uses Tailwind CSS for rapid styling.

**Full Code:**

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Expanding Card</title>
<link href="https://cdn.jsdelivr.net/npm/tailwindcss@2.2.19/dist/tailwind.min.css" rel="stylesheet">
<style>
  .card {
    width: 300px;
    border: 1px solid #ccc;
    border-radius: 5px;
    overflow: hidden;
  }

  .card-content {
    padding: 1rem;
    transition: max-height 0.5s ease-in-out;
  }

  .card-content.collapsed {
    max-height: 100px; /* Initial height */
  }

  .card-content:not(.collapsed) {
    max-height: 500px; /* Expanded height */
  }

  .expand-link {
    display: block;
    position: relative;
    width: 100%;
    padding: 1rem;
    cursor: pointer;
    text-decoration: none;
    color: inherit;
  }
</style>
</head>
<body class="bg-gray-100">
  <div class="container mx-auto p-8">
    <a href="#content1" class="expand-link">
      <div class="card bg-white shadow-md">
        <div class="card-content collapsed" id="content1">
          <h2 class="text-xl font-bold mb-2">Card Title</h2>
          <p class="text-gray-700">This is some sample text for the card content.  It will expand when you click the card.</p>
          <p class="text-gray-700">More content here...</p>
          <p class="text-gray-700">Even more content here...</p>
        </div>
      </div>
    </a>


    <a href="#content2" class="expand-link mt-4">
      <div class="card bg-white shadow-md">
        <div class="card-content collapsed" id="content2">
          <h2 class="text-xl font-bold mb-2">Another Card</h2>
          <p class="text-gray-700">Different content for this card.</p>
        </div>
      </div>
    </a>
  </div>
</body>
</html>
```

**Explanation:**

1. **Structure:**  The HTML creates a simple card structure with a hidden anchor (`<a>`) element wrapping the card. The `id` attribute on the inner `div` corresponds to the `href` of the anchor.  The `collapsed` class initially sets a max-height, hiding the extra content.

2. **CSS Transitions:** The `transition` property on `.card-content` smoothly animates the `max-height` change.

3. **`max-height` and `:target`:** The `max-height` property controls the visible height. The `:not(.collapsed)` selector, combined with the `:target` pseudo-class (triggered by the anchor click), removes the `collapsed` class and reveals the full content.  The initial `max-height` is set to a small value using the `collapsed` class.

4. **Tailwind CSS:**  Tailwind CSS classes are used for quick styling, providing responsive design features.


**Links to Resources to Learn More:**

* **Tailwind CSS Documentation:** [https://tailwindcss.com/docs](https://tailwindcss.com/docs)
* **CSS Transitions and Animations:** [https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions/Using_CSS_transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions/Using_CSS_transitions)
* **CSS Pseudo-classes:** [https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

