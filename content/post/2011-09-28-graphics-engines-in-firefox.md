---
author: jet
categories:
- Internet
- Software
date: "2011-09-28T16:00:30Z"
guid: http://www.junglecode.net/?p=35
id: 35
tags:
- Firefox
- Mozilla
- Open Source
title: Graphics Engines in Firefox
url: /graphics-engines-in-firefox/
---

One of the key goals for the Firefox Layout &amp; Rendering team is to improve performance for web applications. Web apps nowadays push the graphics rendering stack in ways that rival console games. To that end, our existing rasterizer was hitting its limits in terms of the sheer volume of data we now push through it on a a regular basis. [Switching out a shipping application’s raster engine](http://robert.ocallahan.org/2011/09/graphics-api-design.html "Gecko Graphics API Design") is a big deal that requires a lot of scaffolding. When I was working on the Flash Player, I saw how much work goes into integrating a [new graphics engine](http://labs.adobe.com/technologies/flashplatformruntimes/features/stage3d.html "Flash 3D Graphics") into a shipping product. Sometimes, you have no choice but to tack it on top of (or in Flash’s case, [behind](http://www.bytearray.org/?p=2555 "Flash Molehill Stacking Order")) the existing rasterizer.

For Firefox, the scaffolding involves the addition of the new rasterizer initially for the [&lt;canvas&gt;](https://developer.mozilla.org/en/HTML/Canvas "Canvas API") API’s. This was ideal because it was fairly localized, and backwards-breakage risk was manageable. In the next phase, all CSS layout styling will use the new engine. The lessons learned from &lt;canvas&gt; make this a much less risky phase but it’s still fraught with peril. The benefits will be worth it, especially when we get page-draw and responsiveness [metrics](https://wiki.mozilla.org/Buildbot/Talos#Paint_Tests "Painting Tests") cranked up.

I’ll be posting up more details on Layout &amp; Rendering internals as I dive deeper into it. It’s quite exciting to work on the guts of the Web with passionate engineers.