# 🐞 Fixing VideoJS Playback Issues on iOS Safari due to CORS


## Description of the Error

A common issue encountered when integrating VideoJS into a web application, particularly on iOS Safari, is the failure to play videos due to Cross-Origin Resource Sharing (CORS) errors.  This happens when the video file's origin (the server where the video is hosted) differs from the origin of the webpage embedding the VideoJS player.  iOS Safari is particularly strict about enforcing CORS policies.  The error might not manifest as a clear error message in the browser console, but instead as a blank player or a video that simply won't start.


## Fixing Steps

This example assumes your video is hosted on a different domain than your website.  Let's say your website is at `https://www.mywebsite.com` and your video is at `https://video.externalsite.com/myvideo.mp4`.

**Step 1: Configure CORS Headers on the Video Server**

The most crucial step is to configure the server hosting your video files to send the correct CORS headers.  This tells the browser that your website is allowed to access the video. You need to add these headers to the response from the video server:

```
Access-Control-Allow-Origin: https://www.mywebsite.com  // Replace with your website's origin
Access-Control-Allow-Methods: GET
Access-Control-Max-Age: 3600 //Optional: Cache control for 1 hour
```

The `Access-Control-Allow-Origin` header specifies the origin(s) allowed to access the resource.  You can use `*` to allow all origins, but this is generally discouraged for security reasons. It's best to specify your website's origin precisely.

**Step 2:  Verify Server Configuration**

Use a tool like Browser developer tools (Network tab) or a dedicated CORS checker (see references below) to confirm that your server is indeed sending the necessary headers when requesting your video.

**Step 3: VideoJS Player Code (Example)**

Ensure your VideoJS player is correctly configured to point to your video file.  Here's a basic example:


```html
<!DOCTYPE html>
<html>
<head>
  <title>VideoJS Example</title>
  <link href="https://vjs.zencdn.net/7.20.3/video-js.css" rel="stylesheet">
  <script src="https://vjs.zencdn.net/7.20.3/video.min.js"></script>
</head>
<body>

  <video id="my-video" class="video-js" controls preload="auto" width="640" height="360" poster="poster.jpg"
         data-setup='{}'>
    <source src="https://video.externalsite.com/myvideo.mp4" type="video/mp4">
    <p class="vjs-no-js">
      To view this video please enable JavaScript, and consider upgrading to a
      web browser that <a href="https://videojs.com/html5-video-support/" target="_blank">supports HTML5 video</a>
    </p>
  </video>

  <script>
    var player = videojs('my-video');
  </script>
</body>
</html>
```

Remember to replace `"https://video.externalsite.com/myvideo.mp4"` and `"poster.jpg"` with your actual video and poster URLs.


## Explanation

The CORS error arises because the browser, acting as a security measure, prevents the webpage from accessing resources from a different origin without explicit permission from the server hosting those resources.  By adding the appropriate CORS headers, the server grants the necessary permission, allowing the browser to load and play the video.


## External References

* **VideoJS Documentation:** [https://videojs.com/](https://videojs.com/)
* **CORS Explained:** [https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS)
* **Online CORS Header Checker:** [Search for "CORS header checker" on your preferred search engine; many online tools are available.]


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

