---
layout:     post
title:      "Five-or-More Modernisation - Progress Report"
date:       2018-07-17 10:00:00 +0200
category:   GNOME
tags:       Five-or-More GNOME GSoC
---

Over the course of the past couple of months, I was able to achieve a promising progress in modernising [Five or More][five-or-more], although I would have to say there is a fair share of aspects to tackle yet.

I opted for rewriting the code module by module, without combining C and Vala code. There was was an [old attempt][old-vala-port] to port [Five or More][five-or-more] to Vala, but I chose not to use it due to the fact that the [partial port][old-vala-port] was 4 years old and it definitely needed an update, which might have taken quite some time, and might have produced some nasty bugs. While doing so, I paid extra attention to keep things nicely separated: all of the currently ported modules separate the game logic from the drawing logic and the UI.

I also managed to port the app menu and the preferences window. However, due to the new [design gudelines][appmenu-proposal], which are currently only in the state of a proposal, the app menu might require future alterations.

<br>

<div align="center">
	<img src="https://ruxandraS.github.io/assets/images/progress-report-1/1-app-menu.gif"  width="500"/>
	<center>App Menu access with functional callbacks</center>
</div>

<br>

The app window is currently resizable and it sports a customisable coloured board. After each click, the next shapes contained inside the next pieces widget are being spawned inside the game board.

<br>

<div align="center">
	<img src="https://ruxandraS.github.io/assets/images/progress-report-1/2-change-color.gif"  width="500"/>
	<center>Changing the board colour from the Preferences menu</center>
	<br>
	<img src="https://ruxandraS.github.io/assets/images/progress-report-1/3-change-boardsize.gif"  width="500"/>
	<center>Changing the board size from the Preferences menu and resizing the window (for some reason there is a colour flick when recording the screen for this one)</center>
	<br>
	<img src="https://ruxandraS.github.io/assets/images/progress-report-1/4-spawn-next.gif"  width="500"/>
	<center>Clicking inside the game board area</center>
	<br>
</div>

<br>

I am currently working on the pathfinding algorithm, which will basically allow the user to move a shape from cell A to cell B inside the game grid.

The short todo list includes adding the game over logic and implementing both the scores and high scores system, by using the [libgnome-games-support][libgnome-games-support]. There are also some extra-features to be added, such as animations, sounds and gamepad-support, and providing a fresh looking UI.

[five-or-more]: https://wiki.gnome.org/Apps/Five%20or%20more
[old-vala-port]: https://gitlab.gnome.org/GNOME/five-or-more/tree/vala-port
[appmenu-proposal]: https://wiki.gnome.org/Initiatives/GnomeGoals/AppMenuRetirement
[libgnome-games-support]: https://gitlab.gnome.org/GNOME/libgnome-games-support