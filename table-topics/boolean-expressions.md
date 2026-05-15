---
layout: post
title: Boolean Expressions
permalink: /boolean-expressions
---

### Boolean Expressions

Boolean expressions are how the game decides whether a feature is available or a condition is met. In AstroPlatformer, checks like whether the score manager exists determine whether the game updates the HUD or skips that step.

```javascript
if (sm && typeof sm.updateScoreDisplay === 'function') {
    sm.updateScoreDisplay(gameEnv.stats.coinsCollected);
  }
```

In AstroPlatformer, this snippet shows how the topic appears in the actual game code and helps demonstrate the idea with a working example. In AstroPlatformer, this boolean check confirms the score manager exists before calling its update method, which prevents runtime errors when some systems are not available.

<div style="display:flex;gap:10px;flex-wrap:wrap;">
  <a href="{{site.baseurl}}/table" style="text-decoration:none;"><div style="background-color:#f59e0b;color:#111;padding:10px 18px;border-radius:8px;font-weight:bold;">Back to Table</div></a>
  <a href="{{site.baseurl}}/astro-platgame-lesson/" style="text-decoration:none;"><div style="background-color:#3b82f6;color:white;padding:10px 18px;border-radius:8px;font-weight:bold;">Open AstroPlatformer Demo</div></a>
  <a href="{{site.baseurl}}/allhw" style="text-decoration:none;"><div style="background-color:#10b981;color:white;padding:10px 18px;border-radius:8px;font-weight:bold;">Open AllHW Notebook</div></a>
</div>
