---
author: jet
categories:
- Internet
- Software
date: "2012-04-06T13:31:35Z"
guid: http://www.junglecode.net/?p=140
id: 140
tags:
- Firefox
- Fonts
- Mozilla
- Open Source
- Text
title: Graphite Smart Fonts in Firefox
url: /graphite-smart-fonts-in-firefox/
---

The Gecko Layout Engine [added](https://bugzilla.mozilla.org/show_bug.cgi?id=631479 "Bugzilla: Adding Graphite support to Gecko") [Graphite Smart Fonts](http://scripts.sil.org/cms/scripts/page.php?site_id=projects&item_id=graphite_home "Graphite Smart Fonts (SIL)") support starting in [Firefox 11](http://www.mozilla.org/en-US/firefox/fx/ "Get Firefox"). *The [Mozilla Firefox documentation for Graphite](http://junglecode.net/graphite/ "Graphite Smart Fonts in Firefox") is still under construction but already contains lots of useful information for Web Designers and Developers.*

The number of people who will benefit from Graphite is the small subset of the population that reads and writes with lesser-known scripts that require complex ligatures and rules for glyph substitution. In other words, we expect this work will appeal to a rather small underrepresented percentage of the web who communicate using uncommon writing systems. Firefox fully supports [OpenType](http://en.wikipedia.org/wiki/OpenType "Wikipedia: OpenType") for the majority of writing systems on the web.

The key benefit of Graphite is that it allows type designers to build in complex script handling logic into fonts themselves, rather than relying on an application library like OpenType to explicitly implement support for it. That’s why it’s so useful for display and layout of scripts that require features not available in OpenType. There’s a lot of overlap with OpenType and the format itself simply adds extra data to OpenType fonts (the glyph and metric data is the same).

Graphite allows fonts to embed rich programs that implement the complex rules that govern glyph behavior in relation to other glyphs in a text run. This rich API presents challenges in an application as widely-distributed as Firefox, especially in regards to security and integration with the rest of the text subsystems. We’re currently testing, validating and documenting the Graphite feature in Firefox. We’re interested in getting feedback from the Font Developer community to ensure that Graphite is expressive enough for complex writing systems. If you have experience with OpenType layout, we’d like to see similar layout functionality implemented using Graphite. We’re looking for examples that could include non-Latin script support (e.g. Arabic, Thai, Indic scripts) or Latin/Cyrillic/Greek fonts with extensive feature support. A symbolic “WingDings” font with complex layout rules could also be a useful example. Please reply in the blog comments if you are interested and available to help us test and verify Graphite’s Layout API’s.

I’m posting about Graphite because it’s another example of why working on Firefox is so different from working on anything else. We don’t optimize our actions to generate maximum revenue, we do things because we want to give the entire planet equal and open access to the web. Proper text layout and rendering for complex scripts enables free expression across communities who would otherwise not have a global voice. We think it’s well worth it in service of the greater good for an Open Web.