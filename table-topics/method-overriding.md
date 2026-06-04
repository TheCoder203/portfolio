---
layout: post
title: Method Overriding
permalink: /method-overriding
---

### Method Overriding

### Overview
In object-oriented programming, **method overriding** is a feature that allows a subclass (child class) to provide a specific implementation of a method that is already defined in its superclass (parent class).

The custom coin class overrides the base update and collect methods so platformer coins behave differently from generic game objects.

That is how the level can reuse common logic while customizing exactly what happens on collection.

When a method is overridden, the child class version of the method takes precedence over the parent class version during runtime execution.

This mechanism enables polymorphism, allowing an array of diverse game objects to be processed through a unified interface (such as calling `.update()` on every object in a loop) while ensuring each individual object executes its own specialized, overridden logic.

---

---
### Why it matters

This concept improves the game's structure and makes the code easier to read and maintain.

### Overriding Lifecycle Methods for Custom Behavior

In AstroPlatformer, this snippet shows how the topic appears in the actual game code and helps demonstrate the idea with a working example.

This specific section of the class definition replaces standard parent behaviors with rules structured around collectibles:

```javascript
/**
 * Specialized platformer token class that overrides inherited lifecycle methods
 * from the generic BaseGameObject blueprint.
 */
class FixedPlatformerCoin extends BaseGameObject {
  /**
   * Overrides the generic update method from the parent class.
   * Manages rendering states based on structural collection status flags.
   */
  update() {
    // 1. Check if the entity state has already been flagged as collected
    if (this.collected) return;
    
    // 2. Execute the localized draw sequence to render the sprite onto the canvas
    this.draw();
  }

  /**
   * Overrides the generic collision response method from the parent class.
   * Implements custom scoring triggers and event tracking sequences.
   */
  collect() {
    // 1. Guard against double-collection triggers within overlapping frame updates
    if (this.collected) return;

    // 2. Set the object state to true to remove it from subsequent physics ticks
    this.collected = true;

    // 3. Increment the global player statistics and trigger localized feedback loops
    if (gameEnv.scoreManager) {
      gameEnv.scoreManager.addPoints(this.value || 10);
    }
    this.triggerSparkleEffect();

    console.log(`[Method Overriding] Custom collect sequence completed for Coin ID: ${this.id}`);
  }
}
```
In AstroPlatformer, this snippet shows how the topic appears in the actual game code and helps demonstrate the idea with a working example.

In AstroPlatformer, the custom coin class overrides base methods so it can draw itself and count a collection in a platformer-specific way.

By examining this structural implementation, you can see how overriding intercepts the generic lifecycle loop to implement custom rules.

When the parent game loop sweeps through all registered entities and calls .update() or .collect(), the engine automatically bypasses the basic placeholder code in the base class and jumps straight into these custom lines instead.



This design approach prevents developers from polluting the base class with highly specific logic, like handling scoreboard updates or sparkle particle systems, that other non-collectible items (like solid bricks or background trees) would never use.

By leaving the parent class lean, you can create dozens of specialized subclasses—such as moving enemies, breakable blocks, or hidden doors—each overriding the exact same core methods to produce an incredibly rich and varied world while sharing a clean, unified control framework.

--- ### Quick Example

```javascript

class GameObject { constructor(x, y) { this.x = x; this.y = y; } }

class Player extends GameObject { constructor(x, y) { super(x, y); this.health = 100; } }
```


## Summary

Explains how subclasses override parent methods to provide specialized behavior (like custom coin collection), enabling polymorphism and code reuse.
