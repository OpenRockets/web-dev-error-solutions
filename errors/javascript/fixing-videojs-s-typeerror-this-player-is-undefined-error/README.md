# 🐞 Fixing VideoJS's "TypeError: this.player is undefined" Error


## Description of the Error

A common error encountered when working with Video.js is the `TypeError: this.player is undefined` error. This typically occurs when trying to access Video.js player instance methods or properties from within a plugin or custom function before the player has been fully initialized.  The error manifests because the `this.player` object hasn't been properly bound to the Video.js player instance. This often happens within event handlers or callback functions.

## Step-by-Step Code Fix

Let's assume you're trying to add a custom button that toggles fullscreen mode.  The erroneous code might look like this:

```javascript
// Erroneous code - this.player is undefined inside the click handler
videojs('my-video').ready(function() {
  const player = this; // this is the player instance *inside* the ready function
  const fullscreenButton = document.createElement('button');
  fullscreenButton.innerHTML = 'Fullscreen';
  fullscreenButton.addEventListener('click', function() {
    if (player.isFullscreen()) {
      player.exitFullscreen();
    } else {
      player.requestFullscreen();
    }
  });
  player.controlBar.addChild(fullscreenButton);
});
```

The problem is the `click` event handler is defined separately. The `this` context within that function is no longer the Video.js player instance.  Here's the corrected code:

```javascript
// Corrected code - using an arrow function to preserve context
videojs('my-video').ready(function() {
  const player = this;
  const fullscreenButton = document.createElement('button');
  fullscreenButton.innerHTML = 'Fullscreen';
  fullscreenButton.addEventListener('click', () => { // Arrow function preserves 'this'
    if (player.isFullscreen()) {
      player.exitFullscreen();
    } else {
      player.requestFullscreen();
    }
  });
  player.controlBar.addChild(fullscreenButton);
});
```

Alternatively, you can explicitly bind the `this` context:

```javascript
// Corrected code - using bind to explicitly set the context
videojs('my-video').ready(function() {
  const player = this;
  const fullscreenButton = document.createElement('button');
  fullscreenButton.innerHTML = 'Fullscreen';
  const fullscreenClickHandler = function() {
    if (player.isFullscreen()) {
      player.exitFullscreen();
    } else {
      player.requestFullscreen();
    }
  }.bind(player); // bind 'this' to the player instance
  fullscreenButton.addEventListener('click', fullscreenClickHandler);
  player.controlBar.addChild(fullscreenButton);
});
```

Both corrected examples solve the problem by ensuring the `this` keyword correctly references the Video.js player within the event handler.


## Explanation

The core issue stems from JavaScript's `this` keyword and how it's bound in different function contexts.  Regular functions (`function() { ... }`) have their `this` value determined by how they are called.  In the erroneous example, the `addEventListener` callback function is called later, independently of the `ready` function's context, resulting in `this` being the `window` object or undefined.

Arrow functions (`() => { ... }`) lexically bind `this`, inheriting the `this` value from their surrounding scope. This is why the arrow function approach elegantly solves the problem.  The `.bind()` method explicitly sets the `this` value of a function.


## External References

* **Video.js Documentation:** [https://videojs.com/](https://videojs.com/)  (Check their documentation for plugin development and best practices)
* **JavaScript `this` keyword:** [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/this](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/this)
* **MDN Arrow Functions:** [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

