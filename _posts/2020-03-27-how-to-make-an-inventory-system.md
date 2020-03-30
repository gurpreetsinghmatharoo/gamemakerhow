---
title: How to make an inventory?
categories: Data-Structures
permalink: /how-to-make-an-inventory/
tags: [inventory, bag, items, loot, store, array, list, data, structure, ds, lists]

similar: 
    -   permalink: /how-to-draw-an-inventory/
        title: "How to draw an inventory"
---

A simple inventory can be made using a [DS List](https://docs2.yoyogames.com/source/_build/3_scripting/4_gml_reference/data_structures/ds%20lists/index.html).

```js
/// Create event
inventory_list = ds_list_create();

/// Clean Up event (Always destroy data structures!)
ds_list_destroy(inventory_list);
```

You can add your items into this list. Let's say your items are numbered (`0` for Apple, `1` for Orange, `2` for Wood, etc.)

You can use [Enums](https://docs2.yoyogames.com/source/_build/3_scripting/3_gml_overview/9_data_types.html) to store your item IDs:

```js
enum ITEM {
    APPLE = 0,
    ORANGE = 1,
    WOOD = 2
}
```

These items (which are really numbers) can be added into the inventory list.

```js
/// Collision event with "oApple"
ds_list_add(inventory_list, ITEM.APPLE);

instance_destroy(other); // Destroy the Apple instance
```