---
layout: post
title: Canvas Rendering
permalink: /canvas-rendering
---

### Canvas Rendering

AstroPlatformer builds visual objects on the fly using DOM elements and style rules, which is a form of rendering that’s similar in spirit to canvas drawing. It shows how game entities can be created, styled, and attached to the screen dynamically.

```javascript
const banner = document.createElement('div');
Object.assign(banner.style, {
    position:'absolute',
    left: (this._flagX + 3*scaleX)+'px',
    top:  (top + this._flagY)+'px',
    width:(24*scaleX)+'px', height:(16*scaleY)+'px',
    background:'#00ff88', ...
  });
```

In AstroPlatformer, this snippet shows how the topic appears in the actual game code and helps demonstrate the idea with a working example. In AstroPlatformer, this snippet creates a flag banner element and styles it at runtime, showing how game visuals are built from code and attached to the screen.

<div style="display:flex;gap:10px;flex-wrap:wrap;">
  <a href="{{site.baseurl}}/table" style="text-decoration:none;"><div style="background-color:#f59e0b;color:#111;padding:10px 18px;border-radius:8px;font-weight:bold;">Back to Table</div></a>
  <a href="{{site.baseurl}}/astro-platgame-lesson/" style="text-decoration:none;"><div style="background-color:#3b82f6;color:white;padding:10px 18px;border-radius:8px;font-weight:bold;">Open AstroPlatformer Demo</div></a>
  <a href="{{site.baseurl}}/allhw" style="text-decoration:none;"><div style="background-color:#10b981;color:white;padding:10px 18px;border-radius:8px;font-weight:bold;">Open AllHW Notebook</div></a>
</div>
