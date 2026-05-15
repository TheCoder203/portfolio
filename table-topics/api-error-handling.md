---
layout: post
title: API Error Handling
permalink: /api-error-handling
---

### API Error Handling

When your code talks to an API, things can fail in ways you don't control: a server can time out, a request can return bad data, or the browser might lose connection. In AstroPlatformer, that means the game needs to keep playing instead of crashing, so users still get a smooth experience.

```javascript
if (typeof gameEnv.initScoreManager === 'function') {
    gameEnv
      .initScoreManager()
      .then((sm) => {
        if (sm && typeof sm.updateScoreDisplay === 'function') {
          sm.updateScoreDisplay(gameEnv.stats.coinsCollected);
        }
      })
      .catch((err) => console.warn('AstroPlatformer: initScoreManager failed', err));
  }
```

In AstroPlatformer, this snippet shows how the topic appears in the actual game code and helps demonstrate the idea with a working example. In AstroPlatformer, this snippet checks whether the score manager initialized successfully before using it, and catches any errors so the game can keep running even when external services fail.

<div style="display:flex;gap:10px;flex-wrap:wrap;">
  <a href="{{site.baseurl}}/table" style="text-decoration:none;"><div style="background-color:#f59e0b;color:#111;padding:10px 18px;border-radius:8px;font-weight:bold;">Back to Table</div></a>
  <a href="{{site.baseurl}}/astro-platgame-lesson/" style="text-decoration:none;"><div style="background-color:#3b82f6;color:white;padding:10px 18px;border-radius:8px;font-weight:bold;">Open AstroPlatformer Demo</div></a>
  <a href="{{site.baseurl}}/api-error-handling-lesson" style="text-decoration:none;"><div style="background-color:#10b981;color:white;padding:10px 18px;border-radius:8px;font-weight:bold;">Open Lesson Notebook</div></a>
</div>
