---
layout:     post
title:      "Five-or-More Modernisation: Now You Can Properly Play It"
date:       2018-08-07 20:30:00 +0200
category:   GNOME
tags:       Five-or-More GNOME GSoC
---

As Google Summer of Code is officially drawing to an end, all of my attention was focused towards making the [Five or More][five-or-more] Vala version feature-complete. As you probably already know from [my previous blog post][previous-blog-post], the game was somehow playable at that time, but it was missing some of the key features included in the old version.

So what's new this time? First and foremost, you can surely notice the game board now sports a grid, which wasn't there until now. On the same note, there are also animations used for clicking a piece on the board, for an improved gaming experience. For further accessibility, some header bar hints are available at different stages in the game: at the start of any new game, at the end of each game, as well as whenever there is no clear path between the initial position and the cell indicated by the user for the current move.

<br>

<div align="center">
	<img src="https://ruxandraS.github.io/assets/images/progress-report-3/1-overall-look.gif"  width="500"/>
	<center>Overall final game look</center>
</div>

<br>


By using [libgnome-games-support][libgnome-games-support], I was able to implement a high scores table, which gets updated each time the player gets a score ranging in the top 10 highest scores for the chosen board size. The high scores for each of all of the three categories can also be viewed as showed in the screencast below. Also, you can see I have done quite my fair share of testing the functionalities and assuring everything worked as planned 😄.

<br>

<div align="center">
	<img src="https://ruxandraS.github.io/assets/images/progress-report-3/2-high-scores.gif"  width="500"/>
	<center>High scores</center>
</div>

<br>

Further changes include theme changing, although this momentarily only works for the vector themes available in [Five or More][five-or-more], namely the ball and shape themes, as implementation for raster images is not fully functional as of this moment.

<br>

<div align="center">
	<img src="https://ruxandraS.github.io/assets/images/progress-report-3/3-change-theme.gif"  width="500"/>
	<center>Changing theme</center>
</div>

<br>

Also, now window size is being saved in between runs, so each time the game starts it will take into consideration the last window size settings, including wether the window was full screened or not.

As for the most exciting change revealed in this blog post, it concerns playing [Five or More][five-or-more] using keyboard controls. Basically, the user can play the game by navigating with the keyboard arrows, the home, end, page up, page down and space, enter or return keys, as described in the [wikipage section for using the keyboard][wiki].

<br>

<div align="center">
	<img src="https://ruxandraS.github.io/assets/images/progress-report-3/4-keyboard-controls.gif"  width="500"/>
	<center>Playing Five-or-More usig keyboard controls</center>
</div>

<br>

If you have been following my journey with GSoC up closely, you probablly remember me mentioning something about extra-features in [my first blog post][first-blog-post], such as adding gamepad support, sounds, or making some design changes. I need to say I feel optimistic about getting some of these features done in the weeks to come, post GSoC. I feel the ground has been already laid down somehow for gamepad support by adding keyboard controls. Also, [Five or More][five-or-more] has already undergone some slight design changes, such as widget spacing and alignment.

[first-blog-post]: https://ruxandras.github.io/gnome/2018/05/07/welcome-to-my-blog.html
[five-or-more]: https://wiki.gnome.org/Apps/Five%20or%20more
[libgnome-games-support]: https://gitlab.gnome.org/GNOME/libgnome-games-support
[previous-blog-post]: https://ruxandras.github.io/gnome/2018/07/30/five-or-more-progress-2.html
[wiki]: https://help.gnome.org/users/five-or-more/stable/play.html.en
