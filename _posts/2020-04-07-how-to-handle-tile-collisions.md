---
title: How to handle tile collisions?
permalink: /how-to-handle-tile-collisions/
categories: [Objects, Rooms, Scripts]
tags: [tile, tilemap, collisions, wall]

similar:
    -   permalink: /how-to-handle-collisions/
        title: How to handle collisions?
---

Tile collisions only allow the first tile in a tileset to be the "empty" tile:

![Tilemap](/assets/tilemaps.png)

When using auto-tiling, make sure to set that tile as the "empty" tile.

Now you need to get the tilemap ID when the room starts:

```js
/// Room Start
global.col_tilemap = layer_tilemap_get_id("Layer Name");
```

You can then make a script/function that takes in `hsp` and `vsp` (x/y speeds) as parameters, and returns whether there's a tile collision where the instance is moving:

```js
var _col =  tilemap_get_at_pixel(global.col_tilemap, bbox_left + _hsp, bbox_top + _vsp)
        ||  tilemap_get_at_pixel(global.col_tilemap, bbox_right + _hsp, bbox_top + _vsp)
        ||  tilemap_get_at_pixel(global.col_tilemap, bbox_left + _hsp, bbox_bottom + _vsp)
        ||  tilemap_get_at_pixel(global.col_tilemap, bbox_right + _hsp, bbox_bottom + _vsp)
```

We're checking all four corners of the bounding box (with the `hsp`/`vsp` added) for collisions on the tilemap.

This function can be used with the collision system demonstrated [here](/how-to-handle-object-collisions/).

> Note that if your instance's mask is larger than a particular block of tiles, then your instance may be able to go through them.