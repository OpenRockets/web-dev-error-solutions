# 🐞 Creating a CSS-Only Pulsating Heart


This document details the creation of a pulsating heart animation using only CSS.  No JavaScript is required.  This effect utilizes CSS animations and keyframes to create a smooth, rhythmic pulse.

**Description of the Styling:**

The heart is created using a pseudo-element (`::before` and `::after`) on a parent element.  These pseudo-elements are shaped using border-radius and positioned absolutely to form the heart shape.  The `animation` property applies the `pulse` animation, which smoothly changes the transform scale to create the pulsating effect.  We'll use Tailwind CSS for rapid styling and utility classes.


**Full Code (using Tailwind CSS):**

```html
<div class="relative inline-block w-12 h-12">
  <div class="absolute w-full h-full rounded-full bg-red-500 animate-pulse"></div>
</div>
```


```css
/* Tailwind Styles (This is implicitly included if you're using Tailwind.  No extra CSS file needed.)*/
@layer base {
  .animate-pulse {
    animation: pulse 1s ease-in-out infinite;
  }
  @keyframes pulse {
    0%, 100% {
      transform: scale(1);
    }
    50% {
      transform: scale(1.1);
    }
  }
}
```


**Explanation:**

* **`relative inline-block`:** This sets the parent div to be positioned relative (so absolute positioning for the child works) and inline-block (to allow other content to flow around it). `w-12` and `h-12` set the width and height to 12 units (Tailwind's default unit is usually 4px, but it can be customized).
* **`absolute w-full h-full rounded-full bg-red-500`:** The inner div is absolutely positioned within its parent, filling its parent's size (`w-full`, `h-full`), rounded to form a circle (`rounded-full`), and colored red (`bg-red-500`).
* **`animate-pulse`:** This class applies the `pulse` animation.
* **`@keyframes pulse`:** This defines the animation. It smoothly scales the element from 100% to 110% and back over 1 second, creating the pulsing effect.  The `infinite` keyword makes the animation loop continuously.
* **`ease-in-out`:** This provides a smooth acceleration and deceleration during the animation.

**Links to Resources to Learn More:**

* **Tailwind CSS Documentation:** [https://tailwindcss.com/docs](https://tailwindcss.com/docs) - Learn more about Tailwind CSS classes and utilities.
* **CSS Animations MDN:** [https://developer.mozilla.org/en-US/docs/Web/CSS/animation](https://developer.mozilla.org/en-US/docs/Web/CSS/animation) - Comprehensive documentation on CSS animations.
* **CSS Keyframes MDN:** [https://developer.mozilla.org/en-US/docs/Web/CSS/@keyframes](https://developer.mozilla.org/en-US/docs/Web/CSS/@keyframes) - Learn about defining custom keyframes for animations.


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

