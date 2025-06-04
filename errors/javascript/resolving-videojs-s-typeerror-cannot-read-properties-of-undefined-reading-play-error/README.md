# 🐞 Resolving VideoJS's "TypeError: Cannot read properties of undefined (reading 'play')" Error


## Description of the Error

The "TypeError: Cannot read properties of undefined (reading 'play')" error in Video.js frequently arises when attempting to interact with the player's `play()` method before the player is fully initialized or loaded. This usually happens when you try to trigger playback prematurely, often within an event handler that fires *before* the Video.js player has finished setting up its internal components.  The player's internal `player` object is still `undefined`, hence the error when you try to access its `.play()` method.

## Step-by-Step Code Fix

Let's assume you have a basic Video.js setup like this:

```html
<!DOCTYPE html>
<html>
<head>
<title>Video.js Example</title>
<script src="https://vjs.zencdn.net/7.20.3/video.js"></script>
<link href="https://vjs.zencdn.net/7.20.3/video-js.css" rel="stylesheet">
</head>
<body>

<video id="my-video" class="video-js" controls preload="auto" width="640" height="360" poster="poster.jpg" data-setup='{"sources": [{"src": "myvideo.mp4", "type": "video/mp4"}]}'>
  <source src="myvideo.mp4" type="video/mp4">
  <p class="vjs-no-js">To view this video please enable JavaScript, and consider upgrading to a web browser that <a href="https://videojs.com/html5-video-support/" target="_blank">supports HTML5 video</a></p>
</video>

<script>
  var player = videojs('my-video');
  // Incorrect placement of play() - this will likely cause the error
  player.play();  
</script>
</body>
</html>
```

The problem lies in calling `player.play()` directly after creating the `player` object. Video.js needs time to initialize.  Here's the corrected code:

```html
<!DOCTYPE html>
<html>
<head>
<title>Video.js Example</title>
<script src="https://vjs.zencdn.net/7.20.3/video.js"></script>
<link href="https://vjs.zencdn.net/7.20.3/video-js.css" rel="stylesheet">
</head>
<body>

<video id="my-video" class="video-js" controls preload="auto" width="640" height="360" poster="poster.jpg" data-setup='{"sources": [{"src": "myvideo.mp4", "type": "video/mp4"}]}'>
  <source src="myvideo.mp4" type="video/mp4">
  <p class="vjs-no-js">To view this video please enable JavaScript, and consider upgrading to a web browser that <a href="https://videojs.com/html5-video-support/" target="_blank">supports HTML5 video</a></p>
</video>

<script>
  var player = videojs('my-video');

  // Use the 'ready' event to ensure the player is initialized
  player.ready(function(){
    this.play();
  });

</script>
</body>
</html>
```

The key change is using the `player.ready()` method. This ensures that the `play()` method is called only after the Video.js player has fully loaded and is ready to receive commands.


## Explanation

The `ready` event is a Video.js event that fires when the player is completely initialized. By placing the `play()` call inside the `ready` callback function, we guarantee that the player object is fully defined and ready to accept the `play()` command, preventing the "TypeError: Cannot read properties of undefined (reading 'play')" error.

## External References

* **Video.js Documentation:** [https://docs.videojs.com/](https://docs.videojs.com/)  (Look for information on events and player lifecycle)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

