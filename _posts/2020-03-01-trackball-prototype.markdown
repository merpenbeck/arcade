---
layout: post
title:  "Trackball Prototype"
date:   2020-03-01 01:00:00 -0600
categories: mame
---

I am building an arcade cabinet with thousands of old games as a fun winter project. I've been building small prototypes to get a feel for the woodworking and to get the components working.  I completed a prototype of using just the trackball.

![Prototype1]({{site.baseurl}}/assets/img/trackball1.jpg)

The casing for this is just a cheap wooden box from Michael's store [Here is the link to the product](https://www.michaels.com/wooden-photo-box-by-artminds/10385255.html).  It is cheap, only $7, and so I feel less concerned to make mistakes.  Additionally, the wood is only around a 1/4" thick...most MDF on arcade machines are 3/4" thick.  This means that prototyping with it is much easier to do, but it's sturdy enough to keep around.

Additionally, you can turn the case over after using the top for controls and use the bottom.  You can see from the video that I'm actually using the case upside down, as the top has different holes drilled into it.

I am using the 3" LED trackball [Here is the link to the product](https://www.amazon.com/dp/B0711TKGFV/ref=cm_sw_em_r_mt_dp_U_BydxEbAH8K21W)
Something that they don't adverstise is that if you want the LED to light up, you need the power supply.  [Here is the link to the product](https://www.hollandcomputers.com/store/pc/3-inch-arcade-game-LED-trackball-power-supply-with-2-pin-molex-connector-p11329.htm)

The system that I'm using for this build is RetroPie.  I configured it using this video: [video](https://youtu.be/BN4_tm4jvXg).  It told me to do the following setup.  After completeing the configuration, the trackball still did not work at all.

The main thing to realize is that the trackball is a mouse.  The wiring instructions for the trackball buttons.
 ![trackball config image]({{site.baseurl}}/assets/img/trackball-config.png)

 Note that most companies that sell this device just send the device in a box with no instructions at all.  I had to contact support to get these after looking on Holland Computer's website.

 The fix that I figured out is that anything hooked to the RetroPie that registers as a mouse as well, will short circuit the trackball from working.  I had a wireless keyboard with a trackpad built into it that once I removed it, the trackball started working.

 Here are the RetroPie configuration changes needed:
```
\\retropie\configs\all\retroarch-core-options.cfg


mame2003-mame_current_mouse_enable = "enabled"
mame2010-mame_current_mouse_enable = "enabled"
```