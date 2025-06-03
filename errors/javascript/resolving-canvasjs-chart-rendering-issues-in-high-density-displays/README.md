# 🐞 Resolving CanvasJS Chart Rendering Issues in High-Density Displays


## Description of the Error

A common problem encountered when using CanvasJS charts, especially on high-density displays (retina displays), is blurry or pixelated chart rendering. This occurs because the chart's default rendering resolution doesn't scale appropriately to the screen's higher pixel density.  The chart might appear correctly sized, but the elements within (lines, text, markers) lack crispness.  This is particularly noticeable with smaller chart elements.


## Step-by-Step Code Fix

This solution focuses on setting the `pixelRatio` property of the CanvasJS chart options to match the device's pixel ratio.  This ensures the chart renders at the correct resolution for the screen.

**1. Determine Device Pixel Ratio:**

First, you need to determine the device's pixel ratio.  This can be done using JavaScript's `window.devicePixelRatio` property.

```javascript
const pixelRatio = window.devicePixelRatio || 1; // Default to 1 if not supported
console.log("Device Pixel Ratio:", pixelRatio);
```

**2. Integrate into CanvasJS Chart Options:**

Next, incorporate this pixel ratio into your CanvasJS chart options.

```javascript
var chart = new CanvasJS.Chart("chartContainer", {
    theme: "light2", // Or your preferred theme
    animationEnabled: true,
    title: {
        text: "My Chart"
    },
    data: [
        {
            type: "column", // Or your desired chart type
            dataPoints: [
                { x: 10, y: 71 },
                { x: 20, y: 55 },
                // ... more data points
            ]
        }
    ],
    pixelRatio: pixelRatio // Add this line
});

chart.render();
```

**3. Full Code Example (combining steps 1 & 2):**

```javascript
<!DOCTYPE HTML>
<HTML>
<HEAD>
<script>
window.onload = function () {

    const pixelRatio = window.devicePixelRatio || 1; 

    var chart = new CanvasJS.Chart("chartContainer", {
        theme: "light2",
        animationEnabled: true,
        title:{
            text: "My Chart"
        },
        data: [
        {
            type: "column",
            dataPoints: [
                { x: 10, y: 71 },
                { x: 20, y: 55 },
                { x: 30, y: 50 },
                { x: 40, y: 65 },
                { x: 50, y: 95 },
                { x: 60, y: 68 },
                { x: 70, y: 28 },
                { x: 80, y: 34 },
                { x: 90, y: 10 },
                { x: 100, y: 26 }
            ]
        }
        ],
        pixelRatio: pixelRatio
    });
    chart.render();

}
</script>
</HEAD>
<BODY>
<div id="chartContainer" style="height: 370px; width: 100%;"></div>
<script src="https://cdn.canvasjs.com/canvasjs.min.js"></script>
</BODY>
</HTML>
```

Remember to replace `"https://cdn.canvasjs.com/canvasjs.min.js"` with the correct path to your CanvasJS library.


## Explanation

The `pixelRatio` property tells CanvasJS the scaling factor needed to render the chart at the correct resolution for the device's pixel density.  By setting it to the device's pixel ratio, the chart's internal rendering process will create a higher-resolution canvas, resulting in a sharper and clearer visual output on high-DPI displays.  If omitted, CanvasJS assumes a pixel ratio of 1, which leads to blurry rendering on retina screens.


## External References

* **CanvasJS Documentation:**  [https://canvasjs.com/](https://canvasjs.com/) (Check their documentation for the latest API details and examples)
* **MDN Web Docs on `window.devicePixelRatio`:** [https://developer.mozilla.org/en-US/docs/Web/API/Window/devicePixelRatio](https://developer.mozilla.org/en-US/docs/Web/API/Window/devicePixelRatio)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

