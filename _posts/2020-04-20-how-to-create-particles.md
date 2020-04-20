---
title: How to create particles?
permalink: /how-to-create-particles/
categories: [Particles]
tags: [particles, effects, types]
similar:
    -   permalink: https://www.youtube.com/watch?v=tV4ghL4CEtw
        title: Introduction to Particles (YouTube)
    -   permalink: https://docs2.yoyogames.com/source/_build/3_scripting/4_gml_reference/drawing/particles/index.html
        title: GMS2 Documentation for Particles
---

To create particles with GML, you need (1) a **Particle System**, and (2) a **Particle Type**.

A Particle System can be created in a controller object:
```js
/// Create event
global.partSystem = part_system_create();
part_system_depth(global.partSystem, -100); // Set depth

/// Clean Up event
part_system_destroy(global.partSystem);
```
This particle system will be used for creating particles.

The actual particles that will be created, will come from **Particle Types**. Here is an example of one particle type:
```js
global.ptBasic = part_system_create();

part_type_shape(global.ptBasic, part_type_disk);
part_type_life(global.ptBasic, 30, 40);
part_type_alpha2(global.ptBasic, 1, 0);
```
This particle type will have a disk shape, a life of between 30 and 40 steps (selected at random), and an alpha fading from 1 to 0.

This can then be created anywhere, anytime, using this function:
```
part_particles_create(global.partSystem, x, y, global.ptBasic, 1);
```
The particle will be created in the specified particle system.