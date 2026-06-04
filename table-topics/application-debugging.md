---
layout: post
title: Application Debugging
permalink: /application-debugging
---

# Application Debugging

### Overview
Application debugging focuses on inspecting stored browser data and application state.

Modern web applications store information such as: - Cookies - localStorage - sessionStorage - Authentication tokens - User settings - Cached data

Developers inspect this information using the DevTools Application tab.

---

### Why Application Debugging Matters

Applications rely heavily on stored state.

Problems can occur when: - Tokens expire - Incorrect data is stored - Cache becomes corrupted - Sessions fail - User data becomes inconsistent

Application debugging helps developers inspect and manage this data safely.

---

---
### Why it matters

Clear debugging and documentation habits make the game easier to maintain and fix when issues arise.

### localStorage Example

Example:

```javascript id="appdbg1"
localStorage.setItem('highScore', 1200);

const score = localStorage.getItem('highScore');

console.log(score);
```

---

### How to Inspect Application Storage

**Steps:**

1. **Open DevTools:** Press `F12` or right-click the game and select `Inspect`.

2. **Navigate to Application Tab:** Click the `Application` tab at the top of DevTools (may be labeled `Storage` on some browsers).

3. **View localStorage:**
   - In the left sidebar, expand `Storage` and click `Local Storage`
   - Select the game's domain from the list
   - All saved key-value pairs are displayed in a table

4. **View sessionStorage:**
   - Click `Session Storage` in the left sidebar
   - Select the game's domain
   - Shows data stored temporarily for the current browser session

5. **View Cookies:**
   - Click `Cookies` in the left sidebar
   - Select the game's domain
   - See all cookies including authentication tokens and preferences

6. **Inspect Stored Data:**
   - Click on any key to see its full value
   - Check the expiration date for cookies
   - Verify that authentication tokens are present and not expired

7. **Modify Storage (Testing):** Double-click a value to edit it temporarily (useful for testing):
   ```
   Key: highScore
   Value: 5000
   ```

8. **Clear Storage:** Right-click an entry and select `Delete` or clear all data for the domain.

9. **Add New Data:** Click the empty row at the bottom to manually add test data:
   - Key: `testLevel`
   - Value: `3`

10. **Check for Corruption:** If the game fails to load save data:
    - Open Application > Local Storage
    - Look for the expected keys (e.g., `coinsCollected`, `levelProgress`)
    - If missing, the game hasn't saved properly
    - If present but corrupted (not valid JSON), you've found the problem

**Example Workflow:**
- Play and collect coins in the game
- Open Application > Local Storage
- Verify that `coinsCollected` has been updated
- Close the browser and reopen the game
- Check if `coinsCollected` persisted correctly
- If it didn't, there's a storage bug to fix

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

<div style="display:flex;gap:10px;flex-wrap:wrap;"> <a href="{{site.baseurl}}/table" style="text-decoration:none;"><div style="background-color:#f59e0b;color:#111;padding:10px 18px;border-radius:8px;font-weight:bold;">Back to Table</div></a> <a href="{{site.baseurl}}/astro-platgame-lesson/" style="text-decoration:none;"><div style="background-color:#3b82f6;color:white;padding:10px 18px;border-radius:8px;font-weight:bold;">Open AstroPlatformer Demo</div></a> <a href="{{site.baseurl}}/application-debugging-lesson" style="text-decoration:none;"><div style="background-color:#10b981;color:white;padding:10px 18px;border-radius:8px;font-weight:bold;">Open Lesson Notebook</div></a> </div>

## Summary

Describes inspecting browser storage and persisted state (localStorage, cookies) to diagnose issues with saved game data and session state.
