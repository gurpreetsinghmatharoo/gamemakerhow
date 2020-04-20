---
title: How to use surfaces?
permalink: /how-to-use-surfaces/
categories: [Surfaces]
tags: [surface, surfaces, draw, canvas, clip, clipping]
similar:
    -   permalink: /how-to-draw-paused-game/
        title: How to draw a paused game?
---

A Surface is a rectangular canvas where something can be drawn. Everything in that surface will **not** be drawn to the screen until you draw it yourself.

Creating a surface is simple:
```js
surface = surface_create(width, height);
```

To draw something to that surface, you need to **set the draw target to that surface**:
```js
surface_set_target(surface);

// Draw in the surface
draw_circle(60, 60, 32, 0);
draw_rectangle(100, 120, 400, 380, 0);

// Reset target when done drawing
surface_reset_target();
```
This will not be drawn to the screen -- it will only be saved to the surface.

To draw it to the screen, you can use this function:
```js
draw_surface(surface, 0, 0);
```

Surfaces are volatile, as in, they can get destroyed automatically. So when dealing with a surface, always make sure that it exists first:
```js
if (surface_exists(surface)) {
```

You can also just re-create it if it doesn't exist; this is usually done in the **Draw Begin** event.

```js
if (!surface_exists(surface)) {
    surface = surface_create(width, height);
}
```