---
layout: post
title: Mathematical Operators
permalink: /mathematical-operators
---

### Mathematical Operators

Operators are used to scale the level, position objects, and calculate collisions. AstroPlatformer uses arithmetic to transform base layout values into screen coordinates and game motion.

```javascript
const scaleX = width / baseWidth;
const scaleY = height / baseHeight;
Object.assign(p._el.style, {
    left: p.sx + 'px',
    top: (top + p.sy) + 'px'
  });
```

In AstroPlatformer, this snippet shows how the topic appears in the actual game code and helps demonstrate the idea with a working example. In AstroPlatformer, these arithmetic calculations convert base layout values into scaled positions, which keeps the level sized correctly on different screens.

<div style="display:flex;gap:10px;flex-wrap:wrap;">
  <a href="{{site.baseurl}}/table" style="text-decoration:none;"><div style="background-color:#f59e0b;color:#111;padding:10px 18px;border-radius:8px;font-weight:bold;">Back to Table</div></a>
  <a href="{{site.baseurl}}/astro-platgame-lesson/" style="text-decoration:none;"><div style="background-color:#3b82f6;color:white;padding:10px 18px;border-radius:8px;font-weight:bold;">Open AstroPlatformer Demo</div></a>
  <a href="{{site.baseurl}}/mathematical-operators-lesson" style="text-decoration:none;"><div style="background-color:#10b981;color:white;padding:10px 18px;border-radius:8px;font-weight:bold;">Open Lesson Notebook</div></a>
</div>
