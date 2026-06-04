---
layout: post
title: Source-Level Debugging
permalink: /source-level-debugging
---

# Source-Level Debugging

Source-level debugging is the process of examining and controlling code execution line-by-line while a program is running.

Instead of only looking at console output, source-level debugging allows developers to:

- Pause execution
- Inspect variables
- Step through functions
- Watch program flow
- Analyze logic in real time
- Identify bugs more precisely

In JavaScript development, source-level debugging is commonly done using the browser DevTools Sources tab.

Games like AstroPlatformer rely heavily on debugging tools because many systems interact simultaneously: - Physics - Rendering - Player movement - Collision systems - API calls - Animation timing

Source-level debugging helps developers understand exactly what the game is doing internally.

---

### Why Source-Level Debugging Matters

Without debugging tools, developers would have to guess where problems are occurring.

Source-level debugging allows you to: - Pause execution at critical moments - Examine object state - Detect incorrect values - Follow execution flow step-by-step - Understand timing-related issues

This is extremely important in game engines because bugs often occur during real-time interactions.

---

---
### Why it matters

Clear debugging and documentation habits make the game easier to maintain and fix when issues arise.

### What Is a Breakpoint?

A breakpoint tells the browser to pause code execution at a specific line.

Once paused, developers can inspect: - Variables - Function calls - Object properties - Game state - Stack traces

Example:

```javascript id="sdbg1"
function updatePlayer(player) {
  player.x += player.speed;
  player.y += player.velocityY;

  debugger;

  applyGravity(player);
}
```
---
### Quick Example

```javascript
console.log('Player position:', player.x, player.y);
```

<div style="display:flex;gap:10px;flex-wrap:wrap;"> <a href="{{site.baseurl}}/table" style="text-decoration:none;"><div style="background-color:#f59e0b;color:#111;padding:10px 18px;border-radius:8px;font-weight:bold;">Back to Table</div></a> <a href="{{site.baseurl}}/astro-platgame-lesson/" style="text-decoration:none;"><div style="background-color:#3b82f6;color:white;padding:10px 18px;border-radius:8px;font-weight:bold;">Open AstroPlatformer Demo</div></a> <a href="{{site.baseurl}}/source-level-debugging-lesson" style="text-decoration:none;"><div style="background-color:#10b981;color:white;padding:10px 18px;border-radius:8px;font-weight:bold;">Open Lesson Notebook</div></a> </div>

## Summary

Explains using breakpoints and stepping through code in DevTools to inspect execution, variables, and timing for precise debugging.
