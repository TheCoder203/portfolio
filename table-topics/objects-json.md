---
layout: post
title: Objects (JSON)
permalink: /objects-json
---

### Objects (JSON)

The level matches coin definitions against game objects using structured sprite data, which is essentially a JSON-style object lookup. That shows how data shapes connect to runtime objects in the game.

```javascript
const coinObject = gameEnv.gameObjects.find(
    obj => obj instanceof FixedPlatformerCoin && obj.spriteData?.id === c.id
  );
  c._coinObject = coinObject || null;
```

In AstroPlatformer, this snippet shows how the topic appears in the actual game code and helps demonstrate the idea with a working example. In AstroPlatformer, this snippet looks up a matching game object by ID from a list, which is how structured object data is connected to the running game state.

<div style="display:flex;gap:10px;flex-wrap:wrap;">
  <a href="{{site.baseurl}}/table" style="text-decoration:none;"><div style="background-color:#f59e0b;color:#111;padding:10px 18px;border-radius:8px;font-weight:bold;">Back to Table</div></a>
  <a href="{{site.baseurl}}/astro-platgame-lesson/" style="text-decoration:none;"><div style="background-color:#3b82f6;color:white;padding:10px 18px;border-radius:8px;font-weight:bold;">Open AstroPlatformer Demo</div></a>
  <a href="{{site.baseurl}}/objects-json-lesson" style="text-decoration:none;"><div style="background-color:#10b981;color:white;padding:10px 18px;border-radius:8px;font-weight:bold;">Open Lesson Notebook</div></a>
</div>
