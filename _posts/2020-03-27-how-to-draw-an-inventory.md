---
title: How to draw an inventory?
categories: Data-Structures
permalink: /how-to-draw-an-inventory/
tags: [inventory, bag, items, loot, store, array, list, data, structure]

similar: 
    -   permalink: /how-to-make-an-inventory/
        title: "How to make an inventory"
---

Assuming your [inventory is a DS List]({{site.baseurl}}/how-to-make-an-inventory/), and your items are in an Enum, you can store the sprite of each item in an array:

```js
global.itemSprite[ITEM.APPLE] = sApple;
global.itemSprite[ITEM.ORANGE] = sOrange;
// ...and more
```

To draw the inventory as a visual list, you can loop through it, get each item's sprite and draw it.

```js
// Base draw position
var _invX = 8;
var _invY = 8;

var _size = ds_list_size(inventory_list);   // Size of list

for ( var i = 0; i < _size; i ++ ) {
    var _item = inventory_list[| i];        // Get item (using | accessor for DS lists)
    var _itemX = _invX;                     // X where item is drawn
    var _itemY = _invY + 32 * i;            // Y where item is drawn

    draw_sprite(global.itemSprite[item], 0, _itemX, _itemY);  // Sprite taken from global.itemSprite[]
}
```