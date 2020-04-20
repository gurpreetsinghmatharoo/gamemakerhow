---
title: How to pause a game?
permalink: /how-to-pause-a-game/
categories: [General, Objects]
tags: [pause, unpause, resume, escape, menu]
similar:
    -   permalink: /how-to-draw-paused-game/
        title: How to draw a paused game?
---

The simplest way to pause a game, is to [deactivate](https://docs2.yoyogames.com/source/_build/3_scripting/4_gml_reference/instances/deactivating_instances/instance_deactivate_all.html) all instances, except for the main controller object (which handles pausing & unpausing).

Let's say we want to pause/unpause the game when the player presses **Escape**.
For that, we would:

* **Deactivate** instances to pause the game
* **Activate** instances to resume the game

```js
/// Step event of your controller object
/// 'pause' is a variable initialized at false

if (keyboard_check_pressed(vk_escape)) {
    pause = !pause; // Flip pause boolean (true to false, and vice-versa)

    // Paused
    if (pause) {
        instance_deactivate_all(true); // <-- Argument set to 'true', so that the controller instance is not disabled
    }
    // Resume
    else {
        instance_activate_all();
    }
}
```

If you implement this, you will notice that you can't see any instances when you pause the game, because they're all deactivated.

To know how to display a snapshot of the game while it is paused, take a look at this page:
