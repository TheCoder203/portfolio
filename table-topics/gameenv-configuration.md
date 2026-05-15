---
layout: post
title: GameEnv Configuration
permalink: /gameenv-configuration
---

### GameEnv Configuration

The game environment config is what tells AstroPlatformer the screen size, level path, and HUD layout. That setup is important because it makes the game behave correctly across different screens and game containers.

```javascript
const path   = gameEnv.path;
const width  = gameEnv.innerWidth;
const height = gameEnv.innerHeight;
const baseWidth  = 650;
const baseHeight = 400;
```

In AstroPlatformer, this snippet shows how the topic appears in the actual game code and helps demonstrate the idea with a working example. In AstroPlatformer, this code reads the game environment dimensions and constructs the level scaling, which helps the platformer adapt to different screen sizes.

<div style="display:flex;gap:10px;flex-wrap:wrap;">
  <a href="{{site.baseurl}}/table" style="text-decoration:none;"><div style="background-color:#f59e0b;color:#111;padding:10px 18px;border-radius:8px;font-weight:bold;">Back to Table</div></a>
  <a href="{{site.baseurl}}/astro-platgame-lesson/" style="text-decoration:none;"><div style="background-color:#3b82f6;color:white;padding:10px 18px;border-radius:8px;font-weight:bold;">Open AstroPlatformer Demo</div></a>
  <a href="{{site.baseurl}}/gameenv-configuration-lesson" style="text-decoration:none;"><div style="background-color:#10b981;color:white;padding:10px 18px;border-radius:8px;font-weight:bold;">Open Lesson Notebook</div></a>
</div>
