---
author: jet
categories:
- Hardware
- Internet
- Mozilla
- Open Source
- Software
date: "2015-02-11T19:39:21Z"
guid: http://junglecode.net/?p=190
id: 190
title: FirefoxOS Dev Quick Start
url: /firefoxos-dev-quick-start/
---

[![B2G_dev_env](http://junglecode.net/wp-content/uploads/sites/2/2015/02/B2G_dev_env.jpg)](http://junglecode.net/wp-content/uploads/sites/2/2015/02/B2G_dev_env.jpg)I’m posting the steps I took to create the FirefoxOS dev environment for the [Flame](https://developer.mozilla.org/en-US/Firefox_OS/Phone_guide/Flame/Updating_your_Flame "Updating Flame") device. We use the Flame as our reference device on the Platform Rendering team. I had to re-do this recently on a new computer and I figure this might help others in the same boat. These steps assume you can already [build the desktop version](https://developer.mozilla.org/en-US/docs/Simple_Firefox_build "desktop build instructions") of Firefox on your computer.

1. [Get ADB](https://developer.mozilla.org/en-US/Firefox_OS/Debugging/Installing_ADB "ADB tools")
2. Turn on [ADB debugging](https://developer.mozilla.org/en-US/Firefox_OS/Debugging/Developer_settings "Debugger Settings") on your device.
3. [Download the latest base image](https://developer.mozilla.org/en-US/Firefox_OS/Phone_guide/Flame/Updating_your_Flame "Download Base Image") (v18D\_nightly.zip at the time of this writing.)
4. Unzip the base image archive and run the flash.sh script to update your phone to the latest base image. You’ll need to re-enable ADB debugging after this step.
5. [Clone the B2G repository](https://developer.mozilla.org/en-US/Firefox_OS/Preparing_for_your_first_B2G_build "git clone B2G") and follow the prerequisite steps for local builds.  
    Note: the device we target for the config.sh step is flame-kk (not the older flame device.)
6. Get a coffee and wait for the long source download.
7. Run ./build.sh in the B2G source directory to build.
8. Run ./flash.sh in the B2G source directory to put your new build on to your phone.