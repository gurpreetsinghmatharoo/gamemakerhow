---
title: How to jump in a top-down game?
categories: [objects, top-down]
permalink: /jump-in-top-down-game/
tags: [jump, top, down, game, view, z, axis]
---

Jumping in a top-down game is tricker. You're already using up the X and Y axes for 4-directional movement, so for jumping, you now need a third axis: Z.

The same jumping mechanics that you apply to the Y axis [in a platformer game]({{site.baseurl}}{% link _posts/2020-03-17-how-to-jump-in-a-platformer.md %}), can be applied to the Z axis, in a top-down game.
To store the value of that axis, you'd have to create a variable (`z`).

Then, when drawing that instance, you'd have to add `z` to the Y-axis:

```js
draw_sprite_ext(sprite_index, image_index, x, y+z, ... );
```

## Ground Collisions

For checking whether you're on the ground, you can simply check if `z` is greater than 0.

### Links

See this tutorial: [Z-Axis in 2D Games](https://www.youtube.com/watch?v=jRAXB-16_7s)

*For other topics on jumping, see this: [How to make the player jump?]({{site.baseurl}}{% link _posts/2020-03-17-how-to-make-the-player-jump.md %})*