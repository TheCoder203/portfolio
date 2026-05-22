---
layout: post
title: Methods & Parameters
permalink: /methods-parameters
---

### Methods & Parameters
 A method is a function inside a class. Parameters are the inputs it needs. Like telling a dog to "fetch" a specific ball — "fetch" is the method, the ball is the parameter.

A method like new Leaderboard(...) takes parameters that tell it how the game should behave, including the game name and visibility settings. Passing those values in makes the same code reusable for different levels or games.

```javascript
new Leaderboard(gameEnv.gameControl, {
    gameName: 'astronaut-platformer-game',
    initiallyHidden: false
  });
```

In AstroPlatformer, this snippet shows how the topic appears in the actual game code and helps demonstrate the idea with a working example. In AstroPlatformer, this constructor call passes configuration parameters into the leaderboard so it knows the game name and whether to show itself immediately.

<div style="display:flex;gap:10px;flex-wrap:wrap;">
  <a href="{{site.baseurl}}/table" style="text-decoration:none;"><div style="background-color:#f59e0b;color:#111;padding:10px 18px;border-radius:8px;font-weight:bold;">Back to Table</div></a>
  <a href="{{site.baseurl}}/astro-platgame-lesson/" style="text-decoration:none;"><div style="background-color:#3b82f6;color:white;padding:10px 18px;border-radius:8px;font-weight:bold;">Open AstroPlatformer Demo</div></a>
  <a href="{{site.baseurl}}/methods-parameters-lesson" style="text-decoration:none;"><div style="background-color:#10b981;color:white;padding:10px 18px;border-radius:8px;font-weight:bold;">Open Lesson Notebook</div></a>
</div>
