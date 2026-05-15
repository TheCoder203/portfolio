---
layout: post
title: Asynchronous I/O
permalink: /asynchronous-io
---

### Asynchronous I/O

AstroPlatformer shows asynchronous behavior in the way it initializes the score manager and updates the screen later, without freezing the page. That same promise-based flow is how modern apps keep responding while waiting for async work to finish.

```javascript
gameEnv
      .initScoreManager()
      .then((sm) => {
        if (sm && typeof sm.updateScoreDisplay === 'function') {
          sm.updateScoreDisplay(gameEnv.stats.coinsCollected);
        }
      })
      .catch((err) => console.warn('AstroPlatformer: initScoreManager failed', err));
```

In AstroPlatformer, this snippet shows how the topic appears in the actual game code and helps demonstrate the idea with a working example. In AstroPlatformer, this snippet shows async setup by waiting for the score manager promise to resolve and then updating the display without blocking the rest of the game.

<div style="display:flex;gap:10px;flex-wrap:wrap;">
  <a href="{{site.baseurl}}/table" style="text-decoration:none;"><div style="background-color:#f59e0b;color:#111;padding:10px 18px;border-radius:8px;font-weight:bold;">Back to Table</div></a>
  <a href="{{site.baseurl}}/astro-platgame-lesson/" style="text-decoration:none;"><div style="background-color:#3b82f6;color:white;padding:10px 18px;border-radius:8px;font-weight:bold;">Open AstroPlatformer Demo</div></a>
  <a href="{{site.baseurl}}/asynchronous-io-lesson" style="text-decoration:none;"><div style="background-color:#10b981;color:white;padding:10px 18px;border-radius:8px;font-weight:bold;">Open Lesson Notebook</div></a>
</div>
