---
layout: post
title: Instantiation & Objects
permalink: /instantiation-objects
---

### Instantiation & Objects

In object-oriented programming, **instantiation** is the process of generating a concrete, live instance of a resource blueprint defined by a class. Using `new` turns a class into an actual object. Like baking a real cookie from the cutter. Every `new Car(...)` is its own separate car with its own color. The class acts as the architectural plan, dictating the properties and capabilities that the resulting object will possess, but it does not contain unique runtime data itself until it is explicitly instantiated in memory.

The level creates actual runtime objects like the leaderboard and coin instances when the game starts. Each new object gets its own state and behavior, which is how the code turns definitions into real gameplay elements. This separation ensures that two distinct objects of the same class can co-exist simultaneously without cross-contaminating their operational values.

---

### Executing Object Construction at Runtime

In AstroPlatformer, this snippet shows how the topic appears in the actual game code and helps demonstrate the idea with a working example. The code initializes critical score tracking systems by spinning up a persistent object reference:

```javascript
/**
 * Core initialization sequence for managing stage elements and statistics.
 * Demonstrates conditional instantiation of persistent game components.
 */
function initializeStageComponents(gameEnv) {
  // Check for an existing shared leaderboard registry or instantiate a unique instance
  this._leaderboard = window.leaderboardInstance || new Leaderboard(gameEnv.gameControl, {
    gameName: 'astronaut-platformer-game',
    initiallyHidden: false
  });

  // Example of spawning multiple separate coin instances from a single class blueprint
  this.coinA = new FixedPlatformerCoin({ id: "coin_left", x: 150, y: 300 });
  this.coinB = new FixedPlatformerCoin({ id: "coin_right", x: 450, y: 300 });

  console.log(`[Instantiation] Leaderboard tracking active for: ${this._leaderboard.gameName}`);
  console.log(`[Instantiation] Multi-object state check: CoinA ID is '${this.coinA.id}', CoinB ID is '${this.coinB.id}'`);
}
```
In AstroPlatformer, this snippet shows how the topic appears in the actual game code and helps demonstrate the idea with a working example. In AstroPlatformer, this code creates the leaderboard instance when the game starts, turning configuration values into a live object used throughout the level. By using the new keyword alongside the Leaderboard class reference, the JavaScript engine allocates a unique block of system memory specifically to hold that object's inner state variables, such as its active database connection details and visual DOM layout flags. 

This pattern allows the engine to decouple definition from execution; for instance, while coinA and coinB share the exact same structural logic inherited from their parent class, each retains its own individual coordinates, pixel buffers, and collection status flags. If a player collides with coinA, its internal boolean flips to true, while coinB remains entirely uncollected and active on the screen. Mastering instantiation is what allows a static file of written rules to explode into a fluid, responsive world populated by hundreds of independent, interactive items reacting dynamically to user input.