---
layout: post
title: Console Debugging
permalink: /console-debugging
---

### Console Debugging

The platformer logs problems during startup and gameplay so developers can inspect what went wrong without breaking the experience. A simple console warning can reveal whether a service failed or a value was missing.

```javascript
 .catch((err) => console.warn('AstroPlatformer: initScoreManager failed', err));
```

In AstroPlatformer, this snippet shows how the topic appears in the actual game code and helps demonstrate the idea with a working example. In AstroPlatformer, this catch block logs an error when score manager initialization fails, which helps developers diagnose problems without breaking the game.

<div style="display:flex;gap:10px;flex-wrap:wrap;">
  <a href="{{site.baseurl}}/table" style="text-decoration:none;"><div style="background-color:#f59e0b;color:#111;padding:10px 18px;border-radius:8px;font-weight:bold;">Back to Table</div></a>
  <a href="{{site.baseurl}}/astro-platgame-lesson/" style="text-decoration:none;"><div style="background-color:#3b82f6;color:white;padding:10px 18px;border-radius:8px;font-weight:bold;">Open AstroPlatformer Demo</div></a>
  <a href="{{site.baseurl}}/console-debugging-lesson" style="text-decoration:none;"><div style="background-color:#10b981;color:white;padding:10px 18px;border-radius:8px;font-weight:bold;">Open Lesson Notebook</div></a>
</div>
