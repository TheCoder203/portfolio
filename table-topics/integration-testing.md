---
layout: post
title: Integration Testing
permalink: /integration-testing
---

### Integration Testing

Integration-style checks in AstroPlatformer make sure the score display only updates when the supporting service is available. That means the level can still load even if one piece of the system is absent.

```javascript
if (gameEnv.scoreManager?.updateScoreDisplay) {
    gameEnv.scoreManager.updateScoreDisplay(totalCoins);
  }
```

In AstroPlatformer, this snippet shows how the topic appears in the actual game code and helps demonstrate the idea with a working example. In AstroPlatformer, this snippet checks for the score manager before updating it, which is an integration-style guard that keeps the game functioning when not all services are present.

<div style="display:flex;gap:10px;flex-wrap:wrap;">
  <a href="{{site.baseurl}}/table" style="text-decoration:none;"><div style="background-color:#f59e0b;color:#111;padding:10px 18px;border-radius:8px;font-weight:bold;">Back to Table</div></a>
  <a href="{{site.baseurl}}/astro-platgame-lesson/" style="text-decoration:none;"><div style="background-color:#3b82f6;color:white;padding:10px 18px;border-radius:8px;font-weight:bold;">Open AstroPlatformer Demo</div></a>
  <a href="{{site.baseurl}}/allhw" style="text-decoration:none;"><div style="background-color:#10b981;color:white;padding:10px 18px;border-radius:8px;font-weight:bold;">Open AllHW Notebook</div></a>
</div>
