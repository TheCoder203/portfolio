---
layout: post
title: Method Overriding
permalink: /method-overriding
---

### Method Overriding

The custom coin class overrides the base update and collect methods so platformer coins behave differently from generic game objects. That is how the level can reuse common logic while customizing exactly what happens on collection.

```javascript
update() {
    if (this.collected) return;
    this.draw();
  }

  collect() {
    if (this.collected) return;
    ...
  }
```

In AstroPlatformer, this snippet shows how the topic appears in the actual game code and helps demonstrate the idea with a working example. In AstroPlatformer, the custom coin class overrides base methods so it can draw itself and count a collection in a platformer-specific way.

<div style="display:flex;gap:10px;flex-wrap:wrap;">
  <a href="{{site.baseurl}}/table" style="text-decoration:none;"><div style="background-color:#f59e0b;color:#111;padding:10px 18px;border-radius:8px;font-weight:bold;">Back to Table</div></a>
  <a href="{{site.baseurl}}/astro-platgame-lesson/" style="text-decoration:none;"><div style="background-color:#3b82f6;color:white;padding:10px 18px;border-radius:8px;font-weight:bold;">Open AstroPlatformer Demo</div></a>
  <a href="{{site.baseurl}}/method-overriding-lesson" style="text-decoration:none;"><div style="background-color:#10b981;color:white;padding:10px 18px;border-radius:8px;font-weight:bold;">Open Lesson Notebook</div></a>
</div>
