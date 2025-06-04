# 🐞 Fixing CanvasJS Chart Rendering Issues in IE11


## Description of the Error

A common problem encountered when using CanvasJS charts in older browsers like Internet Explorer 11 (IE11) is the failure of charts to render correctly or at all. This often manifests as a blank space where the chart should be, or as a partially rendered or distorted chart.  This is primarily due to IE11's limited support for certain HTML5 canvas features and rendering engines used by CanvasJS.

## Step-by-Step Code Fix

This fix focuses on ensuring compatibility with IE11 by using a polyfill (a piece of code that provides functionality missing in older browsers) for the `requestAnimationFrame` API, which CanvasJS relies on for smooth animations and rendering.  While CanvasJS generally works better with modern browsers, this specific issue can be resolved with this polyfill.

**1. Include the `requestAnimationFrame` Polyfill:**

You can include a polyfill directly in your HTML file or via a CDN. Here's an example using a CDN:

```html
<!DOCTYPE html>
<html>
<head>
<title>CanvasJS Chart in IE11</title>
<script src="https://cdnjs.cloudflare.com/ajax/libs/raf/3.3.0/raf.min.js"></script>  <!-- Polyfill -->
<script src="https://canvasjs.com/assets/script/canvasjs.min.js"></script> </head>
<body>
<div id="chartContainer" style="height: 300px; width: 100%;"></div>
<script>
window.onload = function () {
    var chart = new CanvasJS.Chart("chartContainer", {
        // Your chart configuration here... (see example below)
        title:{
            text: "IE11 Compatible Chart"
        },
        data: [
        {
            type: "column",
            dataPoints: [
                { label: "Apple", y: 10 },
                { label: "Orange", y: 15 },
                { label: "Banana", y: 25 }
            ]
        }
        ]
    });
    chart.render();
}
</script>
</body>
</html>
```

**2.  Your CanvasJS Chart Configuration:**

Replace the `// Your chart configuration here...` comment with your actual CanvasJS chart configuration.  The example above provides a simple column chart.  Refer to the CanvasJS documentation for more advanced configurations.


## Explanation

The `requestAnimationFrame` API is crucial for efficient animation and rendering in modern browsers. IE11's implementation might be incomplete or buggy, leading to rendering problems with CanvasJS. The polyfill essentially provides a fallback implementation of `requestAnimationFrame`, ensuring the API functions correctly even in older browsers like IE11. By including this polyfill, we bridge the compatibility gap and allow CanvasJS to function as expected.

## External References

* **CanvasJS Documentation:** [https://canvasjs.com/docs/](https://canvasjs.com/docs/)  (Refer to their documentation for chart configuration and other details)
* **`requestAnimationFrame` Polyfill (raf.js):** [https://github.com/cwilso/requestAnimationFrame](https://github.com/cwilso/requestAnimationFrame) (Source for the polyfill used)
* **MDN Web Docs - `requestAnimationFrame()`:** [https://developer.mozilla.org/en-US/docs/Web/API/window/requestAnimationFrame](https://developer.mozilla.org/en-US/docs/Web/API/window/requestAnimationFrame) (Understanding `requestAnimationFrame`)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

