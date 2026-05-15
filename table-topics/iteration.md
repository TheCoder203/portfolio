---
layout: post
title: Iteration
permalink: /iteration
---

### Iteration

Loops power the level by iterating over platforms, coins, and overlays. Instead of handling each object separately, AstroPlatformer processes collections in bulk so the code stays compact and efficient.

```javascript
for (const p of this._platforms) {
    if (p._el) {
      Object.assign(p._el.style, { ... });
    }
  }
```

In AstroPlatformer, this snippet shows how the topic appears in the actual game code and helps demonstrate the idea with a working example. In AstroPlatformer, the loop updates every platform element in the level, which is how the game handles all of its objects efficiently without repeating code.

<div style="display:flex;gap:10px;flex-wrap:wrap;">
  <a href="{{site.baseurl}}/table" style="text-decoration:none;"><div style="background-color:#f59e0b;color:#111;padding:10px 18px;border-radius:8px;font-weight:bold;">Back to Table</div></a>
  <a href="{{site.baseurl}}/astro-platgame-lesson/" style="text-decoration:none;"><div style="background-color:#3b82f6;color:white;padding:10px 18px;border-radius:8px;font-weight:bold;">Open AstroPlatformer Demo</div></a>
  <a href="{{site.baseurl}}/iteration-lesson" style="text-decoration:none;"><div style="background-color:#10b981;color:white;padding:10px 18px;border-radius:8px;font-weight:bold;">Open Lesson Notebook</div></a>
</div>
