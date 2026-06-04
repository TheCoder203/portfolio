---
layout: post
title: Conditionals
permalink: /conditionals
---

# Conditionals

### Overview
Conditionals are one of the most important concepts in programming because they allow programs to make decisions.

A conditional statement checks whether a condition is true or false and then chooses what code should execute.

Without conditionals, programs would always follow the exact same sequence of instructions and would not be able to react dynamically to user input, gameplay events, or changing data.

In game development, conditionals are used constantly to control behavior such as:

- Player movement - Collision detection - Enemy AI - Health systems - Item collection - Game over states - Animation triggers - Level progression

In AstroPlatformer, conditionals help the game decide how objects should behave based on the current game state.

---

### What Are Conditionals?

A conditional is a programming structure that runs code only if a condition is met.

The most common conditional statement in JavaScript is the `if` statement.

Example:

```javascript
if (score > 100) {
  console.log('High score reached!');
}
```

If the condition is true, the code inside the block executes.

If the condition is false, the code is skipped.

---

### Boolean Logic in Conditionals

Conditionals rely on boolean values:

```javascript

true
```

or

```javascript
false
```

Example:

```javascript
const playerAlive = true;

if (playerAlive) {
  updatePlayer();
}
```

The game only updates the player if the condition is true.

---

### Why Conditionals Matter in Games

Games constantly react to changing situations.

Conditionals allow the game to answer questions such as:

- Is the player alive? - Did the player collect the coin? - Is the enemy nearby? - Is the game paused? - Has the level been completed? - Is the object visible?

Without conditionals, games would not be interactive.

---

### AstroPlatformer Example

The following code comes directly from AstroPlatformer:

```javascript

if (this.collected) return;

if (this.canvas) { this.canvas.style.opacity = '0'; this.canvas.style.transition = 'opacity 0.3s'; setTimeout(() => this.canvas?.remove(), 350); }
```

These conditionals control how collected coins behave.

The code checks:

1. Whether the coin has already been collected 2.

Whether the coin's visual element exists

Depending on the results, the game performs different actions.

---

### Breaking Down the First Conditional

```javascript
if (this.collected) return;
```

This checks whether the coin was already collected.

If:

```javascript
this.collected === true
```

then the function exits immediately.

This prevents:

- Duplicate collection - Multiple score increases - Repeated animations - Extra processing

Conditionals help maintain stable game logic.

---

### Breaking Down the Second Conditional

```javascript

if (this.canvas)
```

This checks whether the coin's visual element exists before modifying it.

Without this check, the game could attempt to access an undefined object and cause errors.

This is an example of defensive programming.

---

### Dynamic Visual Effects

Inside the conditional:

```javascript
this.canvas.style.opacity = '0';
```

The game fades out the coin visually.

Then:

```javascript
this.canvas.style.transition = 'opacity 0.3s';
```

creates a smooth animation effect.

Finally:

```javascript

setTimeout(() => this.canvas?.remove(), 350);
```

removes the coin after the animation finishes.

The conditionals control whether these visual updates should occur.

---

### Basic `if` Statements

The simplest conditional structure is:

```javascript
if (condition) {

}
```

Example:

```javascript
if (playerHealth <= 0) {
  gameOver();
}
```

The game only ends if the condition is true.

---

### `if...else` Statements

Programs often need multiple possible outcomes.

Example:

```javascript

if (playerAlive) { updatePlayer(); } else { showGameOverScreen(); }
```

If the player is alive, gameplay continues.

Otherwise, the game over screen appears.

---

### `else if` Statements

Programs can also check several conditions.

Example:

```javascript
if (score >= 1000) {
  rank = 'Gold';
} else if (score >= 500) {
  rank = 'Silver';
} else {
  rank = 'Bronze';
}
```

This allows more advanced decision-making.

---

### Comparison Operators

Conditionals commonly use comparison operators.

| Operator | Meaning | |---|---| | `===` | Equal to | | `!==` | Not equal to | | `>` | Greater than | | `<` | Less than | | `>=` | Greater than or equal | | `<=` | Less than or equal |

