---
layout:     post
title:      "Five-or-More Modernisation - Now They Move!"
date:       2018-07-30 20:30:00 +0200
category:   GNOME
tags:       Five-or-More GNOME GSoC
---

These past two weeks I have worked on (probably) the most exciting part of modernising the [Five or More][five-or-more] game. After the new changes, the game is officially playable and fun! But still, there is room for more changes. So let’s jump right to the updates.

First of all, if you remember reading [my previous blog post][previous-blog-post], there were no means to interact with a shape, or otherwise move it to any desired cell. The cells inside the game board were [filled up randomly][board-filling] on click, using the queue on the top left corner of the window, which contained the next shapes to be rendered inside the game area.

Now, all of that changed, and the user can interact with each individual shape rendered on the game board. The pathfinding system I came up with uses the A\* algorithm with a Manhattan distance heuristic to determine the shortest path from the current cell to the destination cell chosen by the player.

<br>

<div align="center">
	<img src="https://ruxandraS.github.io/assets/images/progress-report-2/1-player-shape-interaction.gif"  width="500"/>
	<center>Player interaction with shapes</center>
</div>

<br>

Next, I continued to work on making five (or more 😄) shapes of the same kind aligned in a row, column or diagonal, disappear from the board...

<br>

<div align="center">
	<img src="https://ruxandraS.github.io/assets/images/progress-report-2/2-match.gif"  width="500"/>
	<center>Matching five or more shapes in a row</center>
</div>

<br>

... and whenever that happens, the player receives points as a result, which are displayed on the top-right corner of the window.


Once I reviewed the screen recordings, I realised I am actually not as good at playing this game. 🙈


[board-filling]: https://ruxandras.github.io/assets/images/progress-report-1/4-spawn-next.gif
[five-or-more]: https://wiki.gnome.org/Apps/Five%20or%20more
[previous-blog-post]: https://ruxandras.github.io/gnome/2018/07/17/five-or-more-progress.html
