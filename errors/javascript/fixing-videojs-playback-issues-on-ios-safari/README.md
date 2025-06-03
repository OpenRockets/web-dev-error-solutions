# 🐞 Fixing VideoJS Playback Issues on iOS Safari


This document addresses a common problem developers encounter when using VideoJS on iOS Safari:  playback failing to initiate or exhibiting inconsistent behavior.  This often manifests as a blank screen, a spinning loading icon that never stops, or the video starting and then immediately pausing.  This is frequently caused by incompatibilities with specific video codecs or a lack of proper configuration within the VideoJS player.


## Description of the Error

The error isn't always accompanied by a specific error message in the browser's developer console.  Instead, you'll observe a failure to play the video despite the video file seemingly loading correctly.  This is often specific to iOS Safari and may work correctly in other browsers or on other operating systems.  The root cause usually boils down to the browser not supporting the supplied video codec or missing configuration options within VideoJS.


## Code Fix: Step-by-Step

Let's assume you're using an MP4 video, which is a common format, but having problems on iOS Safari. The solution involves using a more widely compatible codec and providing explicit sources within VideoJS.

**Step 1: Ensure Proper Codec**

iOS Safari generally supports H.264 video encoding with AAC audio.  If your MP4 uses a different codec (like HEVC), iOS Safari may fail to play it.  Ensure you encode your MP4 using H.264 video and AAC audio.  Tools like FFmpeg or Handbrake can re-encode your videos.

**Step 2:  Provide Multiple Video Sources with VideoJS**

VideoJS allows you to specify multiple sources for the video player, allowing the browser to select the most appropriate option.  This approach helps accommodate different devices and browsers.

```html
<!DOCTYPE html>
<html>
<head>
<title>VideoJS with Multiple Sources</title>
<link href="https://vjs.zencdn.net/7.20.3/video-js.css" rel="stylesheet">
<script src="https://vjs.zencdn.net/7.20.3/video.min.js"></script>
</head>
<body>
<video id="my-video" class="video-js vjs-big-play-centered" controls preload="auto" width="640" height="360" poster="poster.jpg">
  <source src="myvideo.mp4" type="video/mp4">
  <source src="myvideo.webm" type="video/webm">  <!-- fallback for browsers supporting webm -->
  <p class="vjs-no-js">
    To view this video please enable JavaScript, and consider upgrading to a web browser that <a href="https://videojs.com/html5-video-support/" target="_blank">supports HTML5 video</a>
  </p>
</video>
<script>
  var player = videojs('my-video');
</script>
</body>
</html>
```

Replace `myvideo.mp4` with your H.264/AAC encoded MP4 file, and optionally add a WebM source (`myvideo.webm`) as a fallback for browsers that prefer that format.  The `poster.jpg` attribute specifies a still image to display before playback begins.  This is crucial, especially on iOS, for faster initial load.

**Step 3: Test Thoroughly**

Test your implementation on a real iOS device running Safari, not just in the simulator.  Browser developer tools (accessed by opening the Safari Inspector) are useful for debugging any additional JavaScript errors.


## Explanation

The core reason this fix works is because it provides iOS Safari with a video source it understands reliably.  By explicitly including an MP4 encoded with H.264/AAC, we remove ambiguity and allow the browser to quickly select the appropriate codec for playback. The addition of a secondary source (e.g., WebM) offers a fallback if the primary source encounters problems.


## External References

* **VideoJS Documentation:** [https://docs.videojs.com/](https://docs.videojs.com/)  (Refer to the sections on source selection and troubleshooting for further information).
* **FFmpeg:** [https://ffmpeg.org/](https://ffmpeg.org/) (A powerful tool for video and audio encoding/decoding)
* **Handbrake:** [https://handbrake.fr/](https://handbrake.fr/) (A user-friendly video transcoding application)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

