---
layout: post
title: Objects (JSON)
permalink: /objects-json
---

### Objects (JSON)

In JavaScript and web development, an **object** is a standalone entity with properties and types, while **JSON (JavaScript Object Notation)** is a standardized format for structuring that data as text. Curly braces group related data together.

The player's setup is one big object — id, sprite path, position, hitbox — all in one place.

Structuring game parameters as data-driven objects allows developers to decouple configurations from functional source code. Instead of hardcoding unique parameters for every distinct obstacle, coin, or platform directly inside the rendering engine, configurations can be stored in clean, nested key-value pairs.

This data-driven layout enables a single class template to dynamically map assets, tracking IDs, and boundary vectors onto live game mechanics at runtime.

---

---
### Why it matters

This concept is essential for connecting the game to external data and keeping persistent state reliable.

### Object Lookup and Key-Value Pairing

In AstroPlatformer, this snippet shows how the topic appears in the actual game code and helps demonstrate the idea with a working example. The level matches coin definitions against game objects using structured sprite data, which is essentially a JSON-style object lookup.

That shows how data shapes connect to runtime objects in the game.

```javascript
/**
 * Processes level layout configuration records by locating and linking 
 * active game entity references based on matching object properties.
 *
 * @param {Object} c - A plain JSON-style configuration node representing a level feature.
 * @param {Object} gameEnv - The global environment wrapper containing active entity arrays.
 */
function bindConfigurationToRuntimeObject(c, gameEnv) {
  // Execute a search through the active object repository.
  // The filter uses an object property pathway (obj.spriteData?.id) to evaluate matches.
  const coinObject = gameEnv.gameObjects.find(
    obj => obj instanceof FixedPlatformerCoin && obj.spriteData?.id === c.id
  );

  // Bind the resulting live object instance directly to an internal tracking property
  c._coinObject = coinObject || null;

  console.log(`[JSON Objects] Linked database ID "${c.id}" to live engine entity: ${c._coinObject !== null}`);
}
```
In AstroPlatformer, this snippet shows how the topic appears in the actual game code and helps demonstrate the idea with a working example. In AstroPlatformer, this snippet looks up a matching game object by ID from a list, which is how structured object data is connected to the running game state.



By querying the nested dictionary structure through obj.spriteData?.id, the code safe-checks for the existence of configuration blocks using the optional chaining operator, avoiding fatal execution errors if a game object happens to lack defined asset parameters. Once a match is confirmed between the configuration property and the engine list, the script assigns a direct memory reference to c._coinObject.

This technique means that metadata loaded from an external text file or state matrix can cleanly command visual components, collision masks, and scoreboard behavior seamlessly. Utilizing structured layout objects forms the backbone of extensible level design, ensuring that adding, removing, or modifying stage components requires editing simple data dictionaries rather than refactoring structural framework code.

--- ### Quick Example

```javascript
const config = JSON.parse(rawJson);
console.log(config.level, config.score);
```

## Summary

Objects (and JSON) let you model game data as structured key/value trees that the engine can map to live entities, keeping configuration separate from runtime code.

