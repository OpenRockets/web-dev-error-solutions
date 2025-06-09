# 🐞 CSS Challenge:  Animated Expanding Card with Tailwind CSS


This challenge focuses on creating an animated expanding card using Tailwind CSS.  The card will have a subtle hover effect, expanding slightly on mouseover to reveal more details.  This example demonstrates the use of Tailwind's utility classes for responsive design and animations, avoiding the need for extensive custom CSS.

**Description of the Styling:**

The card will be a simple rectangular box containing an image and some text.  On hover, the card will smoothly increase in width and height, giving a visual cue of interactivity. We'll use Tailwind's transition and transform utilities to achieve the animation. The styling will be clean and modern, leveraging Tailwind's pre-defined classes for a concise and efficient implementation.

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
<body class="bg-gray-100">

  <div class="container mx-auto p-8">
    <div class="max-w-sm rounded overflow-hidden shadow-lg hover:shadow-2xl transition duration-300 transform hover:scale-105 cursor-pointer">
      <img class="w-full" src="https://via.placeholder.com/350x150" alt="Card Image">
      <div class="px-6 py-4">
        <div class="font-bold text-xl mb-2">Card Title</div>
        <p class="text-gray-700 text-base">
          Lorem ipsum dolor sit amet, consectetur adipisicing elit. Voluptatibus quia, nulla! Maiores et perferendis eaque, exercitationem praesentium nihil.
        </p>
      </div>
      <div class="px-6 pt-4 pb-2">
        <span class="inline-block bg-gray-200 rounded-full px-3 py-1 text-sm font-semibold text-gray-700 mr-2">#photography</span>
        <span class="inline-block bg-gray-200 rounded-full px-3 py-1 text-sm font-semibold text-gray-700 mr-2">#travel</span>
        <span class="inline-block bg-gray-200 rounded-full px-3 py-1 text-sm font-semibold text-gray-700">#nature</span>
      </div>
    </div>
  </div>

</body>
</html>
```

**Explanation:**

* **`container mx-auto p-8`**: Centers the card horizontally and adds padding.
* **`max-w-sm`**: Sets a maximum width for responsiveness.
* **`rounded overflow-hidden shadow-lg`**: Styles the card with rounded corners, prevents content overflow, and adds a shadow.
* **`hover:shadow-2xl`**: Increases the shadow on hover.
* **`transition duration-300 transform hover:scale-105`**: Adds a smooth transition effect and scales the card on hover.
* **`cursor-pointer`**: Changes the cursor to a pointer on hover.
*  The rest of the classes style the image and text content within the card using Tailwind's pre-built styles.


**Links to Resources to Learn More:**

* **Tailwind CSS Documentation:** [https://tailwindcss.com/docs](https://tailwindcss.com/docs)
* **Tailwind CSS Playgrounds:**  Various online playgrounds exist where you can experiment with Tailwind classes.  Search for "Tailwind CSS playground".


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

