# DoraemonOS #

<img src="https://raw.githubusercontent.com/DoraemonOS/android_manifest/Quiche/DoraemonOS.jpeg"> 

Getting Started :
===============
To get started with the building process, you'll need to get familiar with [Git and Repo](http://source.android.com/source/using-repo.html).

Minimum computer :
```bash
   [CPU Intel] [X86_64] [>4 Core]
   [Ram] [16Gb] [32Gb]
   [SSD|HDD] [320Gb] 
   [OS] [Ubuntu 14.04 64Bit] | [Ubuntu 16.04 64Bit] | [Ubuntu 18.04 64Bit] | [Ubuntu 19.04 64Bit] | [Ubuntu 20.04 64Bit] | [Ubuntu 21.04 64Bit] | [Later Versions 64Bit] | [Debian 64Bit]
```

Package : 
Enable I386 Packages :
```bash
   sudo dpkg --add-architecture i386
```
Update Source Packages :
```bash
   sudo apt-get update
```
Upgrade Source Packages :
```bash
   sudo apt-get upgrade -y
```
Install Packages :
Tested on Ubuntu 16.04,16.10,17.04,18.04,18.10,19.04,21.04:
```bash
   sudo apt install openjdk-8-jdk python bc bison build-essential ccache curl flex g++-multilib gcc-multilib git gnupg gperf imagemagick lib32ncurses5-dev lib32readline-dev lib32z1-dev liblz4-tool libncurses5-dev libsdl1.2-dev libssl-dev libwxgtk3.0-dev libxml2 libxml2-utils lzop pngcrush rsync schedtool squashfs-tools xsltproc zip zlib1g-dev
```
Tested on Ubuntu 20.04:
```bash
   sudo apt install openjdk-8-jdk python bc bison build-essential ccache curl flex g++-multilib gcc-multilib git gnupg gperf imagemagick lib32ncurses5-dev lib32readline-dev lib32z1-dev liblz4-tool libncurses5-dev libsdl1.2-dev libssl-dev libwxgtk3.0-gtk3-dev libxml2 libxml2-utils lzop pngcrush rsync schedtool squashfs-tools xsltproc zip zlib1g-dev
```
Repo Sync :
===========

Github Config Accmount :
```bash
   git config --global user.name "USERNAME"
```
```bash
   git config --global user.email "MY_NAME@example.com"
```
Bin :
```bash
   mkdir ~/bin
```
```bash
   PATH=~/bin:$PATH
``` 
```bash
   curl https://storage.googleapis.com/git-repo-downloads/repo > ~/bin/repo
```
```bash
   chmod a+x ~/bin/repo
```

To initialize your local repository, use a command like this:
```bash
   mkdir -p ~/android
```
```bash
   cd ~/android
```

```bash
   repo init -u https://github.com/DoraemonOS/android_manifest.git -b 11
```

```bash
   repo sync -c -j$(nproc --all) --force-sync --no-clone-bundle --no-tags
```

Additionally, you can define the number of parallel download repo should do:

```bash
   repo sync -f -j$(nproc --all) --force-sync --no-clone-bundle --no-tags
```
Or Packages Repo Full :

```bash
   repo sync -j$(nproc --all)
```
# Devices Tree #
And Git Clone Device Tree / Vendor / Kernel :
Source Device Tree :

   [**Device Tree**](https://github.com/DoraemonOS-Devices)
```bash
   Device Tree : ~/repo/device/xxx/yyy
   Vendor : ~/repo/vendor/xxx/yyy
   Kernel : ~/repo/kernel/xxx/yyy
```
```bash
   xxx = brand
   yyy = codename
```
EX:
```bash
   Device : Xiaomi Redmi Note 5 Pro ( Whyred )
   Device Tree : ~/repo/device/xiaomi/whyred
   Vendor : ~/repo/vendor/xiaomi/whyred
   Kernel : ~/repo/kernel/xiaomi/whyred
```
Pack Tree :
```bash
   Xiaomi Redmi Note 5 Pro ( Whyred )
```
```bash
   git clone -b 11 https://github.com/DoraemonOS-Devices/device_xiaomi_whyred.git devive/xiaomi/whyred
   git clone -b 11 https://github.com/DoraemonOS-Devices/vendor_xiaomi_whyred.git vendor/xiaomi/whyred
   git clone -b 11 https://github.com/DoraemonOS-Devices/kernel_xiaomi_whyred.git kernel/xiaomi/whyred
   git clone -b 11 https://github.com/DoraemonOS-Devices/vendor_MiuiCamera.git vendor/MiuiCamera
```

Compilation of DoraemonOS :
====================

From root directory of Project, perform following commands in terminal

Use Ccache :
```bash
   ccache -M 50G ( For 50Gb )
```
```bash
   export USE_CCACHE=1
```
```bash
   export CCACHE_DIR=ccache
```
```bash
   export ANDROID_JACK_VM_ARGS="-Dfile.encoding=UTF-8 -XX:+TieredCompilation -Xmx4G"
```
```bash
   export LC_ALL=C
```

Source Terminal :
```bash
   source build/envsetup.sh
```

Compilation With Brunch :

```bash
   brunch aosp_<devicecodename>-userdebug
```
EX:
```bash
   Device : Xiaomi Redmi Note 5 Pro ( Whyred )
   Type : brunch aosp_whyred-userdebug
   Or
   Type : brunch aosp_whyred-eng
   Type : brunch aosp_whyred-user
```

Compilation With Lunch :

```bash
   lunch aosp_<devicecodename>-userdebug
```
EX:
```bash
   Device : Xiaomi Redmi Note 5 Pro ( Whyred )
   Type : lunch aosp_whyred-userdebug
   Or
   Type : lunch aosp_whyred-eng
   Type : lunch aosp_whyred-user
```
```bash
   mka bacon -j$(nproc --all)
```

-----------------------------------------------------------------------------

 Credits :
=======
 * [**CyanogenMod**](https://github.com/Cyanogenmod)
 * [**LineageOS**](https://github.com/LineageOS)
 * [**CherishOS**](https://github.com/CherishOS)
 * [**LotusOS**](https://github.com/Lotus-OS)
 * [**pixel experience**](https://github.com/pixelexperience)
 * [**Cosmic**](https://github.com/Cosmic-OS)
 * [**AOSiP**](https://github.com/aosip)
 * [**bootlegger**](https://github.com/BootleggersROM)
 * [**CherishOS**](https://github.com/CherishOS)
 * [**AOSP**](https://android.googlesource.com)
