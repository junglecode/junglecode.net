---
author: jet
categories:
- Internet
- Software
date: "2012-02-07T01:58:53Z"
guid: http://www.junglecode.net/?p=119
id: 119
tags:
- C++
- CSS
- Firefox
- Gecko
- HTML
- Mozilla
title: How I got started hacking on Firefox
url: /how-to-get-started-hacking-the-firefox-browser-engine/
---

One of the [Gecko](http://en.wikipedia.org/wiki/Gecko_%28layout_engine%29 "Gecko Layout") Layout &amp; Rendering team’s main responsibilities is the continuing development of [CSS](http://en.wikipedia.org/wiki/Cascading_Style_Sheets "CSS wikipedia") in Firefox. I recently [modified the CSS style system to allow nested rule parsing](https://bugzilla.mozilla.org/show_bug.cgi?id=511909 "allow @-rules inside of @media and @-moz-document"). This [bug fix](https://bugzilla.mozilla.org/attachment.cgi?id=580586&action=diff "code change") taught me a lot about the CSS parser and how styles cascade through the rest of the Layout engine. It took me a little while to [set up a dev environment](https://developer.mozilla.org/En/Simple_Firefox_build "MDN build instructions"), understand the bug, [write tests](https://bug511909.bugzilla.mozilla.org/attachment.cgi?id=580247 "HTML test cases"), get the code written, reviewed, and checked in. I now have a much better understanding of what it takes to move code through the Mozilla source trunk.

I suspect that there are other programmers out there currently lurking around the Mozilla community, intimidated by the scale of the source tree, and wondering where to start hacking on Firefox. I highly recommend starting with the [Gecko Overview](https://wiki.mozilla.org/Gecko:Overview "Gecko Overview") started by [L.David Baron](http://dbaron.org/ "David Baron's weblog"), Mozilla Principal Software Engineer, to help beginners understand the browser engine. Thanks, David!