---
layout: post
title: Numbers
permalink: /numbers
---

### Numbers

In computer programming, **numbers** are a primary data type used to represent quantitative values, track states, and drive algorithmic calculations. Numbers are what define the platformer level dimensions, object positions, and movement thresholds. Everything from the flag location to the coin size is controlled with numeric values.

Within a game engine, numbers are categorized generally into integers (whole numbers) and floating-point numbers (decimals). These data primitives act as the bedrock of the entire simulation. Without them, an engine cannot track passing frames, measure velocities, increment player scores, or map coordinates onto a two-dimensional visual grid.

---

### Defining Screen Geometry with Numeric Constants

In AstroPlatformer, this snippet shows how the topic appears in the actual game code and helps demonstrate the idea with a working example. This structural definition block uses precise numbers to calculate proportional screen scaling values across different displays:

```javascript
/**
 * Quantifies game viewport measurements to establish an internal physics coordinate system.
 * Demonstrates the application of integer constants and floating-point evaluation.
 *
 * @param {number} width - The active, real-time horizontal boundary of the browser window.
 * @param {number} height - The active, real-time vertical boundary of the browser window.
 */
function configureViewportMetrics(width, height) {
  // 1. Establish reference dimensions as immutable integer values
  const baseWidth  = 650; // Reference width in pixels
  const baseHeight = 400; // Reference height in pixels

  // 2. Perform division to output floating-point ratio multipliers
  const scaleX = width / baseWidth;
  const scaleY = height / baseHeight;

  // 3. Store the numeric results inside an environmental state block
  this.engineMetrics = {
    canvasWidth: width,
    canvasHeight: height,
    horizontalScale: scaleX,
    verticalScale: scaleY
  };

  console.log(`[Numbers Engine] Calculated floating-point scale: X=${scaleX.toFixed(4)}, Y=${scaleY.toFixed(4)}`);
}
```
In AstroPlatformer, this snippet shows how the topic appears in the actual game code and helps demonstrate the idea with a working example. In AstroPlatformer, these numeric constants define the level dimensions and scale factors, which are the foundation for positioning and sizing every object in the game. 

By setting baseWidth to exactly 650 and baseHeight to exactly 400, the engine establishes a reliable mathematical baseline for the virtual world. When the code divides the active screen width and height by these base constants, it generates precise decimal scale values like 1.5 or 0.85. These floating-point numbers then act as multipliers across the rest of the script, instantly shrinking or stretching speed variables, jump gravity, and interaction boundaries to match the target device. Relying on numbers to drive layout constraints prevents the game assets from bunching up or breaking apart when loaded inside a mobile app or a desktop browser window. This mathematical consistency forms the framework for reliable collision rules, ensuring that a jump distance calculated in your logic remains consistent for every user.