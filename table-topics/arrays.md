---
layout: post
title: Arrays
permalink: /arrays
---

### Arrays

Arrays are the backbone of the level layout: platforms, coins, spikes, and game state all live in lists that the loop can process. That makes the code easier to maintain and allows the game to draw dozens of objects without repeating logic.

```javascript
for (const p of this._platforms) {
    const el = document.createElement('div');
    ...
    container.appendChild(el);
    this._overlays.push(el);
  }
```

In AstroPlatformer, this snippet shows how the topic appears in the actual game code and helps demonstrate the idea with a working example. In AstroPlatformer, this loop walks through platform definitions and adds each one to the DOM, so the level can render many platforms from a single data structure.

<div style="display:flex;gap:10px;flex-wrap:wrap;">
  <a href="{{site.baseurl}}/table" style="text-decoration:none;"><div style="background-color:#f59e0b;color:#111;padding:10px 18px;border-radius:8px;font-weight:bold;">Back to Table</div></a>
  <a href="{{site.baseurl}}/astro-platgame-lesson/" style="text-decoration:none;"><div style="background-color:#3b82f6;color:white;padding:10px 18px;border-radius:8px;font-weight:bold;">Open AstroPlatformer Demo</div></a>
  <a href="{{site.baseurl}}/arrays-lesson" style="text-decoration:none;"><div style="background-color:#10b981;color:white;padding:10px 18px;border-radius:8px;font-weight:bold;">Open Lesson Notebook</div></a>
</div>
