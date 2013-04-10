CFLAGS += -Wall
CPPFLAGS += $(shell pkg-config --cflags fuse)
CPPFLAGS += -DFUSE_USE_VERSION=26
CPPFLAGS += -DHAVE_XATTR
INC = -I/home/user/unionfs-fuse/fuse-android/jni/include -I/home/lpizzagalli/android-standalone-toolchain/sysroot/usr/include
CPPFLAGS += $(INC)
CPPFLAGS += -D_FILE_OFFSET_BITS=64
AR=/home/user/android-standalone-toolchain/bin/arm-linux-androideabi-ar
SYS_ROOT=/home/user/android-standalone-toolchain/sysroot
LD=/home/user/android-standalone-toolchain/bin/arm-linux-androideabi-ld
CC=/home/user/android-standalone-toolchain/bin/arm-linux-androideabi-gcc


LDFLAGS =/home/user/unionfs-fuse/fuse-android/obj/local/armeabi/libfuse.a -L/home/lpizzagalli/devices/m10_ionik/ionik_again/out/target/product/a_devise/system/lib 

HASHTABLE_OBJ = hashtable.o hashtable_itr.o
UNIONFS_OBJ = unionfs.o stats.o opts.o debug.o findbranch.o readdir.o \
		general.o unlink.o rmdir.o cow.o cow_utils.o string.o \
		usyslog.o


unionfs: $(UNIONFS_OBJ) $(HASHTABLE_OBJ) version.h
	$(CC) -o $@ $(UNIONFS_OBJ) $(HASHTABLE_OBJ) $(LDFLAGS) $(LIB) 

clean:
	rm -f unionfs
	rm -f *.o
