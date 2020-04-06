---
title: How to do depth-ordering?
permalink: /how-to-do-depth-ordering/
categories: [Objects, Top-Down]
tags: [depth, order, ordering, z, test, top, down, front, back]
---

To make sure that objects are drawn in the correct order, when making a top view game, you can use the `depth` variable.

```js
/// End Step
depth = -y;
```

`depth` controls the draw order of the instances, so which instance appears in the front and which appears in the back is dependent on that draw order.

Instances with higher depth values are drawn first, and so they're below instances with lower depth values.
An instance with a depth of 500 would be **below** an instance with a depth of -200.

![Example](/assets/gmhow-depth.png)

So when you set `depth` to `-y`, you're making sure that instances that are ordered based on their vertical position.

It is recommended to use `bbox_bottom` instead of `y`, so that the "foot" of each instance becomes its center point for depth ordering.

```js
depth = -bbox_bottom;
```