# 🐞 Fixing VideoJS's `TypeError: Cannot read properties of undefined (reading 'currentTime')`


## Description of the Error

A common error encountered when working with Video.js is `TypeError: Cannot read properties of undefined (reading 'currentTime')`. This typically arises when trying to access the `currentTime` property of a Video.js player instance before the player has fully initialized or loaded the video.  This means your code attempts to read the `currentTime` before the video player object is ready.

## Steps to Fix the Error

This error usually indicates a timing issue where you're trying to access the player before it's ready. The solution involves ensuring that your code executes *after* the player has been initialized and the video metadata is loaded.  We'll use the `ready` event provided by Video.js.

**Step 1: Include Video.js**

First, ensure that you've correctly included the Video.js library in your HTML file.  This typically involves adding a `<script>` tag linking to the Video.js CDN or a local copy.

```html
<!DOCTYPE html>
<html>
<head>
  <title>Video.js Example</title>
  <script src="https://cdn.jsdelivr.net/npm/video.js@7/dist/video.min.js"></script>
  <link href="https://cdn.jsdelivr.net/npm/video.js@7/dist/video-js.css" rel="stylesheet">
</head>
<body>

  <video id="my-video" class="video-js vjs-big-play-centered" controls preload="auto" width="640" height="360"
         poster="poster.png" data-setup='{"sources": [{"src": "my-video.mp4", "type": "video/mp4"}]}'>
    <p class="vjs-no-js">
      To view this video please enable JavaScript, and consider upgrading to a
      web browser that <a href="https://videojs.com/html5-video-support/" target="_blank">supports HTML5 video</a>
    </p>
  </video>

  <script>
    // Our fix will go here
  </script>

</body>
</html>
```

**Step 2: Use the `ready` event**

Instead of directly accessing `player.currentTime` immediately, wait for the `ready` event.  This event fires when the player is fully initialized and ready to use.

```javascript
var player = videojs('my-video');

player.ready(function(){
  console.log("Player is ready!");
  console.log("Current time:", this.currentTime()); //Access currentTime here

  // Add event listeners or perform other actions here
  this.on('timeupdate', function() {
      console.log("Current Time Updated:", this.currentTime());
  });
});
```


## Explanation

The `ready` event ensures that your code runs only after the Video.js player has finished loading and is ready to interact with.  Attempting to access `currentTime` before the player is initialized leads to the `undefined` error because the player object isn't fully formed yet.  The `this` keyword inside the `ready` callback refers to the Video.js player instance.


## External References

* **Video.js Documentation:** [https://videojs.com/](https://videojs.com/)  (Look for their documentation on events and player initialization)


## Copyright (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

