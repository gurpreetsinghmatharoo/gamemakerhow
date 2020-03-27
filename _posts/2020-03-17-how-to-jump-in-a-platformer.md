---
title: How to jump in a platformer?
categories: [objects, platformer]
permalink: /jump-in-platformer/
tags: [jump, in, a, platformer, air]
---

For jumping in a platformer, you need gravity. And for gravity, you need a vertical speed variable.

The gravity would be a constant value, which is added to the vertical speed:

```js
vsp += grav;

y += vsp;
```

When you need to jump, you can simply set vsp to a negative value:

```js
if (keyboard_check_pressed(vk_space) && grounded) {
    vsp = -10;
}
```

`grounded` would store if the player is standing on the ground.