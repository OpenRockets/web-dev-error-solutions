# 🐞 Resolving CanvasJS Chart Rendering Issues in IE11


This document addresses a common problem encountered when using CanvasJS charts in Internet Explorer 11 (IE11): failure to render charts correctly or rendering blank spaces.  This is often due to IE11's limited support for certain HTML5 canvas features used by CanvasJS.

**Description of the Error:**

In IE11, you might encounter situations where a CanvasJS chart either doesn't render at all, displays a blank space where the chart should be, or renders incompletely with missing elements.  This is not a CanvasJS bug per se, but rather a compatibility issue with the older browser.  The browser's console may not always provide helpful error messages.

**Step-by-Step Code Fix:**

The most reliable solution involves using a polyfill, specifically one that addresses the `excanvas` compatibility issue sometimes found in older IE versions.  While CanvasJS itself attempts some level of compatibility, a direct polyfill is often necessary.  We'll use the `excanvas` library here (though other compatibility libraries might also work).

**1. Include the excanvas library:**

First, download the `excanvas.js` file (easily found with a web search, look for reputable sources).  Place this file in your project's JavaScript directory.  Then, include it in your HTML file *before* including the CanvasJS script:


```html
<!DOCTYPE HTML>
<html>
<head>
<script src="excanvas.js"></script>  <!-- Include excanvas BEFORE CanvasJS -->
<script src="https://canvasjs.com/assets/script/canvasjs.min.js"></script> </head>
<body>

<div id="chartContainer" style="height: 300px; width: 100%;"></div>

<script>
window.onload = function () {
    var chart = new CanvasJS.Chart("chartContainer", {
        title:{
            text: "Basic Column Chart"
        },
        data: [
        {
            type: "column",
            dataPoints: [
                { label: "Apple",  y: 10  },
                { label: "Orange", y: 15  },
                { label: "Banana", y: 25  }
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

**2. Verify CanvasJS Inclusion:**

Make absolutely sure you've correctly included the CanvasJS library in your project. Double-check the path and the file name (`canvasjs.min.js` or the unminified version).

**3. Test in IE11:**

Open your webpage in IE11 and verify that the chart renders correctly.  If not, inspect the browser's developer tools console for any additional error messages that might offer further clues.


**Explanation:**

`excanvas.js` provides a compatibility layer for older browsers that lack full support for the HTML5 canvas element.  By including it *before* the CanvasJS library, we ensure that CanvasJS has access to the necessary functionality to render the chart even in IE11's less-capable rendering engine.  The order of inclusion is critical.


**External References:**

* **CanvasJS Documentation:** [https://canvasjs.com/](https://canvasjs.com/)  (Check their documentation for browser compatibility details, although it might not explicitly mention the need for excanvas in all cases)
* **Excanvas (Search for this term):**  You will find several repositories and downloads for excanvas.js.  Choose a reliable source.  Note that this is an older library and might not be actively maintained.  Modern browsers generally don't require it.


**Copyright (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.**

