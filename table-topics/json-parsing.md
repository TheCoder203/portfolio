---
layout: post
title: JSON Parsing
permalink: /json-parsing
---

### JSON Parsing

AstroPlatformer reads saved coin totals from localStorage and turns that string into a number the game can use. Parsing JSON-style data or stored values is a key way to make text data useful in gameplay.

```javascript
const savedCoins = parseInt(localStorage.getItem('coinsCollected') || '0') || 0;
const newTotal = savedCoins + this.value;
localStorage.setItem('coinsCollected', newTotal);
```

In AstroPlatformer, this snippet shows how the topic appears in the actual game code and helps demonstrate the idea with a working example. In AstroPlatformer, this code reads the saved coin total from localStorage, converts it from text to a number, and stores the updated value again, which makes persistent state usable in gameplay.

<div style="display:flex;gap:10px;flex-wrap:wrap;">
  <a href="{{site.baseurl}}/table" style="text-decoration:none;"><div style="background-color:#f59e0b;color:#111;padding:10px 18px;border-radius:8px;font-weight:bold;">Back to Table</div></a>
  <a href="{{site.baseurl}}/astro-platgame-lesson/" style="text-decoration:none;"><div style="background-color:#3b82f6;color:white;padding:10px 18px;border-radius:8px;font-weight:bold;">Open AstroPlatformer Demo</div></a>
  <a href="{{site.baseurl}}/allhw" style="text-decoration:none;"><div style="background-color:#10b981;color:white;padding:10px 18px;border-radius:8px;font-weight:bold;">Open AllHW Notebook</div></a>
</div>
