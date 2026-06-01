---
layout: post
title: Methods & Parameters
permalink: /methods-parameters
---

### Methods & Parameters

In object-oriented programming, a **method** is a function defined inside a class that represents an action or behavior that an object instantiated from that class can perform. **Parameters** are the placeholders or variables listed in the method's definition that specify the type of input data the method needs to execute its logic. When you call a method and supply actual data to those placeholders, the inputs are known as **arguments**. Like telling a dog to "fetch" a specific ball — "fetch" is the method, and the ball is the parameter.

Using methods with parameters allows developers to write highly flexible, modular, and reusable blueprints. Instead of creating distinct, hardcoded functions for every slight variation of an action, a single method can process completely different inputs and adapt its behavior dynamically based on the arguments passed into it at runtime.

---

---
### Why it matters

This concept improves the game's structure and makes the code easier to read and maintain.

### Passing Configuration Arguments to Objects

In AstroPlatformer, this snippet shows how the topic appears in the actual game code and helps demonstrate the idea with a working example. The instantiation mechanism uses parameter passing to set up structural components with specific baseline rules:

```javascript
/**
 * Core game class representing a system tracking dashboard.
 */
class Leaderboard {
  /**
   * The constructor method takes two explicit parameters to define its state.
   * @param {Object} controlService - Core engine manager handling application flow.
   * @param {Object} options - Key-value pair configuration settings for this instance.
   */
  constructor(controlService, options) {
    this.controller = controlService;
    this.gameName = options.gameName || 'generic-web-game';
    this.isHidden = options.initiallyHidden !== undefined ? options.initiallyHidden : true;
    
    this.setupDisplay();
  }

  setupDisplay() {
    console.log(`[Leaderboard Method] Initializing display for game container: ${this.gameName}`);
    if (!this.isHidden) {
      console.log("[Leaderboard Method] Rendering table interface immediately onto DOM.");
    }
  }
}

// Executing the method call by sending arguments into the constructor parameters
const activeLeaderboard = new Leaderboard(gameEnv.gameControl, {
  gameName: 'astronaut-platformer-game',
  initiallyHidden: false
---
### Quick Example

```javascript
console.log('Quick example for Methods & Parameters');
```

});
```
In AstroPlatformer, this snippet shows how the topic appears in the actual game code and helps demonstrate the idea with a working example. In AstroPlatformer, this constructor call passes configuration parameters into the leaderboard so it knows the game name and whether to show itself immediately. By isolating these configuration points into an options object parameter, the inner architecture of the Leaderboard class remains independent of any single, specific level blueprint. The execution engine reads the gameName string and the initiallyHidden boolean directly from the incoming arguments, allowing it to modify the visual layout properties during the initial setup phase. 

This decoupling means that if you choose to launch a completely separate mini-game within the same project workspace later on, you can spin up a second scoreboard instance simply by altering the text argument to something like 'alien-defense-game'. Passing variables into parameters eliminates the need to duplicate complex DOM rendering code across multiple scripts. This foundational development practice keeps your engineering workflows organized, cuts down on maintenance issues, and guarantees that your methods behave in a predictable and controlled manner throughout the lifecycle of your web application.
