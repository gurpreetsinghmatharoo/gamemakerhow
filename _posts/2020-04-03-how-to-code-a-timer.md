---
title: "How to code a timer?"
permalink: /how-to-code-a-timer/
categories: Objects
tags: [make, code, timer, interval, run, 'on', a, an]
---

You can use [Alarms](https://docs2.yoyogames.com/source/_build/3_scripting/4_gml_reference/instances/instance_variables/alarm.html) to run code after some time or on a loop.

Let's say you set Alarm 0 to `30`, in the Create event of an object:

```js
/// Create
alarm[0] = 30;
```

Since one second has `60` steps, the Alarm 0 event should run after half a second.

```js
/// Alarm 0 event
speed += 1;
```

After half a second, the speed of the instance will be increased by 1.

If you set the alarm again inside the same Alarm event, it'll create a loop:

```js
speed += 1;

alarm[0] = 60;
```

From that point on, the alarm will run every `60` steps -- which is one second. This creates a 1-second interval loop.