---
layout: post
title: Boolean Expressions
permalink: /boolean-expressions
---

# Boolean Expressions

Boolean expressions are logical statements that evaluate to either `true` or `false`. They are one of the most fundamental concepts in computer science because they allow programs to make decisions and control behavior dynamically.

In programming, boolean expressions are used everywhere, including:

- Conditional statements
- Game logic
- Collision detection
- User authentication
- AI behavior
- Input validation
- Loops
- Error checking

In AstroPlatformer, boolean expressions help determine whether systems are available and whether certain actions should occur. The game uses logical checks to safely control gameplay systems and avoid runtime errors.

---

### What is a Boolean?

A boolean is a data type that can only have two values:

```javascript
true
false
```

Examples:

```javascript
const gameRunning = true;
const playerDead = false;
```

Booleans are commonly used to represent states or conditions inside a program.

---

### What is a Boolean Expression?

A boolean expression is any expression that evaluates to either `true` or `false`.

Example:

```javascript
5 > 3
```

This evaluates to:

```javascript
true
```

Another example:

```javascript
10 === 20
```

This evaluates to:

```javascript
false
```

Programs use these expressions to decide what code should run.

---

### Comparison Operators

Boolean expressions often use comparison operators.

Common operators include:

| Operator | Meaning |
|---|---|
| `===` | Equal to |
| `!==` | Not equal to |
| `>` | Greater than |
| `<` | Less than |
| `>=` | Greater than or equal |
| `<=` | Less than or equal |

Examples:

```javascript
score > 100
```

```javascript
lives === 0
```

```javascript
playerHealth <= 0
```

Each expression evaluates to either `true` or `false`.

---

### Conditional Statements

Boolean expressions are commonly used with `if` statements.

Example:

```javascript
const score = 150;

if (score > 100) {
  console.log('High score reached!');
}
```

The code inside the block only runs if the boolean expression is true.

---

### Logical Operators

Programs often combine multiple boolean expressions together.

Common logical operators include:

| Operator | Meaning |
|---|---|
| `&&` | AND |
| `||` | OR |
| `!` | NOT |

---

### Using `&&` (AND)

The `&&` operator requires both conditions to be true.

Example:

```javascript
if (playerAlive && levelComplete) {
  console.log('Advance to next level');
}
```

Both conditions must be true for the code to execute.

---

### Using `||` (OR)

The `||` operator requires only one condition to be true.

Example:

```javascript
if (hasKey || doorUnlocked) {
  console.log('Door can open');
}
```

Only one condition needs to be true.

---

### Using `!` (NOT)

The `!` operator reverses a boolean value.

Example:

```javascript
const paused = false;

if (!paused) {
  console.log('Game is running');
}
```

Because `paused` is false, `!paused` becomes true.

---

### AstroPlatformer Example

The following code comes directly from AstroPlatformer:

```javascript
if (sm && typeof sm.updateScoreDisplay === 'function') {
    sm.updateScoreDisplay(gameEnv.stats.coinsCollected);
}
```

This snippet uses a boolean expression to safely verify that the score manager exists before updating the display.

This prevents errors if the score manager has not initialized properly.

---

### Breaking Down the Expression

The expression contains two separate conditions:

```javascript
sm
```

and

```javascript
typeof sm.updateScoreDisplay === 'function'
```

These are combined using the `&&` operator.

---

### Condition 1: Checking if `sm` Exists

```javascript
sm
```

This checks whether the score manager object exists.

If `sm` is:

- `null`
- `undefined`
- `false`

then the condition fails.

This protects the program from accessing missing objects.

---

### Condition 2: Checking the Function Type

```javascript
typeof sm.updateScoreDisplay === 'function'
```

This verifies that `updateScoreDisplay` is actually a function before calling it.

Without this check, the program could throw an error such as:

```javascript
TypeError: sm.updateScoreDisplay is not a function
```

This is an example of defensive programming.

---

### Why Boolean Expressions Matter in Games

