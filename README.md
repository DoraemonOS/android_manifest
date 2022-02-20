# DoraemonOS #

<img src="https://raw.githubusercontent.com/DoraemonOS/.github/12/profile/README.png"> 

Getting Started :
===============
To get started with the building process, you'll need to get familiar with [Git and Repo](http://source.android.com/source/using-repo.html).

Minimum computer :
```bash
[CPU Intel | AMD] [64Bit] [Min 8 Core]
[Ram] [Min 16Gb]
[SSD | HDD | nvme] (Min[320Gb])
[Ubuntu 14.04 64Bit]
To
[Ubuntu 21.04 64Bit]
Or
[Later Ubuntu Versions 64Bit]
Or
[Debian 64Bit]
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
You need Linker python3:
```bash
sudo mv /usr/bin/python /usr/bin/python2
```
```bash
sudo ln -s /usr/bin/python3 /usr/bin/python
```
Repo Sync :
===========

Github Config Accmount :
```bash
git config --global user.name "username"
```
```bash
git config --global user.email "username@example.com"
```
Install repo [ bin folder ]
```bash
curl https://storage.googleapis.com/git-repo-downloads/repo > ~/repo
```
```bash
chmod a+x ~/repo
```
```bash
sudo mv ~/repo /usr/bin/
```

To initialize your local repository, use a command like this:
```bash
mkdir -p ~/android
```
```bash
cd ~/android
```

```bash
repo init -u https://github.com/DoraemonOS/android_manifest.git -b 12
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
git clone -b 12 https://github.com/DoraemonOS-Devices/device_xiaomi_whyred.git devive/xiaomi/whyred
git clone -b 12 https://github.com/DoraemonOS-Devices/vendor_xiaomi_whyred.git vendor/xiaomi/whyred
git clone -b 12 https://github.com/DoraemonOS-Devices/kernel_xiaomi_whyred.git kernel/xiaomi/whyred
```

Compilation of DoraemonOS :
====================

From root directory of Project, perform following commands in terminal

If you use Ubuntu 18.04 i think you need this:
```bash
export LC_ALL=C
```

Source Terminal :
```bash
source build/envsetup.sh
```

Compilation With Brunch :

```bash
brunch dora_<devicecodename>-userdebug
```
EX:
```bash
Device : Xiaomi Redmi Note 5 Pro ( Whyred )
Type : brunch dora_whyred-userdebug
Or
Type : brunch dora_whyred-eng
Type : brunch dora_whyred-user
```

Compilation With Lunch :
```bash
lunch dora_<devicecodename>-userdebug
```
```bash
mka bacon -j$(nproc --all)
```
EX:
```bash
Device : Xiaomi Redmi Note 5 Pro ( Whyred )
Type : lunch dora_whyred-userdebug
Or
Type : lunch dora_whyred-eng
Type : lunch dora_whyred-user
```
```bash
mka bacon -j$(nproc --all)
```
⚠️⚠️⚠️
You need add some stuff to dora_codename.mk for build:
```bash
DORA_BUILD_TYPE := OFFICIAL or UNOFFICIAL
DORA_MAINTAINER := You Name
```
-----------------------------------------------------------------------------

 Credits :
=======
 * [**CyanogenMod**](https://github.com/Cyanogenmod)
 * [**LineageOS**](https://github.com/LineageOS)
 * [**CherishOS**](https://github.com/CherishOS)
 * [**LotusOS**](https://github.com/Lotus-OS)
 * [**Pixel Experience**](https://github.com/pixelexperience)
 * [**Proton AOSP**](https://github.com/ProtonAOSP)
 * [**GrapheneOS**](https://github.com/GrapheneOS)
 * [**CalyxOS**](https://gitlab.com/CalyxOS)
 * [**ABC**](https://github.com/ezio84)
 * [**Cosmic**](https://github.com/Cosmic-OS)
 * [**AOSiP**](https://github.com/aosip)
 * [**bootlegger**](https://github.com/BootleggersROM)
 * [**DerpFest 12**](https://github.com/DerpFest-12)
 * [**AOSP**](https://android.googlesource.com)
 * [**Some AOSP Custom Projects**](https://github.com/)
