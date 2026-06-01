---
layout: post
title: Canvas Rendering
permalink: /canvas-rendering
---

# Canvas Rendering

Rendering is the process of drawing visual elements onto the screen so users can see and interact with them. In game development, rendering systems are responsible for displaying:

- Players
- Platforms
- Backgrounds
- Animations
- UI elements
- Effects
- Enemies
- Objects

One common rendering method in web development is the HTML Canvas API, which allows developers to draw graphics dynamically using JavaScript. However, games can also render visuals using DOM elements and CSS styling instead of direct canvas drawing.

In AstroPlatformer, the game dynamically creates visual objects using HTML elements and CSS styles. Although this is DOM-based rendering rather than direct canvas rendering, the overall concept is very similar because the game is still generating and positioning graphics programmatically at runtime.

---

### What is Rendering?

Rendering means converting game data into visible graphics on the screen.

For example:

- A player's position becomes a visible sprite
- A platform object becomes a visual rectangle
- A coin object becomes an animated collectible
- UI data becomes a health bar or score display

Without rendering systems, the game world would exist only as invisible data.

---

### What is the HTML Canvas?

The HTML `<canvas>` element allows JavaScript to draw graphics dynamically.

Example:

```html
<canvas id="gameCanvas" width="800" height="600"></canvas>
```

JavaScript can then render graphics onto the canvas.

Example:

```javascript
const canvas = document.getElementById('gameCanvas');
const ctx = canvas.getContext('2d');

ctx.fillStyle = 'blue';
ctx.fillRect(100, 100, 200, 50);
```

This draws a blue rectangle onto the screen.

Canvas rendering is commonly used in:

- 2D games
- Particle systems
- Physics simulations
- Data visualizations
- Interactive graphics

---

### DOM Rendering vs Canvas Rendering

AstroPlatformer primarily uses DOM rendering instead of direct canvas drawing.

DOM rendering means:

- Creating HTML elements
- Styling them with CSS
- Positioning them dynamically

Canvas rendering means:

- Drawing pixels directly onto a graphics surface

Both systems achieve similar goals: displaying game visuals dynamically.

---

### AstroPlatformer Example

The following code comes directly from AstroPlatformer:

```javascript
const banner = document.createElement('div');

Object.assign(banner.style, {
    position:'absolute',
    left: (this._flagX + 3*scaleX)+'px',
    top:  (top + this._flagY)+'px',
    width:(24*scaleX)+'px',
    height:(16*scaleY)+'px',
    background:'#00ff88',
    ...
});
```

This code dynamically creates a visual banner object during gameplay.

The game:

1. Creates a new HTML element
2. Applies visual styling
3. Positions it on screen
4. Attaches it to the game world

This is a rendering process similar to how canvas systems draw graphics dynamically.

---

### Creating Elements Dynamically

The first step creates a new visual object:

```javascript
const banner = document.createElement('div');
```

This generates a new HTML element entirely through JavaScript.

The element does not exist in the original HTML file.

Games often create objects dynamically because:

- Levels change constantly
- Objects appear and disappear
- Players interact with the world
- Effects spawn during gameplay

Dynamic rendering is essential for interactive applications.

---

### Styling Rendered Objects

The game uses CSS styles to control appearance.

Example:

```javascript
background:'#00ff88'
```

This sets the background color.

Other properties include:

- Position
- Width
- Height
- Rotation
- Opacity
- Borders
- Shadows

CSS styling acts similarly to graphics settings in canvas rendering.

---

### Positioning Objects

The game positions objects using coordinates.

Example:

```javascript
left: (this._flagX + 3*scaleX)+'px'
```

and

```javascript
top: (top + this._flagY)+'px'
```

These coordinates determine where the object appears on the screen.

Position-based rendering is fundamental to all game engines.

---

### Scaling Objects

The code also uses scaling variables:

```javascript
width:(24*scaleX)+'px'
```

and

```javascript
height:(16*scaleY)+'px'
```

Scaling allows graphics to resize dynamically.

Games use scaling for:

- Responsive layouts
- Resolution support
- Zoom systems
- Animation effects
- Pixel art scaling

---

### Rendering Loops

Most games continuously update visuals using rendering loops.

Example:

```javascript
function gameLoop() {
  update();
  render();

  requestAnimationFrame(gameLoop);
}

gameLoop();
```

