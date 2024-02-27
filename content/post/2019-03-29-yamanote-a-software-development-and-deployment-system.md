---
author: jet
categories:
- Indeed
- Internet
- Mozilla
- Open Source
- Software
date: "2019-03-29T09:35:08Z"
guid: https://junglecode.net/?p=214
id: 214
title: 'Yamanote: A software development and deployment system'
url: /yamanote-a-software-development-and-deployment-system/
---

I left Mozilla back in July, 2018. There are many reasons for this decision, and I’ll talk about just one here: I decided to [Help People Get Jobs](https://www.indeed.com/cmp/Indeed/jobs). The following text is from a blog post I wrote at work. I have reposted it here, edited for length and content (Internal Indeed systems are not referenced.)

At Indeed, we now use a software development and deployment system called “Yamanote.” Yamanote takes its name from the Yamanote Line (山手線) in Tokyo, Japan. It is one of Tokyo’s busiest and most important lines, connecting most of Tokyo’s major stations and urban centers. The Yamanote line is a continuous railway loop. Trains which run clockwise are known as sotomawari (外回り, “outer circle”) and those counter-clockwise as uchi-mawari (内回り, “inner circle”). We deploy software on two lines as well: QA and PROD. Just like the Yamanote line, our goal is for our software trains to run reliably, safely, and securely, in a continuous ring of <span style="color: #00ff00;">**green**.</span>

[![](http://junglecode.net/wp-content/uploads/sites/2/2019/03/rings-300x217.png)](http://junglecode.net/wp-content/uploads/sites/2/2019/03/rings.png)

The level of service and quality required to operate the Yamanote train line is what we aspire to and apply to our software development. We continuously improve our tools and processes. It is expected that code merging into any of our deployment branches is tested and ready for public use.

Our business (We Help People Get Jobs) is a very long-term concern (think in decades!) and we expect some of our software to have a service-life that can span many years. We optimize for lasting impact. We operate quickly and carefully.

The Yamanote line is a marvel of technology, with incredible innovations in electrical engineering and automated systems. Despite all of the technology used, the most important factors in the line’s reliability are **the people who operate the system:**

[![](http://junglecode.net/wp-content/uploads/sites/2/2019/03/3354697-300x200.jpg)](http://junglecode.net/wp-content/uploads/sites/2/2019/03/3354697.jpg)

Every staff member on the line has the authority to stop and start the trains with a wave of their white glove. It’s this level of responsibility and care that makes all the difference. We aspire to bring that “white glove” treatment into our software development discipline, as the millions of people who depend on us also need to get to work every single day.

Thanks to Wikipedia for the Yamanote line history facts. I’m working on releasing the Yamanote tools as Open Source in a future post.