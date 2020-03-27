---
title: How to move an instance?
categories: objects
permalink: /how-to-move-an-instance/
tags: [how, to, move, an, instance, position, change]
---

To move an instance, you can modify its `x` and `y` properties. `x` is the instance's horizontal position, and `y` is the vertical position.

```js
// Moves the instance to 320, 400 in the room
x = 320;
y = 400;
```

You can also use the built-in variables `hspeed` and `vspeed` to set the horizontal speed and vertical speed of the instance, respectively.

```js
// Tells the instance to move left horizontally, and down vertically
hspeed = -4;
vspeed = 4;
```

However, it is recommended to create your own variables for movement, usually called `hsp` and `vsp`.
You can add them to the `x` and `y` variables respectively, in the Step event.