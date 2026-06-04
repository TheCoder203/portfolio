---
layout: post
title: API Error Handling
permalink: /api-error-handling
---

# API Error Handling

### Overview
Modern applications constantly communicate with APIs (Application Programming Interfaces).

APIs allow programs to exchange information with external systems such as databases, cloud storage, authentication systems, multiplayer servers, analytics tools, and leaderboards.

In web development and game development, APIs are extremely important because they allow applications to access live and dynamic data.

However, APIs are never guaranteed to work perfectly every time.

Servers may go offline, requests can time out, internet connections can fail, or invalid data may be returned unexpectedly.

Because developers cannot control every external system, applications must be designed to handle these failures safely.

In AstroPlatformer, API error handling helps ensure that gameplay continues smoothly even if online systems fail.

Instead of crashing the game when something goes wrong, the game catches the error and continues operating normally whenever possible.

---

### Why API Error Handling Matters

Without proper error handling, even a small API failure could completely break an application.

Some common API problems include:

- The server is temporarily offline - The user loses internet connection - A request takes too long to respond - Invalid JSON data is returned - Authentication tokens expire - A function does not exist - The API rate limit is exceeded - Browser security policies block the request

Good applications are designed to recover from these problems gracefully.

In game development, this is especially important because players expect games to continue running even when background systems fail.

For example:

- A leaderboard failing should not stop gameplay - A failed save request should not crash the game - Missing online data should fall back to defaults - Network lag should not freeze the application

Error handling improves reliability, stability, and overall user experience.

---

### Basic Promise Error Handling

JavaScript APIs commonly use Promises for asynchronous operations. Promises can either:

- Resolve successfully - Reject with an error

The `.catch()` method is used to safely handle rejected Promises.

```javascript
fetch('/api/player')
  .then(response => response.json())
  .then(data => {
    console.log('Player loaded:', data);
  })
  .catch(error => {
    console.error('Failed to load player data:', error);
  });
```

In this example:

- The application requests player data - If successful, the JSON data is processed - If the request fails, the error is caught safely - The application continues running

Without `.catch()`, the program could throw an unhandled exception.

---

### AstroPlatformer Example

The following snippet comes directly from AstroPlatformer and demonstrates defensive API initialization:

```javascript

if (typeof gameEnv.initScoreManager === 'function') { gameEnv .initScoreManager() .then((sm) => { if (sm && typeof sm.updateScoreDisplay === 'function') { sm.updateScoreDisplay(gameEnv.stats.coinsCollected); } }) .catch((err) => console.warn('AstroPlatformer: initScoreManager failed', err)); }
```

This code demonstrates several important defensive programming techniques.

---

### Function Existence Checking

```javascript
if (typeof gameEnv.initScoreManager === 'function')
```

Before calling the function, the code verifies that it actually exists.

This prevents errors such as:

```javascript
TypeError: gameEnv.initScoreManager is not a function
```

Checking functions before using them is a common defensive programming technique.

---

### Asynchronous Initialization

```javascript

gameEnv.initScoreManager()
```

The score manager initializes asynchronously because it may communicate with external systems such as:

- Online score databases - Cloud save systems - Multiplayer services - Analytics APIs

Asynchronous loading prevents the game from freezing while waiting for the server.

---

### Nested Validation

```javascript
if (sm && typeof sm.updateScoreDisplay === 'function')
```

Even after the Promise succeeds, the returned object is validated again before use.

This protects the game from:

- Null values - Undefined objects - Missing methods - Partial initialization failures

Defensive checks like this improve overall application stability.

---

### Catching Errors Safely

```javascript
.catch((err) => console.warn('AstroPlatformer: initScoreManager failed', err));
```

If anything fails during initialization:

- The error is logged - The game does not crash - Gameplay continues normally

This is one of the most important goals of error handling.

---

### Using `try...catch`

Another common error handling technique uses `try...catch`.

This style is commonly paired with `async/await`.

```javascript

async function loadPlayerData() { try { const response = await fetch('/api/player'); const data = await response.json();

console.log('Loaded player:', data); } catch (error) { console.error('API request failed:', error); } }
```

In this example:

- `try` contains code that may fail - `catch` handles the error safely - The application continues running

Many developers prefer `async/await` because it is easier to read than long Promise chains.

---

### Preventing Game Crashes

Without proper error handling:

```javascript
const data = await fetch('/api/player');
const json = await data.json();

game.start(json);
```

If the API fails, the game may completely stop executing.

With error handling:

