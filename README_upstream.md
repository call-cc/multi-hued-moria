# Umoria COLOR

_The Dungeons of Moria_ is a single player dungeon simulation originally
written by Robert Alan Koeneke, with its first public release in 1983.
The game was originally developed using VMS Pascal before being ported to the
C language by James E. Wilson in 1988, and released as _Umoria_.

Moria/Umoria has had many variants over the years, with [_Angband_](http://rephial.org/)
being the most well known. Umoria was also an inspiration for one the most
commercially successful action roguelike games, _Diablo_!

Supported Platforms:

  - Windows
  - macOS
  - Linux (Ubuntu/Debian)

Compiling and limited testing has been done for other Linux based system
including NetBSD 8.1 and Fedora 32.


## Umoria COLOR

Colour-Umoria was a patch originally written in 1993 by Edouard Poor. In 2020
it was ported by Andrew Weber as a fork of the modernized Umoria restoration
release.

* The correct spelling of "color" is now used 🇺🇸🦅🗽
* Many colors and color assignments were adjusted
* Roguelike controls are now disabled by default to encourage new players to try the game out
* Walking into a door will attempt to open it automatically without having to press the `'o'` key
* Fire, lightning, and glowing effects were added

## Umoria 5.7.x releases

The main focus of the `5.7.0` release was to provide support for the three
main operating systems: Windows, macOS, and Linux. Support for all other
outdated computer systems such as MS DOS, "Classic" Mac OS (pre OSX), Amiga,
and Atari ST was removed.

_Note: there have been no intentional game play changes in the 5.7.x releases._

Since the initial 5.7 release, a great deal of _code restoration_ has been
undertaken in the hope of aiding future development of the game. Some examples
of the work done include reformatting the source code with the help of
`clang-tidy` and `clang-format`, modernizing the code to use standard C types,
breaking apart most large functions (many of which had hundreds of lines of code)
into smaller, easier to read functions, and fixing all compiler warnings when
compiling against recent versions of GCC and Clang.

Full details of all changes can be found in the [CHANGELOG](CHANGELOG.md), and
by browsing the commit history.

Due to its lack of Windows and macOS support Moria was inaccessible to many
people. Hopefully these changes will give many more people a chance to play
this classic roguelike game.


## Notes on Compiling Umoria

Umoria has been tested against GCC (`10` and `11`) and with `ncurses 6.x`,
although recent earlier versions should also work fine.

You will need these as well as `CMake` and the C++ build tools for your system.


### macOS and Linux

Change to the `umoria` game directory and enter the following commands at the
terminal:

    $ mkdir build && cd build
    $ cmake ..
    $ make

NOTE: use `make -j $(nproc)` to speed up compilation on Linux.

An `umoria` directory will be created in the current directory containing the
game binary and data files, which can then be moved to any other location, such
as the `home` directory.


### Windows

MinGW is used to provide GCC and GNU Binutils for compiling on the Windows platform.
The easiest solution to get set up is to use the [MSYS2 Installer](http://msys2.github.io/).
Once installed, `pacman` can be used to install `GCC`, `ncurses`, and the
`make`/`cmake` build tools.

At present an environment variable for the MinGW system being compiled on will
need to be specified. This will be either `mingw64` or `mingw32`.

At the command prompt type the following, being sure to add the correct label
to `MINGW=`:

    $ MINGW=mingw64 cmake .
    $ make

To perform an out-of-source build, type the following:

    $ mkdir build
    $ cd build
    $ MINGW=mingw64 cmake ..
    $ make

As with the macOS/Linux builds, all files will be installed into an `umoria` directory.


## Historical Documents

Most of the original document files included in the Umoria 5.6 sources have
been placed in the [historical](historical) directory. You will even find the
old CHANGELOG, which tracks all code changes made between versions 4.81 and
5.5.2 (1987-2008). If you'd like to learn more on the development history of
Umoria, these can make for interesting reading.

There is also the original Moria Manual and FAQ. Although these are a little
outdated now they are certainly worth reading as they contain a lot of
interesting and useful information.


## Code of Conduct and Contributions

See here for details on our [Code of Conduct](CODE_OF_CONDUCT.md).

For details on how to contribute to the Umoria project, please read our
[contributing](CONTRIBUTING.md) guide.


## License Information

Umoria is released under the [GNU General Public License v3.0](LICENSE).

In 2007 Ben Asselstine and Ben Shadwick started the
[_free-moria_](http://free-moria.sourceforge.net/) project to re-license
UMoria 5.5.2 under GPL-2 by obtaining permission from all the contributing
authors. A year later they succeeded in their goal and in late 2008 official
maintainer David Grabiner released Umoria 5.6 under a GPL-3.0-or-later license.
