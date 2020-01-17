# DoraemonOS #

<img src="https://raw.githubusercontent.com/DoraemonOS/android_manifest/Quiche/DoraemonOS.jpeg"> 

Getting Started :
===============
To get started with the building process, you'll need to get familiar with [Git and Repo](http://source.android.com/source/using-repo.html).

Minimum computer :
```bash
   [CPU Intel] [X86_64] [8 Core] {Or Mainboard Dual Socket CPU}
   [Ram] [8Gb] [16Gb] [32Gb]
   [Rom] [500Gb] 
   [OS] [Ubuntu 14.04 64Bit] | [Ubuntu 16.04 64Bit] | [Later Versions 64Bit] | [Debian 64Bit]
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
```bash
   sudo apt-get install -y git-core gnupg flex bison gperf build-essential zip curl zlib1g-dev gcc-multilib g++-multilib libc6-dev-i386 lib32ncurses5-dev x11proto-core-dev libx11-dev lib32z-dev libgl1-mesa-dev libxml2-utils xsltproc unzip bc repo nano
```
And :
```bash
   sudo apt-get install -y git gnupg flex bison gperf build-essential zip curl zlib1g-dev gcc-multilib g++-multilib libc6-dev-i386 x11proto-core-dev libx11-dev libgl1-mesa-dev libxml2-utils xsltproc unzip bc repo nano libssl-dev
```
And :
```bash
   sudo apt-get install -y openjdk-8-jdk android-tools-adb bc bison build-essential curl flex g++-multilib gcc-multilib gnupg gperf imagemagick lib32readline-dev lib32z1-dev liblz4-tool libncurses5-dev libsdl1.2-dev libssl-dev libwxgtk3.0-dev libxml2 libxml2-utils lzop pngcrush rsync schedtool squashfs-tools xsltproc yasm zip zlib1g-dev
```
And :
```bash
   sudo apt-get install -y build-essential kernel-package libncurses5-dev bzip2 android-liblog android-libbacktrace libtinyxml2-6 android-libutils android-sdk-build-tools git-lfs libncurses5:i386 libncurses5 ccache
```

Repo Sync :
===========

Github Config Accmount :
```bash
   git config --global user.name "FIRST_NAME LAST_NAME"
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
   repo init -u https://github.com/DoraemonOS/android_manifest.git -b Quiche
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
   git clone -b Quiche https://github.com/DoraemonOS-Devices/device_xiaomi_whyred.git devive/xiaomi/whyred
   git clone -b Quiche https://github.com/DoraemonOS-Devices/vendor_xiaomi_whyred.git vendor/xiaomi/whyred
   git clone -b Quiche https://github.com/DoraemonOS-Devices/kernel_xiaomi_whyred.git kernel/xiaomi/whyred
   git clone -b Quiche https://github.com/DoraemonOS-Devices/vendor_MiuiCamera.git vendor/MiuiCamera
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
   brunch doraemon_<devicecodename>-userdebug
```
EX:
```bash
   Device : Xiaomi Redmi Note 5 Pro ( Whyred )
   Type : brunch doraemon_whyred-userdebug
   Or
   Type : brunch doraemon_whyred-eng
   Type : brunch doraemon_whyred-user
```



Compilation With Lunch :

```bash
   lunch doraemon_<devicecodename>-userdebug
```
EX:
```bash
   Device : Xiaomi Redmi Note 5 Pro ( Whyred )
   Type : lunch doraemon_whyred-userdebug
   Or
   Type : lunch doraemon_whyred-eng
   Type : lunch doraemon_whyred-user
```
```bash
   mka bacon -j$(nproc --all)
```


-----------------------------------------------------------------------------

 Credits :
=======
 * [**CyanogenMod**](https://github.com/Cyanogenmod)
 * [**LineageOS**](https://github.com/LineageOS)
 * [**LotusOS**](https://github.com/Lotus-OS)
 * [**pixel experience**](https://github.com/pixelexperience)
 * [**Cosmic**](https://github.com/Cosmic-OS)
 * [**AOSiP**](https://github.com/aosip)
 * [**bootlegger**](https://github.com/BootleggersROM)
 * [**CherishOS**](https://github.com/CherishOS)
 * [**AOSP**](https://android.googlesource.com)
 
 # Doraemon Maintainer : #
 * [**Nobi Nobita**](https://github.com/dopaemon)
 * [**Đinh San**](https://github.com/dinhsan2000)
 
 # Doraemon Channel + Group : #
 * [**Telegram-Channel**](https://t.me/DoraemonOS)
 * [**Telegram-Group**](https://t.me/DoraemonOS_Chat)
 * [**Facebook Nobi Nobita**](https://facebook.com/nobita.developer)
 * [**Facebook Đinh San**](https://facebook.com/profile.php?id=100007847622202)
 

