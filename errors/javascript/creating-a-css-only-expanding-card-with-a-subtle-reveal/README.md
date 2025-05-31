# 🐞 Creating a CSS-only Expanding Card with a Subtle Reveal


This document details a CSS-only technique to create an expanding card effect.  The card expands smoothly when hovered over, revealing additional content hidden initially. We'll utilize CSS transitions and transforms to achieve this effect without JavaScript.  This example is applicable to both standard CSS3 and frameworks like Tailwind CSS (though the Tailwind implementation would simply replace the standard CSS classes with their Tailwind equivalents).

**Description of the Styling:**

The card starts with a compact size. On hover, it expands smoothly to a larger size, revealing hidden content beneath.  We'll use a `max-height` property initially set to a small value.  The `transition` property will handle the smooth animation during the expansion.  We'll also use `transform: scale()` for a subtle "zoom in" effect alongside the height expansion.

**Full Code (Standard CSS):**

```html
<!DOCTYPE html>
<html>
<head>
<title>Expanding Card</title>
<style>
.card {
  background-color: #f0f0f0;
  border-radius: 8px;
  overflow: hidden; /* Hide content that overflows during transition */
  transition: max-height 0.3s ease-in-out, transform 0.3s ease-in-out; /* Smooth transition */
  max-height: 100px; /* Initially compact */
  box-shadow: 2px 2px 5px rgba(0, 0, 0, 0.1); /* Add a subtle shadow */
}

.card:hover {
  max-height: 300px; /* Expand on hover */
  transform: scale(1.02); /* Subtle zoom effect */
}

.card-content {
  padding: 15px;
}

.hidden-content {
  display: none; /* Initially hidden */
}

.card:hover .hidden-content {
  display: block; /* Show on hover */
}
</style>
</head>
<body>

<div class="card">
  <div class="card-content">
    <h2>Card Title</h2>
    <p>Some initial content.</p>
    <div class="hidden-content">
      <h3>Hidden Section</h3>
      <p>This content is revealed on hover.</p>
    </div>
  </div>
</div>

</body>
</html>
```

**Full Code (Tailwind CSS):**

```html
<!DOCTYPE html>
<html>
<head>
<title>Expanding Card</title>
<script src="https://cdn.tailwindcss.com"></script>
</head>
<body>

<div class="card bg-gray-100 rounded-lg overflow-hidden transition-all duration-300 ease-in-out max-h-[100px] shadow-md">
  <div class="card-content p-4">
    <h2 class="text-xl font-bold">Card Title</h2>
    <p class="mb-4">Some initial content.</p>
    <div class="hidden-content hidden">
      <h3 class="text-lg font-semibold">Hidden Section</h3>
      <p>This content is revealed on hover.</p>
    </div>
  </div>
</div>

</body>
</html>
```

**(Remember to include the Tailwind CSS CDN link in your `<head>` for the Tailwind version.)**


**Explanation:**

* **`max-height`:** Controls the initial height of the card.
* **`transition`:** Specifies the properties to animate (`max-height` and `transform`), the duration (0.3 seconds), and the easing function (`ease-in-out`).
* **`transform: scale(1.02)`:**  Adds a subtle scaling effect on hover, enhancing the visual expansion.
* **`overflow: hidden`:** Prevents content from spilling out of the card during the transition.
* **`.hidden-content`:** This class is initially hidden and revealed on hover using the `:hover` pseudo-class.

**External References:**

* [MDN Web Docs on CSS Transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
* [MDN Web Docs on CSS Transforms](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
* [Tailwind CSS Documentation](https://tailwindcss.com/)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

# Expanding Card Hover Animation Not Working

---

## Error Message

```
No specific error message, but the card does not expand or reveal extra content on hover as expected.
```

---

## Context

- **Where does this error occur?**  
  In a plain HTML/CSS setup where a card component is supposed to expand and reveal more content on hover.

- **When does it typically happen?**  
  When the card is not styled properly, or CSS transitions and hover selectors are not applied correctly.

---

## Problem

The issue arises when the `.card-extra` content is not revealed on hover due to missing or incorrect styling for transitions, `max-height`, or `opacity`. This usually happens if either:

- Transitions are not smooth.
- The `max-height` is not set to a high enough value.
- The `opacity` or `overflow` rules are misconfigured.

---

## Solution(s)

### 1. Proper CSS for Expanding Card

**Steps:**
1. Wrap the content in a `.card` container.
2. Use `max-height` and `opacity` with transitions for smooth animation.
3. Add a `.card:hover` rule to expand the card and reveal extra content.

```html
<!DOCTYPE html>
<html>
<head>
  <title>Expanding Card</title>
  <style>
    .card {
      background-color: #f0f0f0;
      border-radius: 8px;
      box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
      overflow: hidden;
      transition: max-height 0.5s ease-in-out;
      max-height: 100px;
    }

    .card:hover {
      max-height: 300px;
    }

    .card-content {
      padding: 15px;
    }

    .card-title {
      font-weight: bold;
      margin-bottom: 5px;
    }

    .card-text {
      font-size: 14px;
      line-height: 1.5;
    }

    .card-extra {
      opacity: 0;
      max-height: 0;
      overflow: hidden;
      transition: opacity 0.5s ease, max-height 0.5s ease;
    }

    .card:hover .card-extra {
      opacity: 1;
      max-height: 200px;
    }
  </style>
</head>
<body>

<div class="card">
  <div class="card-content">
    <h3 class="card-title">Card Title</h3>
    <p class="card-text">This is a short summary of the card content.</p>
    <p class="card-text card-extra">This is the extra content that will be revealed on hover. This text is initially hidden but now animates smoothly into view.</p>
  </div>
</div>

</body>
</html>
```

---

## Example

<details>
<summary>Show Example</summary>

**index.html**
```html
<!-- See complete solution code above -->
```
</details>

---

## References

- [CSS Transitions – MDN Docs](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
- [Stack Overflow – CSS expand card on hover](https://stackoverflow.com/questions/3937513/css-expand-div-on-hover)

---

## Version

- **Solution version:** 1.0.0
- **Last updated:** 2025-05-31
- **Contributed by:** [shanthi1999/](https://github.com/shanthi1999/)

---

## Tags

`#css` `#html` `#hover` `#animation` `#transition` `#ui`

---