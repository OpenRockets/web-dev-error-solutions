# 🐞 CSS Challenge:  Animated Expanding Card with Tailwind CSS


This challenge involves creating an animated card that expands to reveal more content when clicked. We'll use Tailwind CSS for rapid styling and efficient class-based development.  The animation will be subtle and user-friendly.

**Description of the Styling:**

The card will initially appear compact, displaying a title and a small image.  Upon clicking, it will smoothly expand vertically, revealing a longer description and potentially more details.  We'll use Tailwind's utility classes for transitions and animations to achieve a polished effect. The expanded state will be visually distinct from the collapsed state, perhaps using different padding, spacing, and potentially even a background color change.

**Full Code:**

```html
<div class="max-w-sm rounded overflow-hidden shadow-lg cursor-pointer transition duration-500 ease-in-out" 
     onclick="this.classList.toggle('expanded')">
  <img class="w-full" src="https://via.placeholder.com/350x150" alt="Card Image">
  <div class="px-6 py-4">
    <div class="font-bold text-xl mb-2">Card Title</div>
    <p class="text-gray-700 text-base">
      This is a short description of the card.
    </p>
  </div>
  <div class="px-6 pt-4 pb-2 hidden" id="expanded-content">
    <p class="text-gray-700 text-base">
      This is the expanded content of the card.  You can add more details here. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed nec enim nec libero aliquet ultrices.
    </p>
  </div>
</div>


<style>
.expanded {
  max-height: 500px; /* Adjust as needed */
  /* Add other styles for the expanded state, if required */
}
</style>
```

**Explanation:**

* **`max-w-sm rounded overflow-hidden shadow-lg cursor-pointer`**: These Tailwind classes provide basic styling: maximum width, rounded corners, hidden overflow, shadow, and a cursor that indicates it's clickable.
* **`transition duration-500 ease-in-out`**: This applies a smooth transition with a duration of 500 milliseconds and an ease-in-out timing function.
* **`onclick="this.classList.toggle('expanded')"`**: This JavaScript code toggles the `expanded` class on the card when clicked.  This class is defined in the `<style>` tag.
* **`.hidden`**: This Tailwind class initially hides the expanded content.
* **`#expanded-content`**:  This div holds the content to be revealed upon expansion.
* **The Custom CSS**: The `max-height` property in the `.expanded` class controls the maximum height of the expanded card.  You can adjust this value as needed.  Additional styles can be added here to further differentiate the expanded and collapsed states.

**Links to Resources to Learn More:**

* **Tailwind CSS Documentation:** [https://tailwindcss.com/docs](https://tailwindcss.com/docs)  - The official Tailwind CSS documentation is an excellent resource for learning about all its features and utility classes.
* **CSS Transitions and Animations:** [https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions/Using_CSS_transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions/Using_CSS_transitions) and [https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations/Using_CSS_animations](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations/Using_CSS_animations) -  Learn more about creating smooth animations and transitions in CSS.


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

