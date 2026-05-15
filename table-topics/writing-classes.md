---
layout: post
title: Writing Classes
permalink: /writing-classes
---

### Writing Classes

AstroPlatformer organizes behavior into classes for the level and the special coin objects. That object-oriented structure keeps platformer logic grouped together and easier to extend.

```javascript
class AstroPlatformer {
  constructor(gameEnv) { ... }
}

class FixedPlatformerCoin extends Coin { ... }
```

In AstroPlatformer, this snippet shows how the topic appears in the actual game code and helps demonstrate the idea with a working example. In AstroPlatformer, these class definitions organize the game into reusable objects and give each behavior a clear place in the level code.

<div style="display:flex;gap:10px;flex-wrap:wrap;">
  <a href="{{site.baseurl}}/table" style="text-decoration:none;"><div style="background-color:#f59e0b;color:#111;padding:10px 18px;border-radius:8px;font-weight:bold;">Back to Table</div></a>
  <a href="{{site.baseurl}}/astro-platgame-lesson/" style="text-decoration:none;"><div style="background-color:#3b82f6;color:white;padding:10px 18px;border-radius:8px;font-weight:bold;">Open AstroPlatformer Demo</div></a>
</div>
