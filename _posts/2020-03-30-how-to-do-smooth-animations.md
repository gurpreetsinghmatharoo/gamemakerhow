---
title: How to do smooth animations?
categories: Objects
permalink: /how-to-do-smooth-animations/
tags: [animation, animating, animations, image, speed, frame, state, lerp, smooth, interpolation]

similar:
    -   permalink: /how-to-animate-an-object/
        title: "How to animate an object?"
---

Smooth animations can be done using the [`lerp`](https://docs2.yoyogames.com/source/_build/3_scripting/4_gml_reference/maths/number%20functions/lerp.html) function.

Let's say you want to animate the `x`/`y` position of an instance, but smoothly. For that, you'd first need "target" `x`/`y` values:

```js
/// Create
targetX = x;
targetY = y;
```

You can set `targetX` and `targetY` to wherever you want the instance to move, and then have `x` and `y` follow the target values, using `lerp()`:

```js
/// Step
// Set target to mouse position
targetX = mouse_x;
targetY = mouse_y;

// Move x/y to targetX/Y by 10% (0.1)
var _t = 0.1;
x = lerp(x, targetX, _t);
y = lerp(y, targetY, _t);
```

Here's how this would look (the green crosshair is the target position)

![Example](/assets/GIFs/gmhow_lerp.gif)