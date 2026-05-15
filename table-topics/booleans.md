---
layout: post
title: Booleans
permalink: /booleans
---

### Booleans

True/false values are everywhere in the platformer: whether a coin has been collected, whether the player is on the ground, or whether the game is over. That binary logic keeps the update loop clean and predictable.

```javascript
if (this.collected) return;
if (!this.collected) {
    this.collected = true;
    ...
  }
```

In AstroPlatformer, this snippet shows how the topic appears in the actual game code and helps demonstrate the idea with a working example. In AstroPlatformer, this snippet uses boolean values to avoid processing a coin more than once, which keeps the coin collection logic stable and predictable.

<div style="display:flex;gap:10px;flex-wrap:wrap;">
  <a href="{{site.baseurl}}/table" style="text-decoration:none;"><div style="background-color:#f59e0b;color:#111;padding:10px 18px;border-radius:8px;font-weight:bold;">Back to Table</div></a>
  <a href="{{site.baseurl}}/astro-platgame-lesson/" style="text-decoration:none;"><div style="background-color:#3b82f6;color:white;padding:10px 18px;border-radius:8px;font-weight:bold;">Open AstroPlatformer Demo</div></a>
  <a href="{{site.baseurl}}/booleans-lesson" style="text-decoration:none;"><div style="background-color:#10b981;color:white;padding:10px 18px;border-radius:8px;font-weight:bold;">Open Lesson Notebook</div></a>
</div>
