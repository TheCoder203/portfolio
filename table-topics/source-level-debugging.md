---
layout: post
title: Source-Level Debugging
permalink: /source-level-debugging
---

# Source-Level Debugging

### Overview
Source-level debugging is the process of examining and controlling code execution line-by-line while a program is running.

Instead of only looking at console output, source-level debugging allows developers to:

- Pause execution - Inspect variables - Step through functions - Watch program flow - Analyze logic in real time - Identify bugs more precisely

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

### How to Use Source-Level Debugging

**Steps:**

1. **Open DevTools:** Press `F12` or right-click the game and select `Inspect`.

2. **Navigate to Sources Tab:** Click the `Sources` tab at the top of DevTools.

3. **Find Your File:** In the left panel, expand the file structure and locate the JavaScript file you want to debug.

4. **Set a Breakpoint:** Click on a line number in the code editor. A blue dot appears, indicating the breakpoint.

5. **Trigger the Code:** Interact with the game to cause the breakpointed code to execute. The debugger pauses execution at that line.

6. **Inspect Variables:** When paused, hover over variables or check the right panel to see their current values.

7. **Step Through Code:**
   - **Step Over (F10):** Execute the current line and move to the next
   - **Step Into (F11):** Enter a function to inspect its internal logic
   - **Step Out (Shift+F11):** Exit the current function and return to the caller

8. **Resume Execution:** Press the play button or press `F8` to continue running the game.

9. **Watch Expressions:** Right-click on a variable and select `Watch` to monitor it throughout execution.

10. **Use the Debugger Statement:** Place `debugger;` in your code to automatically pause when that line executes:
    ```javascript
    function updatePlayer(player) {
      debugger;  // Execution pauses here when the debugger is open
      player.x += player.speed;
    }
    ```

**Example Workflow:**
- Set a breakpoint in the collision detection function
- Run the game until a collision occurs
- Inspect the player position and platform coordinates
- Step through the logic to understand why the collision did or didn't trigger

---

### Toggling Hitbox Display Using Browser Inspect

You can toggle hitbox visibility directly in the browser DevTools without restarting the game.

**Steps:**

1. **Open DevTools:** Press `F12` or right-click the game and select `Inspect`.

2. **Open the Console:** Click the `Console` tab at the top of DevTools.

3. **Enable Debug Mode:** Run this command to activate hitbox visualization:
   ```javascript
   gameEnv.debugModeActive = true;
   ```

4. **Disable Debug Mode:** To hide hitboxes, run:
   ```javascript
   gameEnv.debugModeActive = false;
   ```

5. **Alternative: Toggle CSS Directly:** If hitboxes are already rendered, you can also find them in the Elements panel:
   - Click the Element Inspector (top-left arrow icon in DevTools)
   - Click on a visible hitbox outline in the game
   - In the Styles panel, toggle the `display` property or the `border` style to show/hide

**Example:** If you see a `.hitbox` element with `display: none`, change it to `display: block` to show it immediately.

This approach is invaluable for testing collision detection, verifying that coins are placed correctly, and confirming that platforms align with their visual representations.

---
### Quick Example

```javascript
console.log('Player position:', player.x, player.y);
```

<div style="display:flex;gap:10px;flex-wrap:wrap;"> <a href="{{site.baseurl}}/table" style="text-decoration:none;"><div style="background-color:#f59e0b;color:#111;padding:10px 18px;border-radius:8px;font-weight:bold;">Back to Table</div></a> <a href="{{site.baseurl}}/astro-platgame-lesson/" style="text-decoration:none;"><div style="background-color:#3b82f6;color:white;padding:10px 18px;border-radius:8px;font-weight:bold;">Open AstroPlatformer Demo</div></a> <a href="{{site.baseurl}}/source-level-debugging-lesson" style="text-decoration:none;"><div style="background-color:#10b981;color:white;padding:10px 18px;border-radius:8px;font-weight:bold;">Open Lesson Notebook</div></a> </div>

## Summary

Explains using breakpoints and stepping through code in DevTools to inspect execution, variables, and timing for precise debugging.