```javascript
try {
  const data = await fetch('/api/player');
  const json = await data.json();

  game.start(json);
} catch (error) {
  console.warn('Using offline mode');

  game.start(defaultPlayerData);
}
```

Now the game can recover safely by using fallback data.

---

### Fallback Systems

Professional applications often include fallback systems to improve reliability.

Examples include:

- Offline mode - Cached save files - Default settings - Retry systems - Local storage backups - Alternate servers

Example:

```javascript

async function loadSettings() { try { const response = await fetch('/api/settings'); return await response.json(); } catch { return { volume: 50, difficulty: 'normal', music: true }; } }
```

If the API fails, the application still loads usable default settings.

---

### Retry Logic

Sometimes API failures are temporary. Developers may retry requests automatically before giving up.

```javascript
async function fetchWithRetry(url, retries = 3) {
  for (let i = 0; i < retries; i++) {
    try {
      const response = await fetch(url);

      if (!response.ok) {
        throw new Error('Server error');
      }

      return await response.json();
    } catch (error) {
      console.warn(`Attempt ${i + 1} failed`);
    }
  }

  throw new Error('All retries failed');
}
```

Retry systems improve reliability during short outages or unstable connections.

---

### Handling HTTP Status Codes

APIs often return status codes that describe what happened during the request.

Common status codes include:

| Status Code | Meaning | |---|---| | 200 | Success | | 401 | Unauthorized | | 403 | Forbidden | | 404 | Resource not found | | 500 | Internal server error |

Example:

```javascript
fetch('/api/profile')
  .then(response => {
    if (!response.ok) {
      throw new Error(`HTTP Error: ${response.status}`);
    }

    return response.json();
  })
  .then(data => {
    console.log(data);
  })
  .catch(error => {
    console.error(error);
  });
```

This allows applications to react differently depending on the type of failure.

---

### Logging Errors

Error logging is important for debugging large applications.

```javascript

catch (error) { console.error('Leaderboard failed:', error); }
```

Logging helps developers inspect:

- Stack traces - Failed requests - Invalid responses - Timing issues - Missing data - Network failures

Good logging makes bugs much easier to diagnose and fix.

---

### Defensive Programming

API error handling is part of a broader programming concept called defensive programming.

Defensive programming means writing code that assumes unexpected problems may occur.

Examples include:

- Checking if variables exist - Validating API responses - Preventing null references - Catching exceptions - Verifying object types - Avoiding invalid states

Example:

```javascript
if (player && player.inventory) {
  console.log(player.inventory);
}
```

Instead of assuming the object exists, the code checks safely first.

---

### Why This Matters in AstroPlatformer

AstroPlatformer uses several systems that may depend on external services:

- Score management - Save systems - User profiles - Online leaderboards - Analytics systems - Asset loading

Without proper error handling, any failure in these systems could break gameplay.

By implementing defensive programming and API error handling, AstroPlatformer:

- Continues running smoothly - Prevents fatal crashes - Improves user experience - Supports offline recovery - Makes debugging easier - Creates more professional software

Reliable applications are designed to expect failure and recover safely when problems occur.

---

### Key Takeaways

- APIs can fail unexpectedly - Error handling prevents crashes - `.catch()` handles Promise failures - `try...catch` works with async/await - Defensive programming improves stability - Fallback systems improve reliability - Logging errors helps debugging - Games should continue functioning even when external services fail

Strong API error handling is one of the most important parts of building stable and professional modern applications.

---
### Quick Example

```javascript
fetch('/api/status')
  .then(res => res.json())
  .then(data => console.log(data))
  .catch(err => console.error(err));
```

<div style="display:flex;gap:10px;flex-wrap:wrap;">
  <a href="{{site.baseurl}}/table" style="text-decoration:none;"><div style="background-color:#f59e0b;color:#111;padding:10px 18px;border-radius:8px;font-weight:bold;">Back to Table</div></a>
  <a href="{{site.baseurl}}/astro-platgame-lesson/" style="text-decoration:none;"><div style="background-color:#3b82f6;color:white;padding:10px 18px;border-radius:8px;font-weight:bold;">Open AstroPlatformer Demo</div></a>
  <a href="{{site.baseurl}}/api-error-handling-lesson" style="text-decoration:none;"><div style="background-color:#10b981;color:white;padding:10px 18px;border-radius:8px;font-weight:bold;">Open Lesson Notebook</div></a>
</div>

## Summary

Describes defensive API error handling patterns—try/catch, .catch(), fallbacks, and retries—to keep gameplay running when external services fail.
