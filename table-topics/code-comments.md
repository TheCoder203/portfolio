---
layout: post
title: Code Comments
permalink: /code-comments
---

# Code Comments

Code comments are notes written inside source code to help explain what the program is doing and why certain decisions were made. Comments are ignored by the computer during execution, but they are extremely important for developers because they improve readability, organization, and maintainability.

In software engineering, developers often work on large codebases containing thousands or even millions of lines of code. Without comments, understanding complicated systems becomes much more difficult.

In AstroPlatformer, comments help explain platformer physics, collision handling, update order, and gameplay systems. These comments make the game easier to understand for both current and future developers.

---

### What Are Code Comments?

A comment is text inside a program that is meant for humans rather than the computer.

In JavaScript, single-line comments use:

```javascript
// This is a comment
```

Multi-line comments use:

```javascript
/*
This is a
multi-line comment
*/
```

The JavaScript engine ignores comments completely during execution.

---

### Why Comments Matter

Comments help developers:

- Understand complicated systems
- Explain difficult algorithms
- Document important logic
- Describe why code exists
- Improve teamwork
- Debug problems more easily
- Maintain large projects

Good comments make software much easier to work with.

---

### Example of Poor Readability

Without comments:

```javascript
player.vy += gravity;

if (player.y + player.height > platform.y) {
  player.y = platform.y - player.height;
  player.vy = 0;
}
```

A new developer may not immediately understand the purpose of the logic.

---

### Example with Comments

```javascript
// Apply gravity to the player's vertical velocity
player.vy += gravity;

// Prevent the player from falling through the platform
if (player.y + player.height > platform.y) {
  player.y = platform.y - player.height;
  player.vy = 0;
}
```

Now the purpose of the code is much clearer.

---

### AstroPlatformer Example

The following comments come directly from AstroPlatformer:

```javascript
//  5. PLATFORM COLLISION — for every platform (including moving one):
//       TOP: player's bottom swept from above-to-below the platform top
//       ...
//  7. SPIKE DEATH — checked using the player's resolved (post-collision) feet position
```

These comments explain the order and reasoning behind the collision system.

Instead of forcing developers to reverse-engineer the logic, the comments clearly describe how the system works.

---

### Explaining Collision Systems

Collision systems are often complicated because they involve:

- Physics calculations
- Position updates
- Timing rules
- Edge cases
- Multiple object interactions

Comments help explain:

- Why collisions are checked in a specific order
- How movement is resolved
- Why certain calculations exist
- How bugs are prevented

In platformer games, update order is extremely important.

---

### Why Update Order Matters

Platformer physics often require operations to happen in a very specific sequence.

For example:

1. Apply gravity
2. Update movement
3. Check collisions
4. Resolve overlaps
5. Update animations
6. Detect hazards

Changing the order can cause bugs such as:

- Falling through platforms
- Double jumps
- Incorrect collisions
- Teleportation glitches

Comments help developers understand why the order matters.

---

### Self-Documenting Code

Good code should already be somewhat readable without comments.

Example:

```javascript
const playerBottom = player.y + player.height;
```

This variable name already explains its purpose.

This is called self-documenting code.

However, comments are still important for explaining:

- Complex logic
- Design decisions
- Unusual behavior
- Performance optimizations

---

### Commenting Complex Logic

Some systems are too complicated to explain with variable names alone.

Example:

```javascript
// Sweep collision detection prevents fast-moving objects
// from tunneling through thin platforms between frames
```

This explains the reasoning behind the algorithm.

Without the comment, the code might appear unnecessarily complicated.

---

### Types of Comments

There are several common types of comments.

---

### 1. Explanatory Comments

Explain what code is doing.

Example:

```javascript
// Spawn enemy at random position
spawnEnemy();
```

---

### 2. Warning Comments

Warn developers about important issues.

Example:

```javascript
// Do not remove this delay — prevents physics instability
```

---

### 3. TODO Comments

Indicate unfinished work.

Example:

```javascript
// TODO: Add multiplayer synchronization
```

---

### 4. Documentation Comments

Describe functions or classes.

Example:

```javascript
/**
 * Updates the player's movement and collision state
 */
function updatePlayer() {

}
```

---

### Comments and Teamwork

Comments are especially important in team projects.

Without comments:

- New developers may struggle to understand systems
- Bugs become harder to fix
- Features become harder to expand
- Collaboration slows down

Good comments improve communication between developers.

---

### Comments in Game Development

Game engines often contain complicated systems such as:

- Physics
- Collision detection
- AI behavior
- Animation systems
- Rendering pipelines
- Networking systems

Comments help explain these systems clearly.

Example:

```javascript
// Only allow jumping if grounded
if (player.grounded) {
  jump();
}
```

This makes gameplay rules easier to understand.

---

### Overcommenting vs Undercommenting

Too few comments can make code confusing.

Too many comments can clutter the code.

Bad example:

```javascript
// Add 1 to x
x = x + 1;
```

This comment is unnecessary because the code is already obvious.

Good comments explain things that are not immediately clear.

---

### Comments and Debugging

Comments also help with debugging.

Example:

```javascript
// Collision bug occurs if velocity exceeds platform width
```

This helps developers quickly locate known issues.

Comments often preserve important knowledge about past bugs.

---

### Comments and Maintenance

Software projects may last for many years.

Future developers may not remember:

- Why a system was designed a certain way
- What edge cases were solved
- Why a workaround exists

Comments preserve this information.

This is extremely important for long-term maintenance.

---

### Real-World Uses of Code Comments

Comments are used in nearly every professional software project.

Examples include:

| System | Purpose of Comments |
|---|---|
| Games | Explain physics and AI |
| APIs | Document endpoints |
| Websites | Describe UI behavior |
| Operating Systems | Explain low-level logic |
| Databases | Document queries |
| Security Software | Explain protections |

Comments are a major part of professional software engineering.

---

### Why Code Comments Matter in AstroPlatformer

AstroPlatformer uses comments to explain systems such as:

- Platform collisions
- Spike detection
- Physics ordering
- Rendering logic
- Update loops
- Gameplay rules

These comments help developers:

- Understand the game engine faster
- Debug issues more easily
- Modify systems safely
- Expand gameplay features
- Maintain code quality

The comments turn complicated game logic into understandable documentation.

---

### Key Takeaways

- Code comments explain source code for humans
- Comments improve readability and maintainability
- JavaScript uses `//` and `/* */` for comments
- Comments help explain complex systems
- Good comments describe why code exists
- Comments improve teamwork and debugging
- Platformer physics often require detailed explanations
- AstroPlatformer uses comments to document collision flow and update order

Code comments are an essential part of professional software engineering and game development.

<div style="display:flex;gap:10px;flex-wrap:wrap;">
  <a href="{{site.baseurl}}/table" style="text-decoration:none;"><div style="background-color:#f59e0b;color:#111;padding:10px 18px;border-radius:8px;font-weight:bold;">Back to Table</div></a>
  <a href="{{site.baseurl}}/astro-platgame-lesson/" style="text-decoration:none;"><div style="background-color:#3b82f6;color:white;padding:10px 18px;border-radius:8px;font-weight:bold;">Open AstroPlatformer Demo</div></a>
  <a href="{{site.baseurl}}/code-comments-lesson" style="text-decoration:none;"><div style="background-color:#10b981;color:white;padding:10px 18px;border-radius:8px;font-weight:bold;">Open Lesson Notebook</div></a>
</div>