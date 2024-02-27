---
author: jet
categories:
- Internet
- Mozilla
- Open Source
- Software
date: "2015-03-17T14:52:49Z"
guid: http://junglecode.net/?p=195
id: 195
title: What can SVG learn from Flash?
url: /what-can-svg-learn-from-flash/
---

Regular readers of my blog know that I also worked on the Macromedia Flash Professional authoring tool and the Adobe Flash Player for many years. I learned a great deal about the design of ubiquitous platforms, and the limitations of single-vendor implementations. At a recent [meeting with the W3C SVG working group](http://www.w3.org/Graphics/SVG/WG/wiki/F2F/Sydney_2015/Agenda_proposals "meeting agenda"), I shared some of my thoughts on how Flash was able to reach critical mass across the Web, and how SVG can leverage those lessons for the future.

Basically, it boils down to 3 principles:  
1\. Flash offered expressive **design-fidelity across all user agents**.  
2\. Flash authoring was superior to SVG **authoring tools** for producing content that adheres to principle # 1.  
3\. Most Flash content is self-contained and atomic in a **packaged file format** that helped preserve design-fidelity in # 1.

I shared some feedback regarding what I hear from Firefox users about SVG. I also shared what I never hear from Firefox users: “We need more SVG features.”

As the working group ponders new SVG specifications for review, the main gripe I hear from users is the lack of interoperability for the current feature set. That is, I don’t get requests for a new DOM or fancy gradient meshes, I get bugs about basic rendering differences across browsers. As a result, I’ve directed our SVG investment towards these paper cuts that make authors distrust SVG for complex designs. I can see why it’s more tempting to focus on new feature specifications, but adoption is hampered by the legacy of interoperability (or lack thereof.) I’d like to see the group organize around fixing these bugs across all browsers in a coordinated fashion, eg. in a hackathon or bug bash at a future multi-browser face-to-face meeting.

I also talked about how SVG could be a very expressive authoring source format for a modern implementation that is more focused on pixel-fidelity. Unfortunately, I didn’t get a lot of support for that idea from other browser vendors, as the desire to compete for the best implementation seemed to outweigh the benefits of dependable runtime characteristics. I’m really surprised that SVG hasn’t stepped in to replace Flash for more use cases, and I’m quite certain that the 3 principles I mentioned above are the reason why. I do hope that authoring tool vendors step in and help drive the state of the art here. It’s one thing for browser vendors to offer competing implementations, but the lack of strong authoring systems makes it hard to define what it means to be correct.

I spoke with a few people about how the packaged SWF format was an advantage for Flash because it was easy to have this content move across the internet in a viral fashion without losing any of the assets. Flash games, for example, are commonly hosted on multiple servers (often unknown to the original publisher) and still retain all the graphics and logic within the SWF file. The [W3C application package](http://w3ctag.github.io/packaging-on-the-web/#streamable-package-format "Streamable Package Format") proposal is something we could implement as a format that lets HTML/SVG content traverse networks intact. It’s not hard for such HTML/SVG applications to be made up of hundreds of individual assets that are easy to lose track of. Having a packaged format with clear semantics and security rules (eg. iframe in a zip) could be a really good feature for the modern web.

What else are we missing for SVG to gain critical mass? Post a reply below or [find me on twitter](https://twitter.com/junglecode "twitter")!