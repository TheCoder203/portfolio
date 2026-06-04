---
layout: post
title: Console Debugging
permalink: /console-debugging
---

# Console Debugging

### Overview
Console debugging is one of the simplest and most powerful ways to understand what is happening inside a program while it runs.

Developers use the browser console to print messages, warnings, and errors so they can inspect program behavior in real time.

In game development, especially in browser-based games like AstroPlatformer, debugging is essential because many systems run simultaneously (physics, rendering, input, APIs, and UI updates).

When something breaks, the console helps reveal what went wrong without stopping the entire game.

---

### What is the Console?

The console is a built-in developer tool in web browsers that allows you to:

- Print messages (`console.log`) - Display warnings (`console.warn`) - Show errors (`console.error`) - Inspect objects - Track program flow

You can open it in most browsers using:

- Right click → Inspect → Console - Or pressing `F12`

---

### Why Debugging Matters

Programs often fail in unpredictable ways due to:

- Missing data - Network issues - Incorrect logic - Undefined variables - Failed API calls - Timing issues in async code

Without debugging tools, it would be extremely difficult to figure out what is happening inside the program.

Console debugging helps developers:

- Identify errors quickly - Understand program flow - Track down bugs - Monitor API responses - Verify system behavior

---

### Basic Console Logging

The simplest debugging tool is `console.log()`.

Example:

```javascript
console.log('Game started');
```

This prints a message to the console when the program runs.

Example with variables:

```javascript

const score = 100; console.log('Score:', score);
```

This helps verify that values are correct.

---

### Console Warnings

Warnings indicate something went wrong, but the program can still continue running.

Example:

```javascript
console.warn('Low memory detected');
```

Warnings are often used for:

- Non-critical failures - Missing optional features - Fallback behavior - API issues that don’t crash the game

---

### Console Errors

Errors indicate serious problems.

Example:

```javascript
console.error('Failed to load game assets');
```

Errors are used when:

- A system fails completely - A required resource is missing - A critical function breaks - The program cannot continue safely

---

### AstroPlatformer Example

The following code comes directly from AstroPlatformer:

```javascript

.catch((err) => console.warn('AstroPlatformer: initScoreManager failed', err));
```

This line is part of an asynchronous operation using Promises.

If the score manager fails to initialize, the error is caught and logged in the console.

---

### Breaking Down the Code

```javascript
.catch((err) => ...)
```

This runs if an error occurs during an asynchronous operation.

Instead of crashing the game, the error is safely captured.

---

### Logging the Error

```javascript
console.warn('AstroPlatformer: initScoreManager failed', err);
```

This prints a warning message along with the actual error object.

The message includes:

- A clear label (`AstroPlatformer`) - The system that failed (`initScoreManager`) - The error details (`err`)

This makes debugging much easier.

---

### Why This Is Important

Without this kind of logging:

- The game might fail silently - Developers wouldn’t know what broke - Bugs would be harder to reproduce - Players might experience invisible issues

With console debugging:

- Errors become visible - Problems can be traced - Fixes are faster to implement - Systems become more reliable

---

### Debugging Asynchronous Code

Asynchronous systems are harder to debug because they run in the background.

Example:

```javascript

gameEnv.initScoreManager() .then((sm) => { console.log('Score manager loaded:', sm); }) .catch((err) => { console.warn('Failed to initialize score manager', err); });
```

This helps track both success and failure cases.

---

### Tracking Game State

Developers often log game state to understand behavior.

Example:

```javascript
console.log('Player position:', player.x, player.y);
```

This helps verify movement and physics updates.

---

### Debugging Collisions

Collision systems are often debugged using logs:

```javascript
if (collisionDetected) {
  console.log('Collision detected at:', player.x, player.y);
}
```

This helps determine:

- Where collisions occur - Why they happen - Whether logic is correct

---

### Debugging Loops

Loops can also be inspected:

