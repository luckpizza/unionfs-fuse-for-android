HOWTO

Requirements:<br/>
	- (1) android NDK <br/>
	- (2) standalone android toolchain (this can be generated with the regular android-NDK) <br/>
	- (3) a compiled android sourcecode (preferable of the target device) <br/>
<br/>
Steps:<br/>
	1. Compile fuse for android under the /fuse-android folder (using the android ndk (1)) <br/>
	2. export ANDROID_STANDALONE_TOOLCHAIN=\<PATH_TO_ANDROID_TOOLCHAIN(2)\> <br/>
	3. export ANDROID_OUT_SYSTEM=\<PATH_TO_ANDROID_OUT_SYSTEM(3)\> <br/>
	4.  make <br/>
<br/>
Enjoy! <br/>

Examples:<br/>
```
cd ~
git clone https://github.com/luckpizza/unionfs-fuse-for-android.git
cd ~/unionfs-fuse-for-android
cd fuse-android
~/android-ndk-r8e/ndk-build 
cd ..
export ANDROID_OUT_SYSTEM=/home/user/android/out/product/target/my_device/system
export ANDROID_OUT_SYSTEM=/home/user/androidstandalone-toolchain
make
```
you should find the binary file under src/unionfs 
