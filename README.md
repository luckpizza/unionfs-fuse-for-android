HOWTO

Requirements:<br/>
	- (1) android NDK <br/>
	- (2) standalone android toolchain (this can be generated with the regular android-NDK) <br/>
<br/>
Steps:<br/>
	1. Compile fuse for android under the /fuse-android folder (using the android ndk (1)) <br/>
	2. export ANDROID_STANDALONE_TOOLCHAIN=\<PATH_TO_ANDROID_TOOLCHAIN(2)\> <br/>
	3.  make <br/>
<br/>
Enjoy! <br/>

Examples:<br/>
```
cd ~
git clone ssh://dev.zertisa.com/opt/sources/git/unionfs-fuse-zertisa
cd ~/unionfs-fuse-zertisa
cd fuse-android
~/android-ndk-r8e/ndk-build 
cd ..
export ANDROID_STANDALONE_TOOLCHAIN==/home/user/androidstandalone-toolchain
make
```
you should find the binary file under src/unionfs 
