---
layout: post
title: GameEnv Configuration
permalink: /gameenv-configuration
---

### GameEnv Configuration

In cross-platform game development, a **global environment configuration object** (often referred to as `gameEnv`) acts as a single source of truth for the runtime state, rendering boundaries, and asset directories. The game environment config is what tells AstroPlatformer the screen size, level path, and HUD layout.

That setup is important because it makes the game behave correctly across different screens and game containers.

By utilizing a centralized environment object instead of hardcoded numbers, the game engine can achieve responsive canvas scaling, track asset loading states globally, and handle orientation changes dynamically. This architecture is vital for web-based games that might be loaded inside a standard desktop browser, a mobile viewport, or an iframe game container.

---

---
### Why it matters

This concept improves the game's structure and makes the code easier to read and maintain.

### Managing Environment Metrics and Base Aspect Ratios

In AstroPlatformer, this snippet shows how the topic appears in the actual game code and helps demonstrate the idea with a working example. This code reads the game environment dimensions and constructs the level scaling, which helps the platformer adapt to different screen sizes.

---
### Quick Example

```javascript
async function saveProgress(data) {
  const response = await fetch('/api/save', {
    method: 'POST',
    body: JSON.stringify(data)
  });
  return response.json();
}
```

```javascript
// Reading current container metrics from the global game environment
const path       = gameEnv.path;         // Base URL or directory path for asset loading
const width      = gameEnv.innerWidth;   // Active real-time width of the viewport/container
const height     = gameEnv.innerHeight;  // Active real-time height of the viewport/container

// Defining target baseline dimensions used during asset creation (Reference Resolution)
const baseWidth  = 650;
const baseHeight = 400;

/**
 * Calculates responsive scaling factors and aspect ratio adjustments
 * to ensure gameplay elements remain proportional regardless of resolution.
 */
function calculateGameScale(gameEnv, baseWidth, baseHeight) {
  // Determine scale ratios compared to our design baseline
  const scaleX = gameEnv.innerWidth / baseWidth;
  const scaleY = gameEnv.innerHeight / baseHeight;

  // Use the smaller ratio to maintain uniform aspect ratio scaling without distortion
  const uniformScale = Math.min(scaleX, scaleY);

  return {
    scaleX: scaleX,
    scaleY: scaleY,
    uniformScale: uniformScale,
    scaledWidth: baseWidth * uniformScale,
    scaledHeight: baseHeight * uniformScale
  };
}

// Example usage within the environment initialization pipeline
const scaleMetrics = calculateGameScale(gameEnv, baseWidth, baseHeight);
console.log(`[GameEnv Config] Scaling factor calculated: ${scaleMetrics.uniformScale.toFixed(2)}x`);
```

## Summary

Describes the central gameEnv configuration object and how responsive scaling and environment metrics keep the game consistent across viewports.