The rendering system redraws the screen many times per second.

This creates smooth animations and gameplay.

---

### Canvas Drawing Example

Example using direct canvas rendering:

```javascript
ctx.fillStyle = 'red';
ctx.fillRect(player.x, player.y, 50, 50);
```

This draws a player rectangle onto the canvas.

Canvas rendering is often faster for large numbers of moving objects.

---

### DOM Rendering Example

Equivalent DOM rendering:

```javascript
player.style.left = player.x + 'px';
player.style.top = player.y + 'px';
```

Instead of drawing pixels directly, the game moves HTML elements.

AstroPlatformer primarily uses this approach.

---

### Advantages of DOM Rendering

DOM rendering offers several advantages:

- Easier styling with CSS
- Simpler UI integration
- Better accessibility
- Easier debugging
- Native HTML support

For smaller web games, DOM rendering can be very effective.

---

### Advantages of Canvas Rendering

Canvas rendering also has advantages:

- Faster large-scale rendering
- Better particle systems
- Efficient sprite drawing
- Lower DOM overhead
- Smoother complex animations

Many professional games use canvas or WebGL for performance reasons.

---

### Rendering Game Entities

Rendering systems display many types of game entities.

Examples include:

| Entity Type | Rendered Visual |
|---|---|
| Player | Character sprite |
| Platform | Terrain block |
| Coin | Collectible item |
| Enemy | NPC sprite |
| UI | Health bar |
| Effects | Particles or animations |

Every visible object in the game must be rendered somehow.

---

### Runtime Rendering

AstroPlatformer renders objects at runtime.

This means visuals are generated dynamically while the game is running.

Benefits include:

- Flexible level design
- Dynamic gameplay
- Procedural generation
- Real-time effects
- Interactive systems

Runtime rendering is essential for modern games.

---

### Rendering and Game Engines

Game engines coordinate rendering systems alongside:

- Physics systems
- Input handling
- Audio systems
- AI systems
- Collision detection

The rendering engine is responsible for turning game data into visible graphics.

---

### Real-World Uses of Rendering Systems

Rendering systems appear throughout modern software.

Examples include:

| Application | Rendering Type |
|---|---|
| Video Games | 2D/3D rendering |
| Websites | DOM rendering |
| Design Software | Vector rendering |
| Simulations | Real-time graphics |
| Mobile Apps | UI rendering |
| Data Visualization | Dynamic chart rendering |

Rendering technology powers nearly all modern graphical applications.

---

### Why Canvas Rendering Concepts Matter in AstroPlatformer

AstroPlatformer uses dynamic rendering systems to generate:

- Platforms
- Flags
- Coins
- UI overlays
- Environmental objects
- Effects

The rendering architecture allows the game to:

- Build visuals from code
- Position objects dynamically
- Scale graphics responsively
- Update visuals in real time
- Create interactive gameplay systems

Even though AstroPlatformer primarily uses DOM rendering, the core rendering principles are very similar to canvas-based game engines.

---

### Key Takeaways

- Rendering displays visual objects on screen
- Canvas rendering draws graphics dynamically
- DOM rendering uses HTML and CSS elements
- AstroPlatformer dynamically creates visual objects
- Positioning controls where objects appear
- Scaling changes object size
- Rendering loops update visuals continuously
- Rendering systems are essential for games
- AstroPlatformer uses runtime rendering for dynamic gameplay

Rendering systems are one of the core technologies behind interactive games, graphics engines, and modern web applications.

---
### Quick Example

```javascript
console.log('Quick example for Canvas Rendering');
```

<div style="display:flex;gap:10px;flex-wrap:wrap;">
  <a href="{{site.baseurl}}/table" style="text-decoration:none;"><div style="background-color:#f59e0b;color:#111;padding:10px 18px;border-radius:8px;font-weight:bold;">Back to Table</div></a>
  <a href="{{site.baseurl}}/astro-platgame-lesson/" style="text-decoration:none;"><div style="background-color:#3b82f6;color:white;padding:10px 18px;border-radius:8px;font-weight:bold;">Open AstroPlatformer Demo</div></a>
  <a href="{{site.baseurl}}/canvas-rendering-lesson" style="text-decoration:none;"><div style="background-color:#10b981;color:white;padding:10px 18px;border-radius:8px;font-weight:bold;">Open Lesson Notebook</div></a>
</div>