Example:

```javascript
if (coins >= 10) {
  unlockDoor();
}
```

---

### Logical Operators

Conditionals can combine multiple conditions.

| Operator | Meaning | |---|---| | `&&` | AND | | `||` | OR | | `!` | NOT |

Example:

```javascript

if (playerAlive && hasKey) { openDoor(); }
```

Both conditions must be true.

---

### Conditionals in Collision Detection

Collision systems heavily rely on conditionals.

Example:

```javascript
if (player.x < enemy.x + enemy.width &&
    player.x + player.width > enemy.x) {
  damagePlayer();
}
```

The conditional checks whether objects overlap.

---

### Conditionals in Enemy AI

Enemy behavior also uses conditionals.

Example:

```javascript
if (distanceToPlayer < 200) {
  enemy.attack();
}
```

The enemy only attacks when the player is close enough.

---

### Nested Conditionals

Conditionals can exist inside other conditionals.

Example:

```javascript

if (playerAlive) { if (hasWeapon) { attack(); } }
```

This creates more advanced game logic.

---

### Ternary Operators

JavaScript also supports shorthand conditionals.

Example:

```javascript
const state = playerAlive ? 'Alive' : 'Dead';
```

This is a compact version of:

```javascript
if (playerAlive) {
  state = 'Alive';
} else {
  state = 'Dead';
}
```

---

### Defensive Programming

Conditionals are extremely important for defensive programming.

Example:

```javascript

if (player && player.inventory) { console.log(player.inventory); }
```

This prevents errors caused by missing objects.

AstroPlatformer uses similar conditional checks to safely manage game systems.

---

### Real-World Uses of Conditionals

Conditionals appear throughout modern software.

Examples include:

| System | Conditional Logic | |---|---| | Games | Is player alive? | | Websites | Is user logged in?

| | Apps | Is internet connected? | | Banking Software | Is payment valid?

| | Security Systems | Is access authorized? | | Navigation Apps | Has destination been reached?

|

Conditionals are one of the foundations of programming logic.

---

### Why Conditionals Matter in AstroPlatformer

AstroPlatformer uses conditionals throughout the game engine to control:

- Coin collection - Collision handling - Rendering updates - Physics systems - Enemy behaviors - UI animations - Object removal - Level progression

The conditionals help the game:

- Respond dynamically to player actions - Prevent errors - Control gameplay flow - Improve stability - Create interactive experiences

Without conditionals, the game could not react intelligently to changing situations.

---

### Key Takeaways

- Conditionals allow programs to make decisions - `if` statements execute code when conditions are true - Games rely heavily on conditional logic - `if...else` handles multiple outcomes - Logical operators combine conditions - Conditionals help prevent errors - Collision systems and AI use conditionals constantly - AstroPlatformer uses conditionals to manage coin behavior and animations

Conditionals are one of the most essential building blocks of programming, interactivity, and game development.

---
### Quick Example

```javascript
if (player.x > flag.x - 10) {
  if (player.y > flag.y - 10) {
    winLevel();
  }
}
```

<div style="display:flex;gap:10px;flex-wrap:wrap;"> <a href="{{site.baseurl}}/table" style="text-decoration:none;"><div style="background-color:#f59e0b;color:#111;padding:10px 18px;border-radius:8px;font-weight:bold;">Back to Table</div></a> <a href="{{site.baseurl}}/astro-platgame-lesson/" style="text-decoration:none;"><div style="background-color:#3b82f6;color:white;padding:10px 18px;border-radius:8px;font-weight:bold;">Open AstroPlatformer Demo</div></a> <a href="{{site.baseurl}}/conditionals-lesson" style="text-decoration:none;"><div style="background-color:#10b981;color:white;padding:10px 18px;border-radius:8px;font-weight:bold;">Open Lesson Notebook</div></a> </div>

## Summary

Describes how conditional statements and boolean logic drive decision-making in games, with examples for collision, AI, and defensive checks.
