---
layout: post
title: 'Example: Rotating a Sequence Item'
permalink: /examples/rotating-a-sequence-item/
categories: [Examples, GMS2.3]
tags: [rotation, sequence, matrix]
---

You can create a Sequence for a sword animation, and play it in-game. But, the animating sword cannot be easily rotated with the player.

![GIF 0](/assets/GIFs/seqrot0.gif)

> *(The player in the Sequence is later made invisible, so you don't see two players)*

One of the solutions for this is to use the [Matrix Functions](https://docs2.yoyogames.com/source/_build/3_scripting/4_gml_reference/matrices/index.html).

By changing the World Matrix in the Draw event of the sword, you can make it draw relative to the player.
The matrix will handle the player's rotation, and since the sword will be drawn relative to that, it'll rotate with the player.

![GIF 1](/assets/GIFs/seqrot1.gif)

Of course, this only makes it draw in the correct position.
This won't fix collisions, although you can use the same matrix to [transform the sword coordinates](https://docs2.yoyogames.com/source/_build/3_scripting/4_gml_reference/matrices/matrix_transform_vertex.html), and then calculate collisions at that position.

# [Download Project](/projects/sequences-matrix-rotation.yyz)