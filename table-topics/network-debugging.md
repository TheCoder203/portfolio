---
layout: post
title: Network Debugging
permalink: /network-debugging
---

# Network Debugging

### Overview
Network debugging is the process of inspecting and analyzing communication between an application and external resources such as APIs, servers, databases, and web services.

Modern applications constantly exchange data through HTTP requests.

Examples include: - Fetch requests - API calls - Image loading - Authentication systems - Game data synchronization

The browser DevTools Network tab allows developers to inspect all of these operations in real time.

---

### Why Network Debugging Matters

Without network debugging, developers would struggle to understand: - Why API requests fail - Why data is missing - Why images do not load - Why CORS errors occur - Why responses are delayed

Network debugging helps developers inspect: - Request URLs - Response status codes - Headers - Response data - Request timing

---

---
### Why it matters

This concept is essential for connecting the game to external data and keeping persistent state reliable.

### HTTP Requests in JavaScript

JavaScript applications commonly use `fetch()`.

Example:

```javascript id="netdbg1"
fetch('/api/player')
  .then(response => response.json())
  .then(data => {
    console.log(data);
  });
```

---

### How to Use Network Debugging

**Steps:**

1. **Open DevTools:** Press `F12` or right-click the game and select `Inspect`.

2. **Navigate to Network Tab:** Click the `Network` tab at the top of DevTools.

3. **Enable Recording:** Make sure the red circle (record button) is active in the top-left of the Network panel.

4. **Perform Network Operations:** Trigger API calls in the game by:
   - Loading level data
   - Submitting scores
   - Fetching leaderboards
   - Authenticating with a server

5. **Inspect Requests:** All web requests appear listed in the Network panel. Click on a request to see details:
   - **Headers:** Request and response headers, including authentication tokens
   - **Payload:** Data sent in POST requests
   - **Response:** The JSON or text data returned by the server
   - **Timing:** How long each phase of the request took

6. **Check Status Codes:**
   - `200` — Success
   - `404` — Resource not found
   - `500` — Server error
   - `403` — Forbidden (authentication issues)
   - `CORS error` — Cross-origin request blocked

7. **Filter Requests:** Use the filter box to show only:
   - XHR (API calls)
   - Fetch API calls
   - Failed requests

8. **Preview Response Data:** Click the `Response` tab to see the actual data returned by the API.

9. **Check Request Timing:** The `Timing` tab shows:
   - How long DNS lookup took
   - Connection time
   - Request/response time
   - Total request duration

**Example Workflow:**
- Open the Network tab before triggering a score submission
- Submit a score in the game
- Look for the POST request to `/api/submit-score`
- Check the Status (should be 200 if successful)
- Preview the Response to see the server's confirmation
- If it failed, check the status code and error message

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
fetch('/api/status')
  .then(res => res.json())
  .then(data => console.log(data))
  .catch(err => console.error(err));
```

<div style="display:flex;gap:10px;flex-wrap:wrap;"> <a href="{{site.baseurl}}/table" style="text-decoration:none;"><div style="background-color:#f59e0b;color:#111;padding:10px 18px;border-radius:8px;font-weight:bold;">Back to Table</div></a> <a href="{{site.baseurl}}/astro-platgame-lesson/" style="text-decoration:none;"><div style="background-color:#3b82f6;color:white;padding:10px 18px;border-radius:8px;font-weight:bold;">Open AstroPlatformer Demo</div></a> <a href="{{site.baseurl}}/network-debugging-lesson" style="text-decoration:none;"><div style="background-color:#10b981;color:white;padding:10px 18px;border-radius:8px;font-weight:bold;">Open Lesson Notebook</div></a> </div>

## Summary

Shows how to inspect HTTP requests and responses using browser DevTools Network tab to diagnose API problems, CORS issues, and timing problems.
