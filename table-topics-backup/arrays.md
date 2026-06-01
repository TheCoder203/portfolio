---
layout: post
title: Arrays
permalink: /arrays
---

# Arrays

Arrays are one of the most important data structures in programming. An array is a collection of values stored in a single variable. Instead of creating separate variables for every object, developers can organize large groups of related data into arrays and process them efficiently.

Arrays are extremely useful in game development because games often manage many objects at the same time, including:

- Platforms
- Coins
- Enemies
- Particles
- Projectiles
- Obstacles
- Player inventories
- Animation frames

In AstroPlatformer, arrays are used heavily throughout the game engine to manage level layouts, objects, overlays, and game state. Arrays allow the game to dynamically render large numbers of objects without duplicating code.

---

### What is an Array?

A JavaScript array stores multiple values inside a single structure.

Example:

```javascript
const coins = [10, 20, 30, 40];
```

This array contains four numbers.

Each item inside an array has an index position:

| Index | Value |
|---|---|
| 0 | 10 |
| 1 | 20 |
| 2 | 30 |
| 3 | 40 |

Arrays use zero-based indexing, meaning counting starts at 0.

---

### Accessing Array Elements

Individual elements can be accessed using bracket notation.

```javascript
const enemies = ['slime', 'robot', 'drone'];

console.log(enemies[0]);
console.log(enemies[1]);
```

Output:

```javascript
slime
robot
```

This allows programs to retrieve specific data from large collections.

---

### Why Arrays Matter in Games

Games constantly manage many objects simultaneously.

Without arrays, developers would need repetitive code like:

```javascript
const platform1 = {};
const platform2 = {};
const platform3 = {};
const platform4 = {};
```

This quickly becomes difficult to manage.

Arrays solve this problem by organizing data into structured collections.

Example:

```javascript
const platforms = [
  { x: 100, y: 200 },
  { x: 300, y: 250 },
  { x: 500, y: 180 }
];
```

Now the game can process all platforms using loops.

---

### AstroPlatformer Example

The following code comes directly from AstroPlatformer:

```javascript
for (const p of this._platforms) {
    const el = document.createElement('div');
    ...
    container.appendChild(el);
    this._overlays.push(el);
}
```

This loop processes the platform array and creates visual platform elements dynamically.

Instead of manually creating every platform one at a time, the game stores platform data in an array and loops through it automatically.

This makes the system scalable and much easier to maintain.

---

### Looping Through Arrays

One of the biggest advantages of arrays is the ability to loop through large collections of data.

Example:

```javascript
const coins = [5, 10, 15, 20];

for (const coin of coins) {
  console.log(coin);
}
```

Output:

```javascript
5
10
15
20
```

The loop processes each element automatically.

This is extremely important in games where hundreds of objects may exist at once.

---

### Dynamic Object Creation

In AstroPlatformer, arrays are used to create objects dynamically.

Example:

```javascript
const enemies = [
  { x: 100, y: 200 },
  { x: 300, y: 150 },
  { x: 500, y: 250 }
];

for (const enemy of enemies) {
  spawnEnemy(enemy.x, enemy.y);
}
```

This allows the game to generate multiple enemies from a single data structure.

Without arrays, developers would need to write repetitive code for every enemy.

---

### Storing Complex Data

Arrays can store many different types of values:

- Numbers
- Strings
- Booleans
- Objects
- Functions
- Other arrays

Example:

```javascript
const player = [
  'Astro',
  100,
  true
];
```

Arrays can also store objects:

```javascript
const platforms = [
  { x: 100, y: 300, width: 200 },
  { x: 400, y: 250, width: 150 }
];
```

Object arrays are extremely common in game engines.

---

### Adding Elements to Arrays

New elements can be added using `.push()`.

Example:

```javascript
const inventory = [];

inventory.push('Key');
inventory.push('Potion');

console.log(inventory);
```

Output:

```javascript
['Key', 'Potion']
```

In games, `.push()` is often used for:

- Collecting items
- Spawning enemies
- Adding particles
- Tracking projectiles

---

### Removing Elements from Arrays

Arrays can also remove elements.

