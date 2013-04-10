HOWTO

Requirements:
	- (1) android NDK 
	- (2) standalone android toolchain (this can be generated with the regular android-NDK)
	- (3) a compiled android sourcecode (preferable of the target device)
Steps:

	- Compile fuse for android under the /fuse-android folder (using the android ndk)
	- export ANDROID_STANDALONE_TOOLCHAIN=<PATH_TO_ANDROID_TOOLCHAIN(2)> 
	- export ANDROID_OUT_SYSTEM=<PATH_TO_ANDROID_OUT_SYSTEM(3)>
	- make

Enjoy! 

Examples:

cd fuse-android
~/android-ndk-r8e/ndk-build 
cd ..
export ANDROID_OUT_SYSTEM=/home/user/android/out/product/target/my_device/system
export ANDROID_OUT_SYSTEM=/home/user/androidstandalone-toolchain
make

you should find the binary file under src/unionfs 
