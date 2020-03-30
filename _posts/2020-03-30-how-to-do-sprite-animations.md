---
title: How to do sprite animations?
categories: Objects, Sprites
permalink: /how-to-do-sprite-animations/
tags: [sprite, animation, animating, animations, image, speed, frame, state]

similar:
    -   permalink: /how-to-flip-an-instance-sprite/
        title: "How to flip an instance?"
    -   permalink: /how-to-animate-an-object/
        title: "How to animate an object?"
---

Simple sprite animation in an object can be done by changing the `sprite_index` when appropriate.

For example, in a platformer, you would switch between jump/walk/idle sprite animations like this:

```js
var _grounded = place_meeting(x, y + 1, oGround);

if (!_grounded) {
    sprite_index = sPlayer_Jump;
}
else if (moveX != 0) {
    sprite_index = sPlayer_Walk;
}
else {
    sprite_index = sPlayer_Idle;
}
```