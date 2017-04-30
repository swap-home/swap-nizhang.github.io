---
layout: post
title:  "Dungeons and Procedural Generation"
date:   2016-04-12 11:11:42 -0400
tags: random procedural generation dungeon crawler
categories: projects demo pinned
demo: ../build/windows/Procedural_Generation.zip
github: https://github.com/swaparcher/tile_dungeon_generation
thumbnail: ../img/screenshots/thumbs/TileGen.jpg
---

{% include icon-github.html username="swap-nizhang"" %} /
[Procedural Generation]({{page.github}})

Download a build for Windows (tested on 8.1?)
[Procedural Generation]({{page.demo}})

As games nowaday grow in ambition, replayability becomes a huge concern for today's persistent games.
PvP games create replayability through human opponents that make more or less unpredictable choices in-game. To compete, PvE games have been forced into generating content faster than development processes allow. 
The fix? Instead of designing levels statically, build levels dynamically via random or procedural generation. The Indie scene has seen plenty of use through Minecraft, Binding of Issac, Nuclear Throne, etc.

There are two main types of dungeon generation, one is to use a tile-based philosophy in which individual tiles are placed, and combined make up organic rooms.
The second approach is to place rooms and stich them together with paths.

Dungeon generation is a fairly binary system, given a bunch of configurable parameters and a grid, set each tile in the grid to be either 0 (a wall, unpathable), or 1 (pathable terrain).

For overworld generation, typically you generate a grid of real values, which represent a heightmap. A simple example algorithm would be the [Diamond-square](https://en.wikipedia.org/wiki/Diamond-square_algorithm) algorithm.

With GameMaker, I've implemented a simple [Drunken Walk](https://en.wikipedia.org/wiki/Random_walk) algorithm with configurable parameters to try to build levels on a 40x40 grid. This is a tile based approach, as a crawler moves randomly throughout a map, carving out pathable tiles until a specified cap is reached or some error state is reached, finishing or forcing a restart of the map generation.

Controls: Keyboard

On the first page, follow the instructions to modify the parameters to the drunken walk algorithm

Here is an explanation of what each parameter controls

~~~~
Maximum Pathable Tiles:	How many tiles to change before the algorithm finishes

Up Base Weight: The base weight of moving to the tile above
Down Base Weight: The base weight of moving to the tile below
Left Base Weight: The base weight of moving to the tile to the left
Right Base Weight: The base weight of moving to the tile to the right
Center Weight: The weight added in the direction of the center
Forward Weight: The weight added in the same direction as the last move
Turn Weight: The weight added to both the left and right turn from the last move
Reverse Weight: The weight added to the reverse of the direction of the last move

Single Block Weight: The weight of converting only the current tile
Double Block Weight: The weight of converting a 2x2 block, with the current tile in the top left
Triple Block Weight: The weight of converting a 3x3 block, with the current tile in the center

Max Border Attempts Before Restart: 
	The maximum amount of times it runs against the 
	border of the 40x40 grid before restarting the dungeon generation

Mob Density: A number from 0 to 1 that gives the percentage to spawn an enemy on the current tile
~~~~

The default generation parameters "Sewers" generates long, winding corridors with very rarely large rooms.

![Screenshot](../img/screenshots/TileGen.jpg)