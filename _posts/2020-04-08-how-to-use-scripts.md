---
title: How to use scripts? (2.2.5)
permalink: /how-to-use-scripts/
categories: [Scripts]
tags: [scripts, functions, methods, call]
---

Scripts allow you to create custom functions. You can call your script function, pass in arguments, run some code in it, and expect a result; just like a regular built-in function.

> This will change once version 2.3 is out.

```js
/// @desc is_player_dead
/// @arg player

if (argument0.hp == 0) {
    return true;
}
else {
    return false;
}
```

This is a script function that checks if a player is dead. You pass in a `player` instance as an argument; it returns `true` if that player's `hp` is equal to `0`, otherwise, it returns `false`.

This function can be called and the return value can be stored in a variable:

```js
/// Example: in a for() loop
var _is_dead = is_player_dead(players[i]);

if (_is_dead) {
    show_debug_message("Player " + string(i) + " is dead.");
}
```