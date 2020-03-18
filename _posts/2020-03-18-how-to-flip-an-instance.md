---
title: How to flip an instance/sprite?
categories: [objects, sprites]
permalink: /how-to-flip-an-instance-sprite/
---

Whether you're making a platformer or a top-down game, you want your instances to flip, depending on where they're facing on the X-axis: that is, either left or right.

That can simply be done by modifying the X-scale of a sprite/instance. `1` is the default scale. So, using `-1` as the X-scale would flip the sprite in the other direction.

In an instance, it can be done with the `image_xscale` variable:

```js
if (hsp != 0)
    image_xscale = sign(hsp)
```
*If the hsp (horizontal speed) is not zero, it sets the image_xscale to its sign (either 1 or -1).*

The same effect can be applied on a sprite being drawn with `draw_sprite_ext` or any form of it.

```js
draw_sprite_ext(sArrow, 0, x, y, -1, 1 ... ) // Flip the arrow horizontally
```

## Links

[sign() function](https://docs2.yoyogames.com/source/_build/3_scripting/4_gml_reference/maths/number%20functions/sign.html)
