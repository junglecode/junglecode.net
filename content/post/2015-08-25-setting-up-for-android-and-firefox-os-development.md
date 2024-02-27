---
author: jet
categories:
- Hardware
- Internet
- Mozilla
- Open Source
- Software
date: "2015-08-25T09:03:21Z"
guid: http://junglecode.net/?p=200
id: 200
title: Setting up for Android and Firefox OS Development
url: /setting-up-for-android-and-firefox-os-development/
---

This post is a follow-up to an earlier article I wrote about [setting up a FirefoxOS development environment](http://junglecode.net/firefoxos-dev-quick-start/ "FirefoxOS Dev Quick Start").

I’m going to set up a Sony Z3C as the target device for Mobile OS software development. The Sony Z3C (also known as [Aries](https://github.com/sonyxperiadev/device-sony-aries "Sony Aries on Github") or aosp\_d5803 ) is a nice device for Mobile OS hacking as it’s an [AOSP device](http://developer.sonymobile.com/knowledge-base/open-source/open-devices/ "Sony & AOSP ") with good support for building the OS binaries. I’ve set the phone up for both FirefoxOS and Android OS development, to compare and see what’s common across both environments.

Please note that if you got your Sony Z3C from the Mozilla Foxfooding program, then this article isn’t for you. Those phones are already flashed and automatically updated with specific FirefoxOS builds that Mozilla staff selected for your testing. Please don’t replace those builds unless you’re actively developing for these phones and have a device set aside for that purpose.

My development host is a Mac (OSX 10.10) laptop already [set up to build](https://developer.mozilla.org/en-US/docs/Simple_Firefox_build) the Firefox for Macintosh product. It’s also set up to [build the Firefox OS](https://developer.mozilla.org/en-US/Firefox_OS/Building_and_installing_Firefox_OS/Building_for_Flame_on_OS_X) binaries for the Flame device.

Most of the development environment for the Flame is also used for the Aries device. In particular, the case-sensitive disk partition is required for both FirefoxOS and Android OS development. You’ll want this partition to be at least 100GB in size if you want to build both operating systems. Set this up before downloading FirefoxOS or Android souce code to avoid ‘include file not found’ errors.

The next step to developing OS code for the Aries is to [root the device](http://developer.sonymobile.com/unlockbootloader/unlock-yourboot-loader/). This will void your warranty, so tread carefully.

For most Gecko and Gaia developers, you’ll want to start from the base image for the Aries. The easiest way to flash your device with a known-good FirefoxOS build is to run flash.sh in the expanded [aries.zip file from the official builds](https://tools.taskcluster.net/task-inspector/#i1V1E5ewTwSKwjssMBK8XA/0). You can then flash the phone with just Gecko or Gaia from your local source code.

The Aries binaries from a FirefoxOS build:

[![aries_firefoxos_images](http://junglecode.net/wp-content/uploads/sites/2/2015/08/aries_firefoxos_images-300x104.png)](http://junglecode.net/wp-content/uploads/sites/2/2015/08/aries_firefoxos_images.png)

The Aries binaries in an Android Lollipop build:

[![aries_android_images](http://junglecode.net/wp-content/uploads/sites/2/2015/08/aries_android_images-300x75.png)](http://junglecode.net/wp-content/uploads/sites/2/2015/08/aries_android_images.png)

If you want to build Android OS for the Aries, then read [these docs from Sony](http://developer.sonymobile.com/knowledge-base/open-source/open-devices/aosp-build-instructions/how-to-build-aosp-lollipop-for-unlocked-xperia-devices/), and these [Mac-specific steps for building Android Lollipop](https://medium.com/@raminmahmoodi/build-android-5-0-lollipop-on-osx-10-10-yosemite-441bd00ee77a). Note that the Android Lollipop SDK requires XCode 5.1.1 and Java 7 (JRE and JDK.) Both versions of XCode and Java are older than the latest versions available, so you’ll need to install the downgrades before building the Android OS.

When it comes time to configure your Android OS build via the *lunch* command, select *aosp\_d5803-userdebug* as your device. Once the build is finished (after about 2 hours on my Mac,) use these commands to flash your phone with the Android OS you just built:

*fastboot flash boot out/target/product/aries/boot.img*  
*fastboot flash system out/target/product/aries/system.img*  
*fastboot flash userdata out/target/product/aries/userdata.img*