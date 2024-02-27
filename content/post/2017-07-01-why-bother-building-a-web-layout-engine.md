---
author: jet
categories:
- Internet
- Mozilla
- Open Source
- Software
date: "2017-07-01T02:20:59Z"
guid: https://junglecode.net/?p=206
id: 206
title: Why bother building a Web Layout Engine?
url: /why-bother-building-a-web-layout-engine/
---

All of Mozilla is currently in San Francisco for the semi-annual All-Hands event. The Web Platform Layout team also meets here to discuss current work and future projects. Our team is responsible for the following browser rendering operations:

1. Compute Style
2. Size
3. Position
4. Animate
5. Paint

…in 2D, 3D, and Virtual Reality.

Because we typically operate 7 days a week, 24 hours a day across the globe, it’s a rare opportunity to meet with everyone to share what we’ve been working on, and where we’re going next. We took turns doing Lightning Talks with each team member taking 2 to 5 minutes to share:

- A brief introduction.
- What you worked on since the last All-Hands.
- What you plan to work on next.
- What you want to learn while you’re here.

This was a “behind the scenes” chat about the guts of the Layout Engine, as illustrated in this image:

[![](http://junglecode.net/wp-content/uploads/sites/2/2017/06/stylo-291x300.png)](http://junglecode.net/wp-content/uploads/sites/2/2017/06/stylo.png)

I’ve been thinking about the internals of our Web Layout Engines and how it’s a lot like the internal movement of a mechanical wristwatch. I shared the following story about the Swiss watch industry before our meeting started. I think the similarities with the web browser business are interesting.

[![](http://junglecode.net/wp-content/uploads/sites/2/2017/07/bulgari-300x225.jpg)](http://junglecode.net/wp-content/uploads/sites/2/2017/07/bulgari.jpg)

Swiss watches are often regarded as the best of the best in haute horology. The long history of handcrafted manufacturing and very successful marketing around a watch’s provenance have made for a multi-billion dollar industry.

[![](http://junglecode.net/wp-content/uploads/sites/2/2017/07/eta09-300x225.jpg)](http://junglecode.net/wp-content/uploads/sites/2/2017/07/eta09.jpg)

The most complex and expensive part of a wristwatch is its movement: the machine that rotates the watch hands and other complications. In that sense, a watch movement is not unlike a web browser’s layout engine, which controls the display of a browser’s content.

Within the wristwatch industry, there’s a debate about the differences between in-house movements (made by the watch vendor) and outsourced movements. [ETA](https://en.wikipedia.org/wiki/ETA_SA) is a relatively obscure Swiss company that manufactures watch movements for other watch brands. There’s a long list of watch vendors that source their movements from ETA. This makes for what seems to be a great business plan: outsource the most expensive components, design the external case/dial appearance, add effective marketing, and you’re in the high-margin Swiss Watch business.

Why bother building your own watch movements, when you can use a cheaper one off the shelf? Why bother building your own layout engine, when you can use one of several “free” alternatives?

Here’s one very good reason why: In 2003 the Swiss Government launched an investigation into ETA after they announced that they would stop supplying watch movements to other companies after being acquired by The Swatch Group. The same Swatch Group that sells low-cost plastic watches at shopping malls around the world also owns several luxury watch brands. What do you do when the giant corporation that builds your watch movements decides to stop supplying? What happens when the giant corporation that builds your layout engine decides to unfairly favor its own products?

The level of skill and effort required to design and build a watch movement is an order of magnitude beyond what’s required for the outer components. There are a number of companies that still manufacture in-house movements: Patek Philippe, Rolex, and Seiko are 3 examples. I personally wear a Seiko that I bought for [less than $100](https://www.youtube.com/watch?v=F3AUN2MHRYE). My preference for in-house movements is not about price, luxury, or exclusivity. I believe there’s great value in the independent creativity and craftsmanship inherent in building the whole widget. I also love pushing the state of the art and not being limited by what others decide that we can offer. Food for thought as we work on the layout engine this week.