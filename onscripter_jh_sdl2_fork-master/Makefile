# -*- Makefile -*-
#
# Makefile.Linux - Makefile rules for linux
#

EXESUFFIX =
OBJSUFFIX = .o

.SUFFIXES:
.SUFFIXES: $(OBJSUFFIX) .cpp .h

TARGET = onscripter$(EXESUFFIX) \
	sardec$(EXESUFFIX) \
	nsadec$(EXESUFFIX) \
	sarconv$(EXESUFFIX) \
	nsaconv$(EXESUFFIX) 
EXT_OBJS = 

# mandatory: SDL, SDL_ttf, SDL_image, SDL_mixer, bzip2
DEFS = -DLINUX -DUSE_SDL_RENDERER -DNDEBUG -DMIYOO
INCS = `sdl2-config --cflags` -I/home/cpi/jh/include -I/home/cpi/jh/include/SDL2
LIBS = `sdl2-config --libs` -L/home/cpi/jh/lib -lSDL2_ttf -lSDL2_image -lSDL2_mixer -ljpeg -lpng -lfreetype -lbz2 -lm -lz
EXT_FLAGS = 

# recommended: smpeg
#DEFS += -DUSE_SMPEG
#INCS += `smpeg-config --cflags`
#LIBS += `smpeg-config --libs`

# recommended: fontconfig (to get default font)
#DEFS += -DUSE_FONTCONFIG
#LIBS += -lfontconfig

# recommended: OggVorbis 
DEFS += -DUSE_OGG_VORBIS
LIBS += -logg -lvorbis -lvorbisfile

# optional: Integer OggVorbis
#DEFS += -DUSE_OGG_VORBIS -DINTEGER_OGG_VORBIS
#LIBS += -lvorbisidec

# optional: support CD audio
#DEFS += -DUSE_CDROM

# optional: avifile
#DEFS += -DUSE_AVIFILE
#INCS += `avifile-config --cflags`
#LIBS += `avifile-config --libs`
#TARGET += simple_aviplay$(EXESUFFIX)
#EXT_OBJS += AVIWrapper$(OBJSUFFIX)

# optional: lua
#DEFS += -DUSE_LUA
#INCS += -I/usr/include/lua
#LIBS += -llua
#EXT_OBJS += LUAHandler$(OBJSUFFIX)

# optional: SIMD optimizing
#DEFS += -DUSE_SIMD -DUSE_SIMD_X86_SSE2

# optional: multicore rendering
#DEFS += -DUSE_OMP_PARALLEL
#EXT_FLAGS += -fopenmp

# optional: enable builtin effects
DEFS += -DUSE_BUILTIN_EFFECTS -DUSE_BUILTIN_LAYER_EFFECTS


# optional: enable English mode
#DEFS += -DENABLE_1BYTE_CHAR -DFORCE_1BYTE_CHAR


# for GNU g++
CC = g++ 
LD = g++ -o

#CFLAGS = -g -Wall -pipe -c $(INCS) $(DEFS)
CFLAGS = -std=c++11 -O3 -Wall -fomit-frame-pointer -pipe -c $(INCS) $(DEFS) $(EXT_FLAGS)

# for GCC on PowerPC specfied
#CC = powerpc-unknown-linux-gnu-g++
#LD = powerpc-unknown-linux-gnu-g++ -o

#CFLAGS = -O3 -mtune=G4 -maltivec -mabi=altivec -mpowerpc-gfxopt -mmultiple -mstring -Wall -fomit-frame-pointer -pipe -c $(INCS) $(DEFS)

# for Intel compiler
#CC = icc
#LD = icc -o

#CFLAGS = -O3 -tpp6 -xK -c $(INCS) $(DEFS)

RM = rm -f

include Makefile.onscripter

run:
	./onscripter -r ../onscripter_cn_test/

#win+f: fullscreen

