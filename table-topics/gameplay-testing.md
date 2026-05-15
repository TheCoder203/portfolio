---
layout: post
title: Gameplay Testing
permalink: /gameplay-testing
---

### Gameplay Testing

AstroPlatformer is tested in the code by checking coin collection, player death, and goal logic. That kind of test thinking is what keeps the level from having obvious bugs when it runs in the browser.

```javascript
if (pcx > fx-14*this._scaleX && pcx < fx+30*this._scaleX && pcy > fy && pcy < fy+58*this._scaleY) {
    self._winLevel();
    return;
  }
```

In AstroPlatformer, this snippet shows how the topic appears in the actual game code and helps demonstrate the idea with a working example. In AstroPlatformer, this snippet checks whether the player has reached the goal flag and then triggers the level win sequence, which is a core part of gameplay correctness.

<div style="display:flex;gap:10px;flex-wrap:wrap;">
  <a href="{{site.baseurl}}/table" style="text-decoration:none;"><div style="background-color:#f59e0b;color:#111;padding:10px 18px;border-radius:8px;font-weight:bold;">Back to Table</div></a>
  <a href="{{site.baseurl}}/astro-platgame-lesson/" style="text-decoration:none;"><div style="background-color:#3b82f6;color:white;padding:10px 18px;border-radius:8px;font-weight:bold;">Open AstroPlatformer Demo</div></a>
</div>
