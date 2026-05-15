---
layout: post
title: Strings
permalink: /strings
---

### Strings

Text appears in the game as labels, messages, and debug output, such as the goal sign or the console log. Building and assigning strings is how the level talks to the player.

```javascript
const goalLbl = document.createElement('div');
goalLbl.textContent = 'GOAL';
```

In AstroPlatformer, this snippet shows how the topic appears in the actual game code and helps demonstrate the idea with a working example. In AstroPlatformer, this snippet creates a DOM label and sets its text content, which is how the game shows the goal sign to the player.

<div style="display:flex;gap:10px;flex-wrap:wrap;">
  <a href="{{site.baseurl}}/table" style="text-decoration:none;"><div style="background-color:#f59e0b;color:#111;padding:10px 18px;border-radius:8px;font-weight:bold;">Back to Table</div></a>
  <a href="{{site.baseurl}}/astro-platgame-lesson/" style="text-decoration:none;"><div style="background-color:#3b82f6;color:white;padding:10px 18px;border-radius:8px;font-weight:bold;">Open AstroPlatformer Demo</div></a>
</div>
