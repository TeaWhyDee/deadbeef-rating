# This forks modifications
* Up to 10 star rating (instead of up to 5).
* Makefile copied from the AUR package,
  install shell scripts removed because they weren't working for me,
  more information in [Building & Installing](#-building--installing)


# DeaDBeeF Song Rating plugin

A plugin enabling commands to rate track(s) by writing to the `%rating%` metadata tag. The commands are accessible from the context menu or by binding them to hotkeys. 

Big thanks to [Alexey Yakovenko](https://github.com/Alexey-Yakovenko) for the [DeaDBeeF](http://deadbeef.sourceforge.net/) music player.

# Building & Installing
1. Clone this repository
2. Download `deadbeef.h`, for example using `curl https://raw.githubusercontent.com/DeaDBeeF-Player/deadbeef/master/deadbeef.h > deadbeef.h`
3. Run `make build` to build rating.so.
4. Run `make install` to install the plugin.

# Uninstalling
Run `make uninstall` to remove the plugin.

# Using
I personally use the following format:
`$meta(rating)`
which displays a number from 0 to 10 (the star rating).

In order to show the rating tags in the playlist, add a new custom column with the following format:

`$ifequal([%rating%], 5, *****,)$ifequal([%rating%], 4, ****,)$ifequal([%rating%], 3, ***,)$ifequal([%rating%], 2, **,)$ifequal([%rating%], 1, *,)`

If you want, you can replace `*` with your rating indicator of choice. For example with beautiful awesome stars:

`$ifequal([%rating%], 5,★★★★★,)$ifequal([%rating%], 4,★★★★,)$ifequal([%rating%], 3,★★★,)$ifequal([%rating%], 2,★★,)$ifequal([%rating%], 1,★,)`

Or combine them with empty stars:

`$ifequal([%rating%], 5,★★★★★,)$ifequal([%rating%], 4,★★★★☆,)$ifequal([%rating%], 3,★★★☆☆,)$ifequal([%rating%], 2,★★☆☆☆,)$ifequal([%rating%], 1,★☆☆☆☆,)$ifequal([%rating%], 0,☆☆☆☆☆,)`

# License

    DeaDBeeF rating plugin
    Copyright (C) 2016  Christian Hernvall

    This program is free software: you can redistribute it and/or modify
    it under the terms of the GNU General Public License as published by
    the Free Software Foundation, either version 3 of the License, or
    (at your option) any later version.

    This program is distributed in the hope that it will be useful,
    but WITHOUT ANY WARRANTY; without even the implied warranty of
    MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
    GNU General Public License for more details.

    You should have received a copy of the GNU General Public License
    along with this program.  If not, see <http://www.gnu.org/licenses/>.
