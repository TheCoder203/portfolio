---
layout: post
title: Nested Conditions
permalink: /nested-conditions
---

### Nested Conditions

The game checks multiple conditions before acting, such as whether the player is touching the flag and whether the score manager exists. Those nested checks prevent invalid operations and keep the game stable.

```javascript
if (gameEnv.scoreManager?.updateScoreDisplay) {
    gameEnv.scoreManager.updateScoreDisplay(totalCoins);
  }
  if (pcx > fx-14*this._scaleX && pcx < fx+30*this._scaleX && pcy > fy && pcy < fy+58*this._scaleY) {
    self._winLevel();
  }
```

In AstroPlatformer, this snippet shows how the topic appears in the actual game code and helps demonstrate the idea with a working example. In AstroPlatformer, these nested checks first verify the score manager exists and then test whether the player reached the goal, which prevents invalid operations and handles game logic safely.

<div style="display:flex;gap:10px;flex-wrap:wrap;">
  <a href="{{site.baseurl}}/table" style="text-decoration:none;"><div style="background-color:#f59e0b;color:#111;padding:10px 18px;border-radius:8px;font-weight:bold;">Back to Table</div></a>
  <a href="{{site.baseurl}}/astro-platgame-lesson/" style="text-decoration:none;"><div style="background-color:#3b82f6;color:white;padding:10px 18px;border-radius:8px;font-weight:bold;">Open AstroPlatformer Demo</div></a>
  <a href="{{site.baseurl}}/allhw" style="text-decoration:none;"><div style="background-color:#10b981;color:white;padding:10px 18px;border-radius:8px;font-weight:bold;">Open AllHW Notebook</div></a>
</div>
