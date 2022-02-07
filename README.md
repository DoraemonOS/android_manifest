# DoraemonOS #

<img src="https://raw.githubusercontent.com/DoraemonOS/android_manifest/Quiche/DoraemonOS.jpeg"> 

Getting Started :
===============
To get started with the building process, you'll need to get familiar with [Git and Repo](http://source.android.com/source/using-repo.html).

Minimum computer :
```bash
[CPU Intel | AMD] [X86_64] [Min 8 Core]
[Ram] [Min 16Gb]
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
You need Linker python3:
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
