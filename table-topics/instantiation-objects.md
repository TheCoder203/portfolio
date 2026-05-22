---
layout: post
title: Instantiation & Objects
permalink: /instantiation-objects
---

### Instantiation & Objects

Using new turns a class into an actual object. Like baking a real cookie from the cutter. Every new Car(...) is its own separate car with its own color.

The level creates actual runtime objects like the leaderboard and coin instances when the game starts. Each new object gets its own state and behavior, which is how the code turns definitions into real gameplay elements.

```javascript
this._leaderboard = window.leaderboardInstance || new Leaderboard(gameEnv.gameControl, {
    gameName: 'astronaut-platformer-game',
    initiallyHidden: false
  });
```

In AstroPlatformer, this snippet shows how the topic appears in the actual game code and helps demonstrate the idea with a working example. In AstroPlatformer, this code creates the leaderboard instance when the game starts, turning configuration values into a live object used throughout the level.

<div style="display:flex;gap:10px;flex-wrap:wrap;">
  <a href="{{site.baseurl}}/table" style="text-decoration:none;"><div style="background-color:#f59e0b;color:#111;padding:10px 18px;border-radius:8px;font-weight:bold;">Back to Table</div></a>
  <a href="{{site.baseurl}}/astro-platgame-lesson/" style="text-decoration:none;"><div style="background-color:#3b82f6;color:white;padding:10px 18px;border-radius:8px;font-weight:bold;">Open AstroPlatformer Demo</div></a>
  <a href="{{site.baseurl}}/instantiation-objects-lesson" style="text-decoration:none;"><div style="background-color:#10b981;color:white;padding:10px 18px;border-radius:8px;font-weight:bold;">Open Lesson Notebook</div></a>
</div>
