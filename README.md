# onscripter-jh-gameshell
About [WIP] My ONScripter-jh ‌ClockworkPi GameShell port

## References  
* onscripter_jh_sdl2_fork-master_v11.tar.gz

## How to build onscripter-jh by static link      
```
cd /home/cpi/work/

# bzip2
tar xzf bzip2-1.0.4.tar.gz
cd bzip2-1.0.4/
make
mkdir ../../jh
mkdir ../../jh/lib
mkdir ../../jh/include
cp *.a ../../jh/lib
cp *.h ../../jh/include 
cd ..

-------------

# zlib
tar xzf zlib-1.2.3.tar.gz
cd zlib-1.2.3/
./configure --prefix=/home/cpi/jh
make
make install
cd ..

# png
tar xzf libpng-1.2.24.tar.gz
cd libpng-1.2.24/
./configure --prefix=/home/cpi/jh --enable-static --disable-shared
make
make install
cd ..

# jpeg, not support libtool
tar xzf jpegsrc.v6b.tar.gz
cd jpeg-6b/
mkdir ../../jh/man
mkdir ../../jh/man/man1
./configure
make
cp *.a ../../jh/lib/
cp *.h ../../jh/include/
cd ..

# freetype
tar xzf freetype-2.3.5.tar.gz
cd freetype-2.3.5/
./configure --prefix=/home/cpi/jh --enable-static --disable-shared
make
make install
cd ..

# ogg
tar xzf libogg-1.1.3.tar.gz
cd libogg-1.1.3/
./configure --prefix=/home/cpi/jh --enable-static --disable-shared
make
make install
cd ..

--------------

# vorbis
tar xzf libvorbis-1.2.0.tar.gz
cd libvorbis-1.2.0/
./configure --prefix=/home/cpi/jh --enable-static --disable-shared
make
make install
cd ..

# SDL2
#./configure -prefix=/home/cpi/jh --disable-shared --enable-static

# SDL2_image
tar xzf SDL2_image-2.0.5.tar.gz
cd SDL2_image-2.0.5/
./configure -prefix=/home/cpi/jh --disable-shared --enable-static
make
make install
cd ..

# SDL2_ttf
tar xzf SDL2_ttf-2.0.15.tar.gz
cd SDL2_ttf-2.0.15/
FT2_CONFIG=/home/cpi/jh/bin/freetype-config ./configure -prefix=/home/cpi/jh --disable-shared --enable-static
make
make install
cd ..

# SDL2_mixer
tar xzf SDL2_mixer-2.0.4.tar.gz
cd SDL2_mixer-2.0.4/
./configure -prefix=/home/cpi/jh --disable-shared --enable-static
make
make install
cd ..

# smpeg2
tar xzf smpeg2-2.0.0.tar.gz
cd smpeg2-2.0.0/
CPPFLAGS=-Wno-narrowing ./configure -prefix=/home/cpi/jh --disable-shared --enable-static
make
make install
cd ..

-------------------

# onscripter-jh
cd onscripter_jh_sdl2_fork-master
#modify Makefile, INCS and LIBS and -DMIYOO (not use -DPDA_WIDTH=320) 
PATH=/home/cpi/jh/bin:$PATH make


```
