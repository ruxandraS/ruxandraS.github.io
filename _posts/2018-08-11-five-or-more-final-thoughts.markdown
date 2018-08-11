---
layout:     post
title:      "Five-or-More Modernisation: It's a Wrap"
date:       2018-08-11 16:00:00 +0200
category:   GNOME
tags:       Five-or-More GNOME GSoC
---

As probably most of you already know, or recently found out, at the beginning of this week the GSoC coding period officially ended, and it is time for us, GSoC students, to submit our final evaluations and the results we achieved thus far. This blog post, as you can probably tell from the title, will be a summary of all of the work I put into modernising [Five or More][five-or-more] throughout the summer months.

My main task was rewriting [Five or More][five-or-more] in Vala since this simple and fun game did not find its way to the list of those included in the [Games Modernisation Initiative][games-modernisation-initiative]. This fun, strategy game consists of aligning, as often as possible, five or more objects of the same shape and color, to make them disappear and score points.

Besides the Vala rewrite, there were also some other tasks included, such as migrating to Meson and dropping autotools, as well as keeping the view and logic separated and updating the UI to make this game more relatable for the public and more fresh-looking. However, after thoroughly discussing the details with my mentor, Robert Roth (IRC: evfool), more emphasis was placed upon rewriting the code to Vala, since the GSoC program is specifically designed for software development. However, slight UI modifications were integrated as to match the [visual layout guidelines][visual-layout-guidelines].

Some of the tasks, namely porting to gettext, porting to Meson and dropping autotools happened earlier on, during the pre-GSoC time frame, in the attempt to familiarise myself with the project and the tasks that would come with it.

Afterward, I started with the easier tasks and advanced towards the more complex ones. At first, I ported the application window and the preferences menu and added callbacks for each of the preferences buttons. I then continued with porting the preview widget displaying the next objects to be rendered on the game board.

Next, it was time to channel my attention towards porting the game board, handling board colour changes and resizing the board alongside the window resize, by using the grid frame functionality inside the [libgnome-games-support][libgnome-games-support] library.

The following target was implementing the actual gameplay logic, which consisted of a pathfinding algorithm based on A\*, erasing all objects of the same shape and colour aligned in a row, column or diagonal from the board, if there were either five or more than five, and adding to the score whenever that happened. I also made the object movement possible with both clicking and keyboard keys, for more ease of use.

Finishing touches included adding the high scores tables via the [libgnome-games-support][libgnome-games-support] library, displaying an option to change the theme of the game, adding a grid to be able to make out easier the actual cells in which different shaped and coloured objects should reside, as well as updating some information contained by the help pages.

Some features, however, could not be done during the GSoC period. These included handling raster game themes, making significant UI updates, as well as some other extra-features I wanted to add, which were not part of the original project description such as gamepad support or sound effects. The fist feature mentioned in this list, handling raster images was decided upon skipping as a suggestion from my mentor, as the existing raster themes were low-resolution and did not scale well to large size and HiDPI displays.

For easier reading, I decided to also include this list of the tasks successfully done during GSoC:

* Ported from autotools to Meson
* Ported application window and preferences menu
* Added callbacks for all buttons
* Ported widget of next objects to be rendered on the game board
* Handled the resize and colour change of the game board
* Implemented the gameplay logic (pathfinding, matching objects and calculating scores)
* Made gameplay accessible for both mouse clicks and keyboard controls
* Added high scores via the [libgnome-games-support][libgnome-games-support] library
* Handling vector image theme changing
* Made slight modifications to the UI to serve as a template and changed the spacing as recommended in the [visual layout guidelines][visual-layout-guidelines].
* Updated documentation.

All code is available by accessing this [merge request link][merge-req].

[five-or-more]: https://wiki.gnome.org/Apps/Five%20or%20more
[games-modernisation-initiative]: https://wiki.gnome.org/Initiatives/GamesModernisation
[libgnome-games-support]: https://gitlab.gnome.org/GNOME/libgnome-games-support
[merge-req]:  https://gitlab.gnome.org/GNOME/five-or-more/merge_requests/1
[visual-layout-guidelines]: https://developer.gnome.org/hig/stable/visual-layout.html.en