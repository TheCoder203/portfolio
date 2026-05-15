---
layout: post
title: String Operations
permalink: /string-operations
---

### String Operations

String operations come into play when the game builds labels and debug output. For example, a template literal formats the coin total message so the logged output is readable.

```javascript
console.log(`Coin collected! Total coins: ${newTotal}`);
```

In AstroPlatformer, this snippet shows how the topic appears in the actual game code and helps demonstrate the idea with a working example. In AstroPlatformer, this console log builds a text message with a template literal so the game can report the coin total in a readable way.

<div style="display:flex;gap:10px;flex-wrap:wrap;">
  <a href="{{site.baseurl}}/table" style="text-decoration:none;"><div style="background-color:#f59e0b;color:#111;padding:10px 18px;border-radius:8px;font-weight:bold;">Back to Table</div></a>
  <a href="{{site.baseurl}}/astro-platgame-lesson/" style="text-decoration:none;"><div style="background-color:#3b82f6;color:white;padding:10px 18px;border-radius:8px;font-weight:bold;">Open AstroPlatformer Demo</div></a>
  <a href="{{site.baseurl}}/allhw" style="text-decoration:none;"><div style="background-color:#10b981;color:white;padding:10px 18px;border-radius:8px;font-weight:bold;">Open AllHW Notebook</div></a>
</div>
