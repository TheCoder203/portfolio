---
layout: post
title: Booleans
permalink: /booleans
---

# Booleans

### Overview
Booleans are one of the most fundamental data types in programming.

A boolean represents a value that can only be one of two possibilities:

```javascript
true
```

or

```javascript

false
```

Although booleans are simple, they are incredibly powerful because they allow programs to track states, make decisions, and control behavior dynamically.

In game development, booleans are used constantly to manage gameplay systems and object states. Games rely on booleans to determine things such as:

- Whether a player is alive - Whether a coin was collected - Whether a door is unlocked - Whether the game is paused - Whether an enemy is active - Whether a level is completed - Whether the player is touching the ground

In AstroPlatformer, booleans help keep the game logic stable, predictable, and efficient.

---

### What is a Boolean?

A boolean stores either:

```javascript
true
```

or

```javascript
false
```

Example:

```javascript

const gameOver = false; const playerAlive = true;
```

These values represent conditions or states inside a program.

---

### Why Booleans Matter

Booleans allow programs to make decisions.

Example:

```javascript
const playerDead = true;

if (playerDead) {
  console.log('Game Over');
}
```

The game checks the boolean value to decide whether to display the game over screen.

Without booleans, programs could not easily control logic or behavior.

---

### Booleans in Games

Games constantly track many states at once.

Examples include:

| Boolean Variable | Meaning | |---|---| | `playerAlive` | Is the player alive? | | `gamePaused` | Is the game paused?

| | `coinCollected` | Was the coin collected? | | `doorUnlocked` | Can the player open the door?

| | `enemyDefeated` | Has the enemy been defeated? |

These states allow the game to react dynamically to gameplay events.

---

### AstroPlatformer Example

The following code comes directly from AstroPlatformer:

```javascript
if (this.collected) return;

if (!this.collected) {
    this.collected = true;
    ...
}
```

This snippet uses booleans to control coin collection behavior.

The `collected` variable tracks whether the coin has already been picked up.

This prevents the game from processing the same coin multiple times.

---

### Breaking Down the First Condition

```javascript

if (this.collected) return;
```

This checks whether the coin has already been collected.

If `this.collected` is true:

- The function exits immediately - No additional processing occurs - The coin cannot be collected again

This improves stability and prevents duplicate rewards.

---

### Using `!` (NOT)

The second condition uses the `!` operator:

```javascript
if (!this.collected)
```

The `!` symbol means NOT.

If:

```javascript
this.collected === false
```

then:

```javascript

!this.collected === true
```

This allows the game to detect coins that have not yet been collected.

---

### Updating the Boolean Value

```javascript
this.collected = true;
```

Once the coin is collected, the boolean value changes permanently.

This state update ensures:

- The coin disappears - The score updates only once - Duplicate collection is impossible

State tracking is one of the main uses of booleans in games.

---

### Boolean Variables

Programs often store states inside boolean variables.

Example:

```javascript
const jumping = true;
const grounded = false;
```

These values help the game engine determine what actions are allowed.

For example:

```javascript

if (grounded) { jump(); }
```

The player can only jump when grounded is true.

---

### Booleans and Conditional Statements

Booleans are commonly used with `if` statements.

Example:

```javascript
const shieldActive = true;

if (shieldActive) {
  reduceDamage();
}
```

The code only runs when the boolean condition is true.

---

### Boolean Expressions

Boolean values are often created using comparisons.

Example:

```javascript
const lowHealth = playerHealth < 20;
```

If the player's health is below 20:

```javascript

lowHealth === true
```

Otherwise:

```javascript
lowHealth === false
```

This creates dynamic game logic.

---

### Toggling Boolean Values

Booleans can also switch between true and false.

Example:

```javascript
let paused = false;

paused = !paused;
```

If `paused` was false, it becomes true.

If it was true, it becomes false.

This is commonly used for:

- Pause menus - Toggle switches - Visibility systems - Game settings

---

### Booleans in Collision Systems

Collision systems rely heavily on booleans.

Example:

```javascript

const touchingGround = player.y >= platform.y;

if (touchingGround) { player.canJump = true; }
```

The boolean determines whether the player is standing on a platform.

---

### Booleans in AI Systems

Enemy AI also uses booleans.

Example:

```javascript
const playerDetected = distance < 200;

if (playerDetected) {
  enemy.attack();
}
```

The boolean determines whether the enemy should attack.

---

### Boolean Flags

Boolean variables are often called flags because they indicate whether something is active or inactive.

Examples:

```javascript
isRunning
hasKey
gameStarted
musicEnabled
```

Flags help organize game state cleanly.

---

### Avoiding Duplicate Actions

One major use of booleans is preventing repeated actions.

Example:

```javascript

if (buttonPressed) return;

buttonPressed = true;
```

This pattern prevents:

- Duplicate API requests - Multiple button presses - Repeated rewards - Double processing

AstroPlatformer uses this exact idea for coin collection.

---

### Truthy and Falsy Values

JavaScript also supports truthy and falsy values.

Falsy values include:

- `false` - `0` - `null` - `undefined` - `''` - `NaN`

Everything else is generally truthy.

Example:

```javascript
if (username) {
  console.log('User exists');
}
```

This checks whether `username` contains a value.

---

### Real-World Uses of Booleans

Booleans appear in nearly every application.

Examples include:

| System | Boolean State | |---|---| | Video Games | Is player alive? | | Websites | Is user logged in?

| | Phones | Is Wi-Fi enabled? | | Streaming Apps | Is video paused?

| | Security Systems | Is access granted? | | Smart Devices | Is the device connected?

|

Boolean logic is one of the foundations of computer science.

---

### Why Booleans Matter in AstroPlatformer

AstroPlatformer uses booleans throughout the game engine to manage:

- Coin collection - Player movement - Collision detection - Level completion - Game states - Menu systems - Enemy behaviors

The boolean-based architecture helps:

- Prevent duplicate actions - Simplify game logic - Improve predictability - Reduce bugs - Keep gameplay stable

Without booleans, the game would struggle to track object states efficiently.

---

### Key Takeaways

- Booleans store either `true` or `false` - Booleans represent states and conditions - Games rely heavily on boolean logic - `if` statements use booleans for decisions - `!` means NOT - Booleans help prevent duplicate actions - Boolean flags track game states - AstroPlatformer uses booleans for stable coin collection logic

Booleans are one of the most essential building blocks of programming and interactive game systems.

---
### Quick Example

```javascript
if (player.health <= 0) {
  endGame();
}
```

<div style="display:flex;gap:10px;flex-wrap:wrap;">
  <a href="{{site.baseurl}}/table" style="text-decoration:none;"><div style="background-color:#f59e0b;color:#111;padding:10px 18px;border-radius:8px;font-weight:bold;">Back to Table</div></a>
  <a href="{{site.baseurl}}/astro-platgame-lesson/" style="text-decoration:none;"><div style="background-color:#3b82f6;color:white;padding:10px 18px;border-radius:8px;font-weight:bold;">Open AstroPlatformer Demo</div></a>
  <a href="{{site.baseurl}}/booleans-lesson" style="text-decoration:none;"><div style="background-color:#10b981;color:white;padding:10px 18px;border-radius:8px;font-weight:bold;">Open Lesson Notebook</div></a>
</div>

## Summary

Summarizes how boolean flags represent simple true/false states that control gameplay flow, prevent duplicate actions, and enable defensive checks.
