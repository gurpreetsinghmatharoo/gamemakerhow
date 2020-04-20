---
title: How to draw a paused game?
permalink: /how-to-draw-paused-game/
categories: [Objects, Surfaces]
tags: [display, draw, pause, paused, snapshot, deactivate, invisible, surface]
similar:
    -   permalink: /how-to-pause-a-game/
        title: How to pause a game?
    -   permalink: /how-to-use-surfaces/
        title: How to use surfaces?
---

You can pause your game now, but you can't see your deactivated instances. To make this work, you can make use of **Surfaces**.

> *This is a follow-up to the [pause system here](/how-to-pause-a-game/).*

A [Surface](/how-to-use-surfaces/) is a rectangular canvas where something is drawn.

The [application_surface](https://docs2.yoyogames.com/source/_build/3_scripting/4_gml_reference/drawing/surfaces/the%20application%20surface.html) is where your game is drawn. So when you pause the game, you can copy the contents of that surface into your own surface, and draw that while your game is paused.

When pausing your game and deactivating the instances, you'd do this:
```js
/// 'pause_surf' should be initialized at -1
    {
        instance_deactivate_all(true);

        // Get application surface size
        var _surf_w = surface_get_width(application_surface);
        var _surf_h = surface_get_height(application_surface);

        // Create surface with that size
        pause_surf = surface_create(_surf_w, _surf_h);

        // Copy application surface to new surface
        surface_copy(pause_surf, 0, 0, application_surface);

        // Disable drawing the application surface
        application_surface_draw_enable(false);
    }
```

When resuming your game, you would destroy your surface:
```js
    {
        instance_activate_all();

        // Destroy pause surface
        if (surface_exists(pause_surf)) {
            surface_free(pause_surf);
        }

        // Enable drawing the application surface
        application_surface_draw_enable(true);
    }
```

Now you can draw this surface in the **Post-Draw** event, while the game is paused:
```js
if (pause && surface_exists(pause_surf)) {
    draw_surface(pause_surf, 0, 0);
}
```