---
layout: post
title: API Integration
permalink: /api-integration
---

### API Integration

AstroPlatformer uses external systems like the leaderboard and score manager, so it needs to integrate with APIs or other game services cleanly. That means wiring the game data into real-world services while still handling the result gracefully.

```javascript
this._leaderboard = window.leaderboardInstance || new Leaderboard(gameEnv.gameControl, {
    gameName: 'astronaut-platformer-game',
    initiallyHidden: false
  });
```

In AstroPlatformer, this snippet shows how the topic appears in the actual game code and helps demonstrate the idea with a working example. In AstroPlatformer, this snippet creates or reuses the leaderboard object and connects it to the game control, which is how the game sends scored data to the leaderboard system.

<div style="display:flex;gap:10px;flex-wrap:wrap;">
  <a href="{{site.baseurl}}/table" style="text-decoration:none;"><div style="background-color:#f59e0b;color:#111;padding:10px 18px;border-radius:8px;font-weight:bold;">Back to Table</div></a>
  <a href="{{site.baseurl}}/astro-platgame-lesson/" style="text-decoration:none;"><div style="background-color:#3b82f6;color:white;padding:10px 18px;border-radius:8px;font-weight:bold;">Open AstroPlatformer Demo</div></a>
  <a href="{{site.baseurl}}/allhw" style="text-decoration:none;"><div style="background-color:#10b981;color:white;padding:10px 18px;border-radius:8px;font-weight:bold;">Open AllHW Notebook</div></a>
</div>
