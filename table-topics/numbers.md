---
layout: post
title: Numbers
permalink: /numbers
---

### Numbers

Numbers are what define the platformer level dimensions, object positions, and movement thresholds. Everything from the flag location to the coin size is controlled with numeric values.

```javascript
const baseWidth = 650;
const baseHeight = 400;
const scaleX = width / baseWidth;
const scaleY = height / baseHeight;
```

In AstroPlatformer, this snippet shows how the topic appears in the actual game code and helps demonstrate the idea with a working example. In AstroPlatformer, these numeric constants define the level dimensions and scale factors, which are the foundation for positioning and sizing every object in the game.

<div style="display:flex;gap:10px;flex-wrap:wrap;">
  <a href="{{site.baseurl}}/table" style="text-decoration:none;"><div style="background-color:#f59e0b;color:#111;padding:10px 18px;border-radius:8px;font-weight:bold;">Back to Table</div></a>
  <a href="{{site.baseurl}}/astro-platgame-lesson/" style="text-decoration:none;"><div style="background-color:#3b82f6;color:white;padding:10px 18px;border-radius:8px;font-weight:bold;">Open AstroPlatformer Demo</div></a>
  <a href="{{site.baseurl}}/numbers-lesson" style="text-decoration:none;"><div style="background-color:#10b981;color:white;padding:10px 18px;border-radius:8px;font-weight:bold;">Open Lesson Notebook</div></a>
</div>
