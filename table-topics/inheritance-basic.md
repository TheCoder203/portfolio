---
layout: post
title: Inheritance (Basic)
permalink: /inheritance-basic
---

### Inheritance (Basic)

AstroPlatformer extends the base Coin class to create a specialized FixedPlatformerCoin that behaves the way the level needs. This is a textbook example of inheritance: reuse shared behavior while adding platformer-specific behavior.

```javascript
class FixedPlatformerCoin extends Coin {
  update() {
    if (this.collected) return;
    this.draw();
  }

  collect() { ... }
}
```

In AstroPlatformer, this snippet shows how the topic appears in the actual game code and helps demonstrate the idea with a working example. In AstroPlatformer, the fixed-platformer coin class extends the base coin class and customizes its update and collect behavior for this level.

<div style="display:flex;gap:10px;flex-wrap:wrap;">
  <a href="{{site.baseurl}}/table" style="text-decoration:none;"><div style="background-color:#f59e0b;color:#111;padding:10px 18px;border-radius:8px;font-weight:bold;">Back to Table</div></a>
  <a href="{{site.baseurl}}/astro-platgame-lesson/" style="text-decoration:none;"><div style="background-color:#3b82f6;color:white;padding:10px 18px;border-radius:8px;font-weight:bold;">Open AstroPlatformer Demo</div></a>
</div>
