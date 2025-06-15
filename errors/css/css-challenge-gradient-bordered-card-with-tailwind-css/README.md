# 🐞 CSS Challenge:  Gradient-Bordered Card with Tailwind CSS


This challenge involves creating a visually appealing card using Tailwind CSS. The card will feature a subtle gradient border, rounded corners, and a simple content area.  We'll leverage Tailwind's utility classes to achieve this efficiently.

## Description of the Styling

The card will be rectangular with soft rounded corners.  The border will be a subtle linear gradient, transitioning between two light colors. The content within the card will be centered and have some basic padding for readability.

## Full Code

```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Gradient-Bordered Card</title>
  <script src="https://cdn.tailwindcss.com"></script>
</head>
<body class="bg-gray-100">

  <div class="max-w-sm mx-auto mt-10 bg-white rounded-lg shadow-md p-6">
    <h2 class="text-xl font-bold mb-4 text-gray-800">My Card Title</h2>
    <p class="text-gray-600 text-base">This is some sample text for the card content.  You can add more details here as needed.  Lorem ipsum dolor sit amet, consectetur adipiscing elit.</p>
    <button class="mt-4 bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">Learn More</button>
  </div>

</body>
</html>
```

To make the card have a gradient border, we'll add the following CSS (you can add this directly within a `<style>` tag in the `<head>` or in a separate CSS file linked to your HTML):

```css
.gradient-border {
  border: 2px solid;
  border-image: linear-gradient(to right, #FF6F61, #FF974C) 1 100%; /*Adjust colors as needed*/
}
```

And add the `gradient-border` class to the main card div:

```html
<div class="max-w-sm mx-auto mt-10 bg-white rounded-lg shadow-md p-6 gradient-border">
```


## Explanation

* **`max-w-sm`**: This limits the card's maximum width to a small size.
* **`mx-auto`**: This centers the card horizontally.
* **`mt-10`**: This adds a top margin of 10 units (Tailwind's spacing system).
* **`bg-white`**: This sets the background color to white.
* **`rounded-lg`**: This applies large rounded corners.
* **`shadow-md`**: This adds a medium shadow effect.
* **`p-6`**: This adds padding of 6 units all around.
* **`text-xl`, `font-bold`, `text-gray-800`**: These style the title.
* **`text-gray-600`, `text-base`**: These style the paragraph text.
* **`bg-blue-500`, `hover:bg-blue-700`, `text-white`, `font-bold`, `py-2`, `px-4`, `rounded`**: These style the button.
* **`gradient-border`**:  This applies our custom gradient border using border-image.

## Links to Resources to Learn More

* **Tailwind CSS Official Documentation:** [https://tailwindcss.com/docs](https://tailwindcss.com/docs)
* **CSS Border-Image Property:** [https://developer.mozilla.org/en-US/docs/Web/CSS/border-image](https://developer.mozilla.org/en-US/docs/Web/CSS/border-image)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

