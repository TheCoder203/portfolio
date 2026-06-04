---
layout: post
title: Constructor Chaining
permalink: /constructor-chaining
---

### Constructor Chaining

In object-oriented programming, **constructor chaining** is a powerful architectural pattern where a constructor invokes another constructor within the same class hierarchy. When dealing with class inheritance, a derived (child) class must call the constructor of its base (parent) class before initializing its own fields.



This initialization link is forged using the `super()` keyword. Executing `super()` ensures that all core infrastructure, standard environments, and state variables belonging to the parent entity are built first.

Think of it like filling out a mandatory baseline registration form before you are allowed to add your own custom, specialized fields on top. In JavaScript, invoking `super()` is not optional; failing to call it in a sub-class constructor before accessing `this` throws a runtime reference error, as the engine requires the foundational blueprint to exist before appending additions.

---

---
### Why it matters

Structured object code makes the game engine easier to expand and reduces repeated logic as the codebase grows.

### Implementing the Base Initialization

The level object starts by setting up its constructor state, which is the first step in building a platformer instance. That constructor sets defaults and prepares the game for all the later logic that depends on those values.

---
### Quick Example

```javascript
class GameObject {
  constructor(x, y) {
    this.x = x;
    this.y = y;
  }
}

class Player extends GameObject {
  constructor(x, y) {
    super(x, y);
    this.health = 100;
  }
}
```

```javascript
class AstroPlatformer {
  /**
   * Base constructor for the core game engine environment.
   * @param {Object} gameEnv - Contains configurations, paths, and window boundaries.
   */
  constructor(gameEnv) {
    if (!gameEnv) {
      throw new Error("Initialization Failed: a valid game environment object is required.");
    }

    // Extracting global environment parameters
    this.path = gameEnv.path;
    this.width = gameEnv.innerWidth || window.innerWidth;
    this.height = gameEnv.innerHeight || window.innerHeight;

    // Establishing universal state variables for any active stage
    this.gravity = 0.5;
    this.score = 0;
    this.isGameOver = false;
    this.entities = []; // Array containing elements like players, floors, and obstacles

    console.log(`[AstroPlatformer Engine] Base configuration initialized (${this.width}x${this.height}).`);
  }

  /**
   * Initiates the standard engine processes.
   */
  initEngineLoop() {
    console.log(`Starting loop execution using gravity constant: ${this.gravity}`);
  }
}

/**
 * Child class demonstrating Constructor Chaining via standard inheritance.
 */
class NebulaSector extends AstroPlatformer {
  /**
   * Custom level builder extending the baseline platformer settings.
   * @param {Object} gameEnv - Passed upstream to configure foundational values.
   * @param {String} stageTheme - A visual and stylistic tag unique to this instance.
   */
  constructor(gameEnv, stageTheme) {
    // 1. Chain constructors by calling super(). This sets up engine parameters first.
    super(gameEnv);

    // 2. Safely introduce child class properties now that 'this' is instantiated.
    this.levelTheme = stageTheme || "Default Space Grid";
    this.enemySpawnRate = 2.5;
    this.isLevelCleared = false;

    console.log(`[Level Extension] '${this.levelTheme}' successfully chained to base engine.`);
  }

  /**
   * Overrides and enhances the default initiation logic.
   */
  initEngineLoop() {
    super.initEngineLoop(); // Run the parent's logic first to maintain consistency
    console.log(`Injecting theme assets and spawning background layers for: ${this.levelTheme}`);
  }
}

// Sample Initialization demonstrating the pattern in action
const mockEnvironment = { path: "/assets/game/sprites/", innerWidth: 1920, innerHeight: 1080 };
const activeStage = new NebulaSector(mockEnvironment, "Cosmic Horizon");
activeStage.initEngineLoop();
```

## Summary

Describes constructor chaining and super() usage to initialize base class state before extending behavior in subclasses, preventing runtime errors and ensuring proper setup.
