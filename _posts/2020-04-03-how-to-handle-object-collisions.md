---
title: How to handle object collisions?
permalink: /how-to-handle-object-collisions/
categories: Objects
tags: [how, to, handle, make, do, collisions, collide, stop, wall, objects, instances]

similar:
    -   permalink: /how-to-handle-collisions/
        title: How to handle collisions?
    -   permalink: /how-to-move-an-instance/
        title: How to move an instance?
---

To enable collisions in a moving object, you can do this:
1. Set the movement speed (usually `hsp` and `vsp`)
2. Check if there are collisions where you're moving (separately on `x` and `y`)
3. If a collision is found on either dimension, you set that dimension's speed to 0
    * Before setting it to 0, you run a `while` loop to close any gap between the two colliding instances

Using the simple [`place_meeting()`](https://docs2.yoyogames.com/source/_build/3_scripting/4_gml_reference/movement%20and%20collisions/collisions/place_meeting.html) function, the code would look something like this:

```js
/// Step event
// Set speed
hsp = input_x * move_speed;
vsp = input_y * move_speed;

// Check collisions: X
if (place_meeting(x + hsp, y, obj_wall)) {
    // Close the gap with a while loop
    while (!place_meeting(x + sign(hsp), y, obj_wall)) {
        x += sign(hsp);
    }

    // Stop
    hsp = 0;
}
// Check collisions: Y
if (place_meeting(x, y + vsp, obj_wall)) {
    // Close the gap with a while loop
    while (!place_meeting(x, y + sign(vsp), obj_wall)) {
        y += sign(vsp);
    }

    // Stop
    vsp = 0;
}

// Finally, apply movement
x += hsp;
y += vsp;
```