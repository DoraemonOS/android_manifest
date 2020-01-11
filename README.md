# DoraemonOS #

<img src="https://raw.githubusercontent.com/DoraemonOS/android_manifest/Quiche/DoraemonOS.jpeg"> 

Getting Started:
===============
To get started with the building process, you'll need to get familiar with [Git and Repo](http://source.android.com/source/using-repo.html).

OS : Ubuntu ( Debian ) 64Bit ( Version 14. )

Package : 
```bash
sudo apt-get install git-core gnupg flex bison gperf build-essential zip curl zlib1g-dev gcc-multilib g++-multilib libc6-dev-i386 lib32ncurses5-dev x11proto-core-dev libx11-dev lib32z-dev libgl1-mesa-dev libxml2-utils xsltproc unzip
```


To initialize your local repository, use a command like this:

```bash
    repo init -u https://github.com/DoraemonOS/android_manifest.git -b Quiche
```

Then to sync up:
================

```bash
    repo sync -c -j$(nproc --all) --force-sync --no-clone-bundle --no-tags
```

Additionally, you can define the number of parallel download repo should do:

```bash
    repo sync -f -j$(nproc --all) --force-sync --no-clone-bundle --no-tags
```

Compilation of DoraemonOS :
====================

From root directory of Project, perform following commands in terminal


```bash
source build/envsetup.sh
```
```bash
lunch aosp_<devicecodename>-userdebug
```
```bash
mka bacon -j$(nproc --all)
```
-----------------------------------------------------------------------------

 Credits:
=======
 * [**CyanogenMod**](https://github.com/Cyanogenmod)
 * [**LineageOS**](https://github.com/LineageOS)
 * [**LotusOS**](https://github.com/Lotus-OS)
 * [**pixel experience**](https://github.com/pixelexperience)
 * [**Cosmic**](https://github.com/Cosmic-OS)
 * [**AOSiP**](https://github.com/aosip)
 * [**bootlegger**](https://github.com/BootleggersROM)
 * [**AOSP**](https://android.googlesource.com)
 * [**CherishOS**](https://github.com/CherishOS)
 
 # Doraemon Maintainer #
 * [**Nobi Nobita**](https://github.com/dopaemon)
 * [**Đinh Trọng San - dinh san**](https://github.com/dinhsan2000)



