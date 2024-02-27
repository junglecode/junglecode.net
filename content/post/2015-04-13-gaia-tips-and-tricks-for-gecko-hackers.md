---
author: jet
categories:
- Internet
- Mozilla
- Open Source
- Software
date: "2015-04-13T17:28:00Z"
guid: http://junglecode.net/?p=196
id: 196
title: Gaia Tips and Tricks for Gecko Hackers
url: /gaia-tips-and-tricks-for-gecko-hackers/
---

I’m often assigned Firefox Rendering bugs in [bugzilla](https://bugzilla.mozilla.org/buglist.cgi?bug_status=UNCONFIRMED&bug_status=NEW&bug_status=ASSIGNED&bug_status=REOPENED&emailassigned_to1=1&emailreporter1=1&emailtype1=exact&email1=bugs%40junglecode.net&field0-0-0=bug_status&type0-0-0=notequals&value0-0-0=UNCONFIRMED&field0-0-1=reporter&type0-0-1=equals&value0-0-1=bugs%40junglecode.net&list_id=12177538 "My bugzilla bugs"). By the time a bug gets assigned to me, the reporter had usually exhausted other options and assumed (correctly) that I’m ultimately responsible for fixing Firefox rendering bugs. Of course, I often have to reassign most bugs to more capable individuals.

Some of the hardest bugs to assign are the ones reported by our own [Gaia](https://github.com/mozilla-b2g/gaia/ "Gaia sources") team: the team responsible for building the user experience in Firefox OS. The Gaia engineers take CSS and JavaScript and build powerful mobile apps like the [phone dialer](https://github.com/mozilla-b2g/gaia/tree/master/apps/communications/dialer "Gaia phone dialer") and [SMS client](https://github.com/mozilla-b2g/gaia/tree/master/apps/sms "Gaia SMS"). When they report bugs, it’s often found within lots of CSS and JS code. I wanted to learn how to effectively reduce the time it takes to resolve rendering issues reported by the Gaia team. It takes a long time to go from a Gaia bug like “scrolling in the gallery app is slow” to find the underlying Gecko bug, for example “rounding issue creates an invalidation rectangle that is too large.”

To do that, I became a Gaia developer for a few days at our Paris office. I reasoned that if I could learn how they work, then I can help my team boil down issues faster and become more responsive to their needs. We already recognize the value of having expert web application developers on staff, but we could do a better job with a better understanding of how they work. With that in mind, I spent the week without any C++ code to look at, and dived into the world of mobile web app development.

I wrote down the steps I took to set up a FirefoxOS build and test environment in [an earlier post](http://junglecode.net/firefoxos-dev-quick-start/ "FirefoxOS Dev Quick Start") This time, I’ll list a few of the tips and tricks I learned while I was working with the Gaia developers.

The first and most important tip: You will brick the phone when working on the OS. In fact, you’re probably not trying hard enough if you don’t brick it 🙂 Fastboot lets you connect ADB to the phone when it becomes unresponsive to flash the device with a known good system (like the base image.) Learn how to [manually force fastboot](http://www.enodev.fr/restore-flame-software.html "Manula Fastboot for Flame devices") on your phone.

[Julien](https://github.com/julienw "Julien Wajsberg") showed me how to maintain a Gaia developer profile on your desktop development environment. This set of commands will configure your B2G build to produce the desktop B2G runtime that’s a bit easier to debug than a device build:

```
# change value of the FIREFOX to point to the full path to the B2G desktop build
 export FIREFOX=/Volumes/firefoxos/B2G/build/dist/B2G.app/Contents/MacOS/b2g
 export PROFILE_FOLDER=gaia-profile DEBUG=1 DESKTOP=0
 make
```

With a Gaia developer profile, you can switch between B2G desktop and a regular Firefox browser build for testing:

```
export FIREFOX=/full/path/to/desktop/browser
 $FIREFOX -profile gaia-profile --no-remote app://sms.gaiamobile.org
```

The Gaia profile lets you use URL’s like app://sms.gaiamobile.org to run the Gaia apps on the desktop browser. This trick alone was a huge time saver! Try it with other URL’s like app://communications.gaiamobile.org

For a first Gaia development project, I picked up the implementation of the [new card view for gaia](https://github.com/jetvillegas/gaia/tree/APZC-card-view "APZC-based card view") that is based on an asynchronous panning and zooming (APZC.) [Etienne](https://github.com/etiennesegonzac/ "Etienne Segonzac") did the initial proof-of-concept and my goal is to rebase/finish/polish it and add some [CSS Scroll Snapping](https://bugzilla.mozilla.org/show_bug.cgi?id=945584 "CSS Scroll Snapping") features. My initial tests for this feature are very promising. CSS Scroll Snapping is much more responsive than the previous JavaScript-based implementation. I’m still working out some bugs but hope to land my first Gaia pull request soon.

I’ve already been able to apply what I’ve learned to triage[ bugs like this one](https://bugzilla.mozilla.org/show_bug.cgi?id=1139306#c20 "RTL scrolling bug"). The bug started out described as a problem with how we launch GMail on B2G in Arabic language. Based on the testing tricks I learned from Gaia team, I was able to distill it to a root cause with scrollbar rendering on right-to-left (RTL) languages. I added a [simplified test case](http://media.junglecode.net/test/1139306/ "RTL scrolling bug test case") to the bug that should greatly reduce debugging time, and assigned it to one of our RTL experts. That’s quite a bit better than assigning tough bugs to random developers with the entire OS as the test case!

Thanks to Julien and Ettiene for helping me get up to speed. I highly recommend that any Gecko engineer spend a few days as a Gaia hacker. I’m humbled by the ingenuity these developers have for building the entire OS user experience with only the capabilities offered by the Web. We could all learn a lot in the trenches with these hackers!