```javascript

for (let i = 0; i < platforms.length; i++) { console.log('Platform:', platforms[i]); }
```

This ensures data is structured correctly.

---

### Debugging Conditional Logic

Conditionals can be traced using logs:

```javascript
if (playerAlive) {
  console.log('Player is alive');
}
```

This confirms which branch is executing.

---

### Performance Debugging

Console logs can also help measure performance:

```javascript
console.time('updateLoop');

// game update logic

console.timeEnd('updateLoop');
```

This shows how long a function takes to run.

---

### Common Debugging Patterns

Developers often use patterns like:

- Logging inputs - Logging outputs - Logging errors - Logging state changes - Logging execution flow

These patterns help isolate problems quickly.

---

### Debugging Game Engines

Game engines like AstroPlatformer involve many systems running together:

- Physics updates - Rendering loops - Input handling - Collision detection - UI updates - API communication

Console debugging helps track how these systems interact.

---

### Example Debugging Workflow

A typical debugging process might look like:

1. Add console logs 2.

Reproduce the bug 3. Inspect console output 4.

Identify incorrect behavior 5. Fix the code 6.

Remove or reduce logs

This iterative process is common in development.

---

### Best Practices for Console Debugging

Good debugging habits include:

- Using clear messages - Including context in logs - Avoiding excessive logging - Using warnings for non-critical issues - Removing logs before production (when needed)

Example of good logging:

```javascript

console.warn('[Leaderboard] Failed to load scores', error);
```

---

### Real-World Uses of Console Debugging

Console debugging is used in:

| System | Purpose | |---|---| | Games | Track gameplay bugs | | Websites | Debug UI issues | | APIs | Monitor requests | | Mobile Apps | Track crashes | | Backend Servers | Monitor errors | | AI Systems | Inspect model behavior |

It is one of the most universal debugging tools.

---

### Why Console Debugging Matters in AstroPlatformer

AstroPlatformer uses console debugging to:

- Track score manager initialization - Detect API failures - Monitor game state - Debug physics and collisions - Identify rendering issues

The logging system ensures that:

- Failures don’t crash the game - Errors are visible to developers - Problems can be fixed efficiently - The game remains stable for players

---

### Key Takeaways

- The console is used for debugging in browsers - `console.log`, `console.warn`, and `console.error` show different message types - Debugging helps developers understand program behavior - Console logs are essential for asynchronous systems - AstroPlatformer logs score manager failures safely - Debugging improves stability and development speed - Logs help track game state and errors

Console debugging is one of the most important tools in programming and is essential for building reliable games and applications.

---

### How to Use Console Debugging

**Steps:**

1. **Open DevTools:** Press `F12` or right-click the game and select `Inspect`.

2. **Open the Console Tab:** Click the `Console` tab at the top of DevTools.

3. **Run Console Commands:** In the console input area at the bottom, type and execute JavaScript commands:
   ```javascript
   console.log('Check this value:', myVariable);
   ```

4. **View Output:** The console displays all logs, warnings, and errors in real-time as the game runs.

5. **Add Logs to Your Code:** Insert console statements directly into your game code:
   ```javascript
   function updatePlayer(player) {
     console.log('Player position:', player.x, player.y);
     player.x += player.speed;
   }
   ```

6. **Filter Output:** Use the filter box to search for specific log messages or errors.

7. **Use Different Log Levels:**
   - `console.log()` — Standard information
   - `console.warn()` — Non-critical warnings
   - `console.error()` — Critical errors

**Example Workflow:**
- Add a log before and after a critical operation
- Reproduce the bug in the game
- Check the console output to see where the problem occurs
- Remove or reduce logs once the issue is fixed

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

--- ### Quick Example

```javascript
console.log('Player position:', player.x, player.y);
```


## Summary

Describes using the browser console for logging, warnings, and errors to trace program flow, inspect state, and debug asynchronous behavior.