Example using `.pop()`:

```javascript
const items = ['Sword', 'Shield'];

items.pop();

console.log(items);
```

Output:

```javascript
['Sword']
```

Example using `.splice()`:

```javascript
const enemies = ['slime', 'robot', 'drone'];

enemies.splice(1, 1);

console.log(enemies);
```

Output:

```javascript
['slime', 'drone']
```

This is useful when objects are destroyed or collected.

---

### Arrays and Game State

Arrays are often used to store game state information.

Examples include:

- Active enemies
- Collected coins
- Current projectiles
- Inventory items
- Animation frames
- Collision objects

Example:

```javascript
const collectedCoins = [];

function collectCoin(id) {
  collectedCoins.push(id);
}
```

The array tracks which coins the player has collected.

---

### Arrays and Rendering

Rendering systems frequently use arrays to draw objects on screen.

Example:

```javascript
for (const particle of particles) {
  drawParticle(particle);
}
```

This allows the game engine to process many visual elements efficiently.

AstroPlatformer uses similar techniques to render platforms and overlays.

---

### Nested Arrays

Arrays can contain other arrays.

Example:

```javascript
const levelMap = [
  [1, 1, 1, 1],
  [0, 0, 1, 0],
  [1, 0, 0, 1]
];
```

This type of structure is commonly used for:

- Tile maps
- Grid systems
- Collision maps
- Board games

Nested arrays are extremely important in level design.

---

### Useful Array Methods

JavaScript arrays include many built-in methods.

Examples:

| Method | Purpose |
|---|---|
| `.push()` | Add element |
| `.pop()` | Remove last element |
| `.shift()` | Remove first element |
| `.unshift()` | Add to beginning |
| `.includes()` | Check for value |
| `.length` | Get array size |
| `.map()` | Transform elements |
| `.filter()` | Select elements |
| `.find()` | Search for element |

Example:

```javascript
const scores = [10, 20, 30];

console.log(scores.length);
```

Output:

```javascript
3
```

---

### Arrays and Performance

Arrays help improve performance because developers can process many objects using shared logic.

Instead of writing repetitive code:

```javascript
drawPlatform(platform1);
drawPlatform(platform2);
drawPlatform(platform3);
```

The game can use loops:

```javascript
for (const platform of platforms) {
  drawPlatform(platform);
}
```

This creates cleaner and more scalable code.

---

### Why Arrays Matter in AstroPlatformer

AstroPlatformer relies heavily on arrays for managing:

- Platforms
- Overlays
- Coins
- Hazards
- Enemy data
- Level layouts
- Collision objects
- Rendering systems

The platform array allows the game to generate entire levels dynamically from stored data structures.

This approach:

- Reduces duplicated code
- Improves scalability
- Simplifies rendering
- Makes level editing easier
- Improves maintainability

Arrays are one of the core systems that make the game's architecture efficient and flexible.

---

### Key Takeaways

- Arrays store collections of data
- Arrays use zero-based indexing
- Loops allow efficient processing of arrays
- Games use arrays for objects and game state
- Arrays simplify rendering systems
- `.push()` adds elements
- `.pop()` removes elements
- Arrays improve scalability and organization
- AstroPlatformer uses arrays to manage platforms and overlays

Arrays are one of the most fundamental and powerful tools in programming and game development.

<div style="display:flex;gap:10px;flex-wrap:wrap;">
  <a href="{{site.baseurl}}/table" style="text-decoration:none;"><div style="background-color:#f59e0b;color:#111;padding:10px 18px;border-radius:8px;font-weight:bold;">Back to Table</div></a>
  <a href="{{site.baseurl}}/astro-platgame-lesson/" style="text-decoration:none;"><div style="background-color:#3b82f6;color:white;padding:10px 18px;border-radius:8px;font-weight:bold;">Open AstroPlatformer Demo</div></a>
  <a href="{{site.baseurl}}/arrays-lesson" style="text-decoration:none;"><div style="background-color:#10b981;color:white;padding:10px 18px;border-radius:8px;font-weight:bold;">Open Lesson Notebook</div></a>
</div>