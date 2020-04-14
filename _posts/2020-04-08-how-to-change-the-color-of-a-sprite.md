---
title: How to change the color of a sprite?
permalink: /how-to-change-the-color-of-a-sprite/
categories: [Sprites, Objects, Shaders]
tags: [change, color, sprite, object, instance, blend, multiply, colorize, set, modify, shaders, tint]
---

The color of an instance can be changed with `image_blend`.

```js
image_blend = c_red;
```

> [List of colors](https://docs2.yoyogames.com/source/_build/3_scripting/4_gml_reference/drawing/colour/index.html)

Note that this only **multiplies** the color. So if your sprite is white, then it will appear red; but if it's a darker color (say dark green) then the product of the original color (dark green) and the new color (red) will be the final result.

The same parameter can also be found in the [draw_sprite_ext()](https://docs2.yoyogames.com/source/_build/3_scripting/4_gml_reference/drawing/sprites_and_tiles/draw_sprite_ext.html) function:

```js
draw_sprite_ext(sprite, index, x, y, xscale, yscale, rot, /*THIS*/blend_color, alpha)
```

With a shader, you can override the RGB values of the sprite with the RGB values of the blend color:

```glsl
gl_FragColor.rgb = v_vColour.rgb;
```

This way, if your blend color is `c_red`, then all pixels in the sprite will actually turn red (no matter what the original color is).