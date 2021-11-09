# TexTron Snake 🐍

TexTron Snake is a very simple ASCII snake game tributed to the classic
Tron arcade. It was meant to be developed as a collaborative programming
exercise in a course on Open Source Systems taught to undergraduate CS
students.

## SETUP

In the following section, the leading `#` in commands indicates that it requires
administrative privileges (`sudo`).

### Dependencies


If you have obtained the project source from the __version control
repository__, you'll need to have GNU Build System (Autotools) installed.
In Debian/Ubuntu based platforms, you may install the required software with:

 ```
 # apt install automake autoconf
 ```

Other missing dependencies will be indicated by the configuration script ---
e.g.: if you don't have `libncurses` installed, it'll complain about it and you
may install it (if in Debian/Ubuntu based system) with:

```
# apt install libncurses5-dev
```

It is also required for your system to have support for POSIX threads.

### Installation

If you have obtained the project source from the __version control repository__, execute the script

 ```
 $ ./autogen.sh
 ```

to bootstrap the build configuration script `configure`.

On the other hand, if you have obtained the software form a __distribution
repository__, usually as a tarball, you should already have the script
`configure`, which performs a series of tests to collect data about the build
platform.

Either way, locate the file in the root of source directory and execute it:

```
 $ ./configure
```

If it complains about missing pieces of software, install them as needed.


Finally, build the software and install it either globally or locally.

To install the programa under the system path --- usually placing the binary
in `/usr/bin` and the data files in `/usr/share` ---, run:

```
 $ make
 # make install
```

Optionally, if you wish to install the software under a different location,
 for instance, in `/tmp/foo`, execute:

```
 $ ./configure --prefix=/tmp/foo
 $ make
 $ make install
```

This shall install the software locally, with the binary in `/tmp/foo/bin`
and the data files in `/tmp/share`.

For more detailed instructions, please, refer to the
[installation guide](./INSTALL).

## USAGE

```
 Usage:  ttsnake [options]

         Options

         -h, --help      Displays this information message
         -d, --data      Selects a non-default data path
```

### Playing the game

The game takes place on a rectangular areana where a snake continuously
move in one of the four directions: left, right, up and down --- it never
stops. As the snake moves it looses energy and if all of it is exausted, the
snake dies. To recover energy, the snake needs to eat pieces of food which
are constantly replaced at random positions.

Be careful, though. The arena borders are electrified and would kill the snake
if touched. Morover, mind that the snake is poisonous and it would also die if
it accidently bites itself, i.e. if the snake's head crosses its own body (yes,
this is weird for snakes, but this is a Tron Snake).

The game score is the count of eaten blocks until the game is over.

### Controls:

```
WASD to control the snake
+ decreases the game speed
- increases the game speed
q quits
r at anytime to restart the game
```

## Contribute to this project

If you wish to contribute to the project, please, __do__ read the
[contribution guide](doc/CONTRIBUTING.md) for important information and
guidelines.
