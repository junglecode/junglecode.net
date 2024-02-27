---
author: jet
categories:
- Internet
- Software
date: "2012-01-18T17:38:33Z"
guid: http://www.junglecode.net/?p=110
id: 110
tags:
- Firefox
- Graphics
- Mozilla
- Open Source
title: Firefox Invalidation
url: /firefox-invalidation/
---

As [promised](http://www.junglecode.net/?p=35 "Graphics Engines in Firefox"), I’m going to call out Firefox Layout &amp; Rendering code changes that my team has been working on. [This bug fix](https://bugzilla.mozilla.org/show_bug.cgi?id=334411 "Bug 334411 - Implement paint flashing") from [Bas Schouten](http://www.basschouten.com "Bas Schouten") (as reviewed by [Robert O’Callahan](http://robert.ocallahan.org/ "Robert O'Callahan")) was one of those light-bulb code changes that have really advanced my understanding of the Gecko Layout Engine’s graphics code:

[https://bugzilla.mozilla.org/attachment.cgi?id=574190&amp;action=diff](https://bugzilla.mozilla.org/attachment.cgi?id=574190&action=diff "diff")

This check-in implements “Paint Flashing”, a diagnostic tool that shows when the browser is invalidating (or repainting) a screen region that has changed. It’s very useful for diagnosing redundant (painting too often) or greedy (painting too large an area) invalidation. Both kinds of bugs are notoriously hard to find.

Paint Flashing will paint a random color (at 20% opacity) to indicate the “damaged” area of the screen that the browser is repainting. You can enable Paint Flashing by [setting this preference](http://kb.mozillazine.org/About:config "About:Config") to true:

nglayout.debug.paint\_flashing

If you’re running a DEBUG build, you can get to it in the Layout Debugger. The code is deceptively simple but shows the logical bottleneck where invalidation occurs in Firefox. We’re already using this tool as we evaluate [larger invalidation changes](https://bugzilla.mozilla.org/show_bug.cgi?id=598482 "Invalidation on the refresh driver") that aim to dramatically speed up rendering in Firefox. You can also use this tool as you develop your web apps to see if performance issues are the result of invalidation problems. You can tune your app much better if you know how much screen area is getting painted from your javascript or CSS code.