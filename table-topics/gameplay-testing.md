---
layout: post
title: Gameplay Testing
permalink: /gameplay-testing
---

### Gameplay Testing

### Overview
In interactive application design, **gameplay testing** and logical validation are the processes used to verify that mechanics perform reliably under all user behaviors.

AstroPlatformer is tested in the code by checking coin collection, player death, and goal logic.

That kind of test thinking is what keeps the level from having obvious bugs when it runs in the browser.

Rather than relying entirely on manual playtesting, modern web engines programmatically validate states within the runtime loop.

By defining specific mathematical boundaries for success and failure, developers can automate boundary test cases—ensuring that physical elements like velocity, hitboxes, and scale adjustments cooperate seamlessly to produce an accurate game state.

---

---
### Why it matters

This concept improves the game's structure and makes the code easier to read and maintain.

### Validating Goal Conditions via Bounding Box Triggers

In AstroPlatformer, this snippet shows how the topic appears in the actual game code and helps demonstrate the idea with a working example.

This segment validates spatial intersections to confirm whether a player has completed the objective:

```javascript
/**
 * Evaluates the spatial intersection between the Player Character (PC)
 * and the Level Finish Flag to trigger the transition routine.
 * * @param {number} pcx - Player character's current X-coordinate.
 * @param {number} pcy - Player character's current Y-coordinate.
 * @param {number} fx  - Finish flag's base X-coordinate reference point.
 * @param {number} fy  - Finish flag's base Y-coordinate reference point.
 */
function checkLevelCompletion(pcx, pcy, fx, fy) {
  // Define bounding boundaries dynamically adjusted by the game's global scale factor
  const leftBoundary   = fx - 14 * this._scaleX;
  const rightBoundary  = fx + 30 * this._scaleX;
  const topBoundary    = fy;
  const bottomBoundary = fy + 58 * this._scaleY;

  // Perform an Axis-Aligned Bounding Box (AABB) intersection check
  if (pcx > leftBoundary && pcx < rightBoundary && pcy > topBoundary && pcy < bottomBoundary) {
    // Self-reference callback to execute state-machine wrap up
    self._winLevel();
    return true; // Match confirmed, execution terminated safely
  }
  
  return false; // Player is not within the completion trigger zone
}
```
In AstroPlatformer, this snippet checks whether the player has reached the goal flag and then triggers the level win sequence, which is a core part of gameplay correctness.

By examining this equation, we see how the test conditions use this._scaleX and this._scaleY to scale the target hitbox alongside changing window resolutions.

Testing this logic confirms that regardless of frame rate stutter or monitor size, the collision coordinates line up properly, preventing players from clipping straight through the finish line without completing the level.



This proportional scaling calculation safeguards the fundamental rules of the world against different display types.

When a user changes orientation or resizes their desktop screen, the bounding boxes morph seamlessly alongside the visual assets.

Consequently, the player never encounters invisible walls or disjointed win conditions. Implementing these adaptive coordinate checks acts as an internal quality control mechanism that executes silently on every frame.

--- ### Quick Example

```javascript
function testPlayerReachedFinish(player, flag) {
  return player.x > flag.x - 10 &&
         player.x < flag.x + flag.width + 10 &&
         player.y > flag.y - 10 &&
         player.y < flag.y + flag.height + 10;
}
```


## Summary

Explains methods for validating gameplay mechanics (bounding boxes and AABB checks) so levels behave consistently across resolutions and inputs.


## Summary

Explains methods for validating gameplay mechanics (bounding boxes and AABB checks) so levels behave consistently across resolutions and inputs.
