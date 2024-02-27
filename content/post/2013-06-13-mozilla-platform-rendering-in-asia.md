---
author: jet
categories:
- Hardware
- Internet
- Software
date: "2013-06-13T21:03:44Z"
guid: http://junglecode.net/?p=162
id: 162
tags:
- Firefox
- Mobile
- Mozilla
- Open Source
- Taiwan
title: Mozilla Platform Rendering in Asia
url: /mozilla-platform-rendering-in-asia/
---

I’ve spent the last 3 weeks traveling in Asia for Mozilla and W3C business. On May 20 to 24, my team was in Taiwan for a series of meetings on Platform Rendering (Layout, Graphics, and Media.) It’s always an enlightening experience for me when I spend time with such a talented group of people:

<div class="wp-caption aligncenter" style="width: 522px">[![](http://media.junglecode.net/media/TWN_9726_sm.jpg)](http://media.junglecode.net/media/TWN_9726_sm.jpg)The Mozilla Firefox Platform Rendering Team on location in Taiwan.

</div>Going to Taiwan was a very special event. The local Taiwan office was awesome, and the local staff was very wonderful, taking great care of us while we were there. Beautiful and fast rendering requires a deep understanding of the underlying hardware, and if you’re serious about hardware, you eventually have to go to Taiwan. Meeting and working with the local Taiwan team was great. They’re so smart, and eager to learn about the Firefox Platform. We spent a lot of time getting them caught up on Rendering infrastructure, and various Mozilla-specific topics (Open Source, Open Specs, Code Review, etc.)

I’ve pasted the calendar we followed for the week, below. The links point to raw notes from the sessions (where available.) I apologize for the lack of context in some notes, as they’re meant for the attendees. They’re in this blog post to give you an idea of what the Rendering Team does when we get together in a large group every few months.

# Taiwan Rendering Sessions

|  | Monday | Tuesday | Wednesday | Thursday | Friday |
|---|---|---|---|---|---|
| 9am | Lightning talks | Graphics: [SkiaGL Canvas](https://etherpad.mozilla.org/TaiwanWorkWeekSkiaGLCanvas) (snorp) | Graphics:[WebGL](https://etherpad.mozilla.org/TaiwanWorkWeekWebGLFxOS) (Vlad) |  | Layout/Media: Implementing [WebVTT CSS features](http://dev.w3.org/html5/webvtt/#applying-css-properties-to-webvtt-node-objects) (rillian/dbaron) |
| 10am | Free | Graphics: [SkiaGL Content](https://etherpad.mozilla.org/TaiwanWorkWeekSkiaGLContent) (Jeff M.)   Layout: [Intro to Style System](https://etherpad.mozilla.org/IntroToStyleSystem) (dbaron) | Graphics: [WebGL](https://etherpad.mozilla.org/TaiwanWorkWeekWebGLFxOS) (Vlad)   Media: [libCubeb/Audio Latency](https://etherpad.mozilla.org/TaiwanWorkWeekLibCubeb) (Kinetik) | Platform:[Cycle Collection 101](https://etherpad.mozilla.org/TaiwanWorkWeekCycleCollection) (khuey) | Graphics: [Timing Attacks](https://etherpad.mozilla.org/TaiwanWorkWeekGFXSecurity) (bjacob)   Layout:[Layout Documentation](https://etherpad.mozilla.org/TaiwanWorkWeekLayoutDocumentation) – Conf Room B (jwir3)Media: **???** |
| 11am | Free | Graphics: [Async Canvas](https://etherpad.mozilla.org/TaiwanWorkWeekAsyncCanvas) (Vlad, snorp)   Layout: [Intro to Dynamic Changes in Layout](https://etherpad.mozilla.org/TaiwanWorkWeekIntroToDynamicChangesLayout) (dbaron) | Graphics: [WebGL](https://etherpad.mozilla.org/TaiwanWorkWeekWebGLFxOS) (Vlad)   Media: [Web Audio](https://etherpad.mozilla.org/TaiwanWorkWeekWebAudio) (padenot) | Layout: CSS Masking   Media: [Fixing MediaStreamGraph video propagation](https://etherpad.mozilla.org/TaiwanWorkWeekMediaStreamGraphVideo) (roc) | Graphics: [Imagelib](https://etherpad.mozilla.org/TaiwanWorkWeekImagelib) (joe)   Other: [WebGL](https://etherpad.mozilla.org/TaiwanWorkWeekWebGLFxOS) (Vlad)   Layout: **???**    Media: **???** |
| Noon | Lunch | Lunch | Lunch | Lunch | Lunch |
| 1pm | Graphics: [OMT-Compositing](https://etherpad.mozilla.org/TaiwanWorkWeekOMTCompositing) (Nical – “D”)   Layout: Layout 101 (Elika – “C”) | Layout: [APZC](https://etherpad.mozilla.org/TaiwanWorkWeekOMTAsyncScrolling) | Graphics: [Moz2D/Player2D](https://etherpad.mozilla.org/TaiwanWorkWeekMoz2D) (Bas) | Layout:[Layout fuzzer](https://etherpad.mozilla.org/TaiwanWorkWeekLayoutFuzzer) status (multicol security bugs, etc.) – Conf Rm. A | Graphics:Intro to Gecko Graphics (mwoodrow)   Layout: **???**    Media: **???** |
| 2pm | Graphics: [Layers and buffers](https://etherpad.mozilla.org/gfx-buffers-taipei) (bjacob) | Layout:[Web Animations](https://wiki.mozilla.org/Platform/Layout/Web_Animations) (birtles)   Media: MediaSource Extensions (kinetik) | Graphics: [OMT Canvas](https://etherpad.mozilla.org/TaiwanWorkWeekOMTCanvas) | Layout: Web Animations contd. (birtles) | Graphics: **???**    Layout: Standardization and Mozilla (dbaron/abr) «[IETF Slides](https://intranet.mozilla.org/images/7/7d/Intro-to-IETF.pdf)»   Media: **???** |
| 3pm | Graphics: [Gralloc](https://wiki.mozilla.org/Platform/GFX/Gralloc)   Layout:[CSS Variables](https://etherpad.mozilla.org/TaiwanWorkWeekCSSVars) / [CSS Cascade](https://etherpad.mozilla.org/TaiwanWorkWeekCSSCascade) (heycam, dbaron – “C”) | Layout: [CSS Graphics](https://etherpad.mozilla.org/TaiwanWorkWeekCSSGraphics) | Graphics: [OMT Animation](https://etherpad.mozilla.org/TaiwanWorkWeekOMTAnimation)   Layout: (see graphics)   Media: [Media Decoding](https://etherpad.mozilla.org/TaiwanWorkWeekMediaDecoding) (cdouble) [OMX Codec](https://etherpad.mozilla.org/TaiwanWorkWeekOMXCodec) (sotaro) | Graphics: [B2G/Android Graphics Testing](https://etherpad.mozilla.org/TaiwanWorkWeekB2GTesting)   Layout:[CSS Writing Modes – Vertical Text](https://etherpad.mozilla.org/TaiwanWorkWeekVerticalText) (fantasai) | Graphics: **???**    Layout:[Layout Performance](https://etherpad.mozilla.org/TaiwanWorkWeekLayoutPerf) (jet)   Media: **???** |
| 4pm | Media: [WebVTT/TextTrack](https://etherpad.mozilla.org/TaiwanWorkWeekWebVTT) (rillian) | The Mozilla Way (roc) | Graphics: [CSS Filters](https://etherpad.mozilla.org/TaiwanWorkWeekCSSFilters)   Layout:[CSS3 Fonts](https://etherpad.mozilla.org/TaiwanWorkWeekCSS3Fonts) | [Code Reviews – The Mozilla Way](https://etherpad.mozilla.org/TaiwanWorkWeekCodeReview) (roc) | **[Work Week Wrap-up](https://etherpad.mozilla.org/TaiwanWorkWeekWrapUp)** (jet) |

![](http://media.junglecode.net/media/gecko_rendering_taiwan_2013_sm.jpg)