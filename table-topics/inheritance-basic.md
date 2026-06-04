---
layout: post
title: Inheritance (Basic)
permalink: /inheritance-basic
---

### Inheritance (Basic)

### Overview
In object-oriented programming, **inheritance** is a foundational mechanism that allows a new class (the child or subclass) to adopt the properties, methods, and behaviors of an existing class (the parent or superclass).

AstroPlatformer extends the base Coin class to create a specialized FixedPlatformerCoin that behaves the way the level needs.

This is a textbook example of inheritance: reuse shared behavior while adding platformer-specific behavior.

By structuring systems around a primary parent class, developers avoid duplicating core logic like tracking structural coordinates, loading universal sprite images, or handling basic visibility.

Subclasses can then target unique behaviors via method overriding, allowing for distinct gameplay components that still match the engine's overarching architectural requirements.

---

---
### Why it matters

Structured object code makes the game engine easier to expand and reduces repeated logic as the codebase grows.

### Overriding Methods in a Derived Subclass

In AstroPlatformer, this snippet shows how the topic appears in the actual game code and helps demonstrate the idea with a working example.

This implementation demonstrates how a subclass safely overrides its parent's methods to alter frame-by-frame updates:

```javascript
/**
 * Represents a specialized collectible item that inherits foundational properties 
 * from the generic, base Coin class.
 */
class FixedPlatformerCoin extends Coin {
  /**
   * Overrides the default update routine inherited from the base Coin class.
   * Handles frame-by-frame visibility checks specific to static placement.
   */
  update() {
    // If the object state is already flagged as collected, bypass rendering completely
    if (this.collected) return;
    
    // Call the draw routine to paint the active coin frame onto the canvas context
    this.draw();
  }

  /**
   * Overrides the collection lifecycle logic to inject custom platformer state changes.
   * @param {Object} player - Reference to the active player character triggering the event.
   */
  collect(player) {
    if (this.collected) return;

    // Set instance state flag to prevent multi-trigger overlaps
    this.collected = true;

    // Trigger platformer-specific rewards such as score adjustments or audio loops
    player.incrementScore(100);
    this.playCollectionSound();

    console.log(`[Inheritance Basic] FixedPlatformerCoin ID: ${this.id} collected. Score modified.`);
  }
}
```
In AstroPlatformer, this snippet shows how the topic appears in the actual game code and helps demonstrate the idea with a working example.

In AstroPlatformer, the fixed-platformer coin class extends the base coin class and customizes its update and collect behavior for this level.

Rather than rebuilding asset variables or standard horizontal and vertical positioning systems from scratch, FixedPlatformerCoin relies directly on the properties established inside the original parent Coin object template.

By overriding the update() loop, the child class controls exactly when it displays itself on screen without modifying the core collection engine rules.



This approach guarantees that when a collision event triggers, the custom collect() script updates the scoreboard precisely when the player overlaps with the asset.

This structural pattern means that if you choose to build a bouncing coin or a moving token down the road, you can simply extend the same base class and append unique traits without breaking any preexisting items in your platformer level.

Using this clean hierarchy keeps your codebase lean, highly organized, and easy to maintain as your game features expand. --- ### Quick Example

```javascript

class GameObject { constructor(x, y) { this.x = x; this.y = y; } }

class Player extends GameObject { constructor(x, y) { super(x, y); this.health = 100; } }
```


## Summary

Introduces class inheritance basics, showing how derived classes reuse and extend parent functionality to model game hierarchies.
