# 🐞 Resolving CanvasJS Chart Rendering Issues in Internet Explorer 11


## Description of the Error

A common problem encountered when using CanvasJS charts in older browsers, particularly Internet Explorer 11 (IE11), is the failure of charts to render correctly or at all.  This often manifests as a blank space where the chart should be, or as a partially rendered chart with missing elements.  IE11's limitations in supporting modern JavaScript features and Canvas rendering capabilities are often the root cause.

## Step-by-Step Code Fix

This solution focuses on using a polyfill to address potential compatibility issues with the `Canvas` element. We'll use a combination of a Canvas polyfill and ensuring the correct inclusion of the CanvasJS library.

**Step 1: Include a Canvas Polyfill**

We'll use a popular and widely compatible polyfill like **excanvas**. While not directly addressing all CanvasJS issues in IE11, it can significantly mitigate problems related to Canvas element support.  You can find it via a CDN or download it and include it locally.  For this example, we'll use a CDN link:

```html
<script src="https://cdnjs.cloudflare.com/ajax/libs/excanvas/r3/excanvas.js"></script>
```
Place this `<script>` tag *before* including the CanvasJS library in your HTML's `<head>` section.

**Step 2: Include CanvasJS Library**

Ensure you've correctly included the CanvasJS library.  Replace `"path/to/canvasjs.min.js"` with the actual path to your CanvasJS file.

```html
<script src="path/to/canvasjs.min.js"></script>
```


**Step 3: Chart Initialization (Example)**

This is a basic example of initializing a CanvasJS chart. Replace the placeholder data with your actual data.

```javascript
window.onload = function () {
  var chart = new CanvasJS.Chart("chartContainer", {
    title:{
      text: "Simple Chart"
    },
    data: [
    {
      type: "column",
      dataPoints: [
        { label: "Apple", y: 10 },
        { label: "Banana", y: 15 },
        { label: "Orange", y: 20 }
      ]
    }
    ]
  });
  chart.render();
};
```

**Step 4:  Provide a Container**

Make sure you have a div element with the ID "chartContainer" in your HTML to hold the chart.

```html
<div id="chartContainer" style="height: 300px; width: 500px;"></div>
```


## Explanation

IE11's limited support for modern web technologies can cause problems with Canvas-based libraries like CanvasJS. The `excanvas` polyfill helps bridge the gap by providing a fallback implementation of the Canvas API for older browsers. This allows CanvasJS to function more reliably in IE11, though complete compatibility is not guaranteed for all CanvasJS features.  Always thoroughly test your chart in IE11 after implementing this solution.


## External References

* **CanvasJS Documentation:** [https://canvasjs.com/](https://canvasjs.com/)  (Check their documentation for browser compatibility specifics.)
* **excanvas on CDNJS:** [https://cdnjs.cloudflare.com/ajax/libs/excanvas/r3/excanvas.js](https://cdnjs.cloudflare.com/ajax/libs/excanvas/r3/excanvas.js) (Alternative sources may be found)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

