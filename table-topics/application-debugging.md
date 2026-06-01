---
layout: post
title: Application Debugging
permalink: /application-debugging
---

# Application Debugging

Application debugging focuses on inspecting stored browser data and application state.

Modern web applications store information such as:
- Cookies
- localStorage
- sessionStorage
- Authentication tokens
- User settings
- Cached data

Developers inspect this information using the DevTools Application tab.

---

### Why Application Debugging Matters

Applications rely heavily on stored state.

Problems can occur when:
- Tokens expire
- Incorrect data is stored
- Cache becomes corrupted
- Sessions fail
- User data becomes inconsistent

Application debugging helps developers inspect and manage this data safely.

---

---
### Why it matters

Clear debugging and documentation habits make the game easier to maintain and fix when issues arise.

### localStorage Example

Example:

```javascript id="appdbg1"
localStorage.setItem('highScore', 1200);
---
### Quick Example

```javascript
console.log('Player position:', player.x, player.y);
```


const score = localStorage.getItem('highScore');

console.log(score);
```
<div style="display:flex;gap:10px;flex-wrap:wrap;"> <a href="{{site.baseurl}}/table" style="text-decoration:none;"><div style="background-color:#f59e0b;color:#111;padding:10px 18px;border-radius:8px;font-weight:bold;">Back to Table</div></a> <a href="{{site.baseurl}}/astro-platgame-lesson/" style="text-decoration:none;"><div style="background-color:#3b82f6;color:white;padding:10px 18px;border-radius:8px;font-weight:bold;">Open AstroPlatformer Demo</div></a> <a href="{{site.baseurl}}/application-debugging-lesson" style="text-decoration:none;"><div style="background-color:#10b981;color:white;padding:10px 18px;border-radius:8px;font-weight:bold;">Open Lesson Notebook</div></a> </div>
