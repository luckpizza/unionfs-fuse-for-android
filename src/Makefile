#Getting from env the locations of the toolchain and compiled android source
ANDROID_STANDALONE_TOOLCHAIN := $(shell echo $(ANDROID_STANDALONE_TOOLCHAIN))
ANDROID_OUT_SYSTEM := $(shell echo $(ANDROID_OUT_SYSTEM))
############################################################################

CFLAGS += -Wall
CPPFLAGS += $(shell pkg-config --cflags fuse)
CPPFLAGS += -DFUSE_USE_VERSION=26
CPPFLAGS += -DHAVE_XATTR
INC = -I../fuse-android/jni/include -I$(ANDROID_STANDALONE_TOOLCHAIN)/sysroot/usr/include
CPPFLAGS += $(INC)
CPPFLAGS += -D_FILE_OFFSET_BITS=64
AR = $(ANDROID_STANDALONE_TOOLCHAIN)/bin/arm-linux-androideabi-ar
SYS_ROOT = $(ANDROID_STANDALONE_TOOLCHAIN)/sysroot
LD = $(ANDROID_STANDALONE_TOOLCHAIN)/bin/arm-linux-androideabi-ld
CC = $(ANDROID_STANDALONE_TOOLCHAIN)/bin/arm-linux-androideabi-gcc


LDFLAGS =../fuse-android/obj/local/armeabi/libfuse.a -L$(ANDROID_OUT_SYSTEM)/lib 

HASHTABLE_OBJ = hashtable.o hashtable_itr.o
UNIONFS_OBJ = unionfs.o stats.o opts.o debug.o findbranch.o readdir.o \
		general.o unlink.o rmdir.o cow.o cow_utils.o string.o \
		usyslog.o


unionfs: $(UNIONFS_OBJ) $(HASHTABLE_OBJ) version.h
	$(CC) -o $@ $(UNIONFS_OBJ) $(HASHTABLE_OBJ) $(LDFLAGS) $(LIB) 

clean:
	rm -f unionfs
	rm -f *.o
