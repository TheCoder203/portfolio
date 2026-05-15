---
layout: post
title: Conditionals
permalink: /conditionals
---

### Conditionals

Conditionals let the game choose different behaviors depending on the current state, such as whether the player is alive, whether the score manager is available, or whether a platform is moving. That branching is how the code becomes responsive to what happens in the game.

```javascript
if (this.collected) return;
if (this.canvas) {
    this.canvas.style.opacity = '0';
    this.canvas.style.transition = 'opacity 0.3s';
    setTimeout(() => this.canvas?.remove(), 350);
  }
```

In AstroPlatformer, this snippet shows how the topic appears in the actual game code and helps demonstrate the idea with a working example. In AstroPlatformer, these conditionals decide whether a collected coin should fade out and be removed, which controls how the game responds to player actions.

<div style="display:flex;gap:10px;flex-wrap:wrap;">
  <a href="{{site.baseurl}}/table" style="text-decoration:none;"><div style="background-color:#f59e0b;color:#111;padding:10px 18px;border-radius:8px;font-weight:bold;">Back to Table</div></a>
  <a href="{{site.baseurl}}/astro-platgame-lesson/" style="text-decoration:none;"><div style="background-color:#3b82f6;color:white;padding:10px 18px;border-radius:8px;font-weight:bold;">Open AstroPlatformer Demo</div></a>
</div>