Games constantly evaluate conditions using boolean logic.

Examples include:

- Is the player alive?
- Has the level been completed?
- Is the enemy nearby?
- Did the player collect the item?
- Is the game paused?
- Has the timer expired?

Without boolean expressions, games could not react dynamically to player actions.

---

### Collision Detection Example

Boolean expressions are heavily used in collision systems.

Example:

```javascript
if (player.x < enemy.x + enemy.width &&
    player.x + player.width > enemy.x) {
  console.log('Collision detected');
}
```

This determines whether two objects overlap.

Collision systems are built almost entirely from boolean logic.

---

### Boolean Variables

Programs often store conditions inside variables.

Example:

```javascript
const playerDead = health <= 0;

if (playerDead) {
  endGame();
}
```

This improves readability and organization.

---

### Truthy and Falsy Values

JavaScript also supports truthy and falsy values.

Falsy values include:

- `false`
- `0`
- `null`
- `undefined`
- `''`
- `NaN`

Everything else is generally considered truthy.

Example:

```javascript
if (username) {
  console.log('Username exists');
}
```

This checks whether `username` contains a value.

---

### Nested Boolean Logic

Programs can combine many boolean expressions together.

Example:

```javascript
if (playerAlive && hasWeapon && ammo > 0) {
  shoot();
}
```

This creates more advanced game logic.

---

### Boolean Expressions in Loops

Loops also use boolean expressions.

Example:

```javascript
while (health > 0) {
  updateGame();
}
```

The loop continues while the condition remains true.

---

### Defensive Programming

Boolean expressions are extremely important for defensive programming.

Defensive programming means writing code that safely handles unexpected situations.

Example:

```javascript
if (player && player.inventory) {
  console.log(player.inventory);
}
```

This prevents errors caused by missing objects.

AstroPlatformer uses similar boolean checks to safely handle game systems.

---

### Real-World Uses of Boolean Logic

Boolean expressions appear throughout modern software.

Examples include:

| System | Boolean Check |
|---|---|
| Login Systems | Is password correct? |
| Games | Is player alive? |
| Websites | Is user authenticated? |
| APIs | Was request successful? |
| AI Systems | Is target visible? |
| Navigation Apps | Has destination been reached? |

Boolean logic is one of the foundations of programming.

---

### Why Boolean Expressions Matter in AstroPlatformer

AstroPlatformer uses boolean expressions to safely manage systems such as:

- Score managers
- Leaderboards
- Player states
- Collision systems
- Game events
- Rendering logic
- Level progression

The boolean checks help the game:

- Prevent crashes
- Verify objects exist
- Control gameplay flow
- Handle missing systems safely
- Improve overall stability

Without boolean logic, the game would not be able to make intelligent decisions dynamically.

---

### Key Takeaways

- Boolean expressions evaluate to `true` or `false`
- Boolean logic controls program decisions
- Comparison operators create conditions
- Logical operators combine conditions
- `&&` means AND
- `||` means OR
- `!` means NOT
- Boolean expressions are essential for games
- AstroPlatformer uses boolean checks for safe system handling

Boolean expressions are one of the most important building blocks of programming and game development.

<div style="display:flex;gap:10px;flex-wrap:wrap;">
  <a href="{{site.baseurl}}/table" style="text-decoration:none;"><div style="background-color:#f59e0b;color:#111;padding:10px 18px;border-radius:8px;font-weight:bold;">Back to Table</div></a>
  <a href="{{site.baseurl}}/astro-platgame-lesson/" style="text-decoration:none;"><div style="background-color:#3b82f6;color:white;padding:10px 18px;border-radius:8px;font-weight:bold;">Open AstroPlatformer Demo</div></a>
  <a href="{{site.baseurl}}/boolean-expressions-lesson" style="text-decoration:none;"><div style="background-color:#10b981;color:white;padding:10px 18px;border-radius:8px;font-weight:bold;">Open Lesson Notebook</div></a>
</div>