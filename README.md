# Meson port of Anton's OpenGL 4 Tutorials book demo code #

This series of demos accompanies the e-book "Anton's OpenGL 4 Tutorials":
[antongerdelan.net/opengl](http://antongerdelan.net/opengl/)

## Meson ##

Building using Meson can be more portable and reliable in different platforms, and
as it's binary free it means a smaller git repository to clone,

``` bash
git clone https://github.com/ebraminio/antons_opengl_tutorials_book --depth=1
```

Meson can be installed either from pip or from the system package manager
```bash
pip3 install meson
# or in Windows
winget install meson
```

See also https://mesonbuild.com/Getting-meson.html

Test mechanism of Meson is (mis)used for running the code,

```bash
meson setup build
meson compile -C build
meson test -C build
```

## Info ##

See "LICENCE.txt" for licence information.

Each chapter with major demonstration code has a corresponding demo here.
There is also an example of code for *Hello Triangle* for OpenGL 2.1 for reference.

Each demo has easy-to-read Makefiles for Linux, MacOS, and Windows.
You may need to download newer versions of the libraries in the `common/` folder.

This code is some years old now and builds may fall out of date. I try to
maintain this so that it functions but be aware that Makefiles and build details
may differ slightly from book text for this reason.

## Compiling ##

The libraries depended on reside in the common/ folder

* `common/include` - Header files.
* `common/linux_x86_64` - 64-bit GNU/Linux libraries.
* `common/osx_64` - 64-bit Apple macOS libraries.
* `common/win32` - 32-bit Windows GCC (MinGW) libraries.
* `common/win64_gcc` - 64-bit Windows GCC (MinGW-w64) libraries.

### Linux ###

* Install a C and C++ compiler - usually by installing a "build-essential"
bundle package via the package manager on your distribution. E.g. for Ubuntu:

```
sudo apt install build-essential
```

* Install the GLFW3, FreeType, and zlib development libraries:

```
sudo apt install libglfw3-dev
sudo apt install libfreetype6-dev
sudo apt install zlib1g-dev
```

* Open a terminal and cd to the demo of choice, then

```
make -f Makefile.linux64
```

### Apple macOS ###

* Install Clang or GNU compiler and tools - usually by installing Apple XCode through the App Store. It's free.
* Open a terminal and `cd` to the demo of choice:

```
make -f Makefile.osx
```

### Windows with GCC ###

* Install the GNU Compiler Collection - usually by installing MinGW (32-bit or the 64-bit alternative). I suggest the minimal MinGW GCC distro at [https://nuwen.net/mingw.html](https://nuwen.net/mingw.html).
* Open a console and `cd` to the demo of choice.
* `make -f Makefile.win32` (MinGW may have renamed `make.exe` to `mingw-make32.exe` or similar).
* Copy the .dll files from the main folder to the demo folder
* Or `make -f Makefile.win64` for the 64-bit build.

If you have trouble linking supporting libraries you may need to recompile GLFW, GLEW, AssImp, and Freetype. It's a good idea to do this anyway to stay up to date.

### Windows with Visual Studio ###

The original Visual Studio solution has gone out of date now, so I removed it.
I have instead recorded a 2020 video stream tutorial where I show how to get Visual Studio set up and start programming OpenGL,
including downloading and setting up libraries.

[Tutorial: Intro to 3D Graphics Programming with OpenGL 4 (with Anton). Stream Recording.](https://youtu.be/qQJ7irgxZFQ)

This includes a very verbose set-up of Visual Studio 2019 with helper libraries.

## Caveats and Errata ##

* Since publication the most reliable version of newer OpenGL that will work everywhere, including macOS, is 4.1 Core. I suggest hinting to use this version first.
* Code is directly copy-pasted from book sections. This means that there will be redundant OpenGL calls to bind things etc., but I think it's easier to follow along like this.
* Code explained in prior examples is moved to a file called `gl_utils.cpp` to avoid cluttering `main.cpp`. This means that `gl_utils.cpp` is not necessarily the same in each demo, but is built up gradually.
* Out of date build files have been removed; 32-bit Linux and older Visual Studio files.
* Sometimes people ask for C examples. OpenGL is a C API, and I would have used C if writing the text later. Readers wishing to use a C compiler should do so - only very minor code convention changes are required.

## Credits ##

Special thanks to all the readers over the years that have submitted additions,
bug reports, fixes, and feedback. If you have submitted a correction and don't
mind having your name/@ printed here please let me know (or if you'd like to change these details).

Contributors

* Olivier Nivoix
* Sarang Baheti <https://github.com/sarangbaheti>
* kevin
* Jon
* Julien Castelain <https://github.com/julien>
* Benjamin Summerton <https://github.com/define-private-public>
* Fwjrei
* guysherman
* 24kwakahana
* battila7
* Gnimuc <https://github.com/Gnimuc>
* Peter Getek <https://github.com/postfixNotation>
* Mikel Losada <https://github.com/Workshoft>
* Kevin Moran <https://github.com/kevinmoran>
* Jon <https://github.com/0xBAMA>
* Pablo Alonso-Villaverde Roza <https://github.com/pavroza>
