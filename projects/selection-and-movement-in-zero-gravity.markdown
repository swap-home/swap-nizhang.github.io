---
layout: post
title:  "Selection and Movement in Zero Gravity"
date:   2016-04-10 01:29:12 -0400
tags: RTS selection movement
categories: projects demo pinned
demo: ../build/windows/Movement_ZeroG.zip
github: https://github.com/swaparcher/ZeroG_Movement_Selection
thumbnail: ../img/screenshots/thumbs/ZeroG.jpg
---

{% include icon-github.html username="swap-nizhang"" %} /
[ZeroG_Movement_Selection]({{page.github}})

Download a build for Windows (tested on 8.1?)
[Movement_ZeroG]({{page.demo}})

Rockets, and by extension Spaceships typically have large thrusters for acceleration, as well as smaller thrusters for deceleration and turning.
This demo system demonstrates an implementation of both a selection system and a movement system to simulate conditions in a zero-g environment.

Controls: Mouse + Keyboard (Optional)

The selection system should be familiar to any RTS player:

- left click a unit to select it
- left drag a box to select a group of units
- double left click a unit to select all units of that type on screen (also Ctrl + left click)
- Shift + left click to add/remove units from current selection
- right click to move units

The movement system is implemented similar to the classic arcade game Asteroids:
Units can accelerate/decelerate in the direction they are facing, as well as turn.

![Screenshot](../img/screenshots/ZeroG.jpg)

Different shapes (types of units) have different max speeds and turn rates.

- The black line denotes the direction the unit is facing.
- The green arrow represents the velocity.
- The purple arrow represents the acceleration.
- The yellow line represents an movement order.
- The shaded yellow circle represents the area the unit needs to start decelerating to come to a complete stop

