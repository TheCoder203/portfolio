---
layout: post
title: Code Comments
permalink: /code-comments
---

### Code Comments

Readable comments explain the platformer flow, collision rules, and why the game updates in a particular order. That type of documentation makes it much easier for a teammate to pick up the level code later.

```javascript
//  5. PLATFORM COLLISION — for every platform (including moving one):
//       TOP: player's bottom swept from above-to-below the platform top
//       ...
//  7. SPIKE DEATH — checked using the player's resolved (post-collision) feet position
```

In AstroPlatformer, this snippet shows how the topic appears in the actual game code and helps demonstrate the idea with a working example. In AstroPlatformer, the comments describe the step-by-step platformer physics and collision flow, so the reader understands why the code executes in that exact order.

<div style="display:flex;gap:10px;flex-wrap:wrap;">
  <a href="{{site.baseurl}}/table" style="text-decoration:none;"><div style="background-color:#f59e0b;color:#111;padding:10px 18px;border-radius:8px;font-weight:bold;">Back to Table</div></a>
  <a href="{{site.baseurl}}/astro-platgame-lesson/" style="text-decoration:none;"><div style="background-color:#3b82f6;color:white;padding:10px 18px;border-radius:8px;font-weight:bold;">Open AstroPlatformer Demo</div></a>
</div>
