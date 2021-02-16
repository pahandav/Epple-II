This is my own custom build of Christopher Mosher's Epple II emulator using msys2.

It includes everything from the official build, with PDF versions of the documentation and a static build of the Dsk2WOZ program, so you can convert disk images to WOZ format.

Bugs fixed:

I added a couple of includes and changed the Makefile so it would build with 64-bit Windows msys2.

This version also fixes the crackling sound from the official version (and I didn't have to change anything this time - it must have been a bug in SDL that's been fixed)

Building your own copy:

Install msys2.

Run the following command to install dependencies:

pacman -S --needed base-devel mingw-w64-i686-toolchain mingw-w64-x86_64-toolchain mingw-w64-x86_64-SDL2 make wget git mingw-w64-x86_64-clang mingw-w64-x86_64-clang-tools-extra

Then, open a 32-bit msys2 window and run the following:

wget https://www.floodgap.com/retrotech/xa/dists/xa-2.3.11.tar.gz
tar xzvf xa-2.3.11.tar.gz
cd xa-2.3.11
make mingw
make install

Finally, open a 64-bit msys2 window and run the following from your copy of the repo:

./bootstrap
./configure
make -f Makefile.mingw