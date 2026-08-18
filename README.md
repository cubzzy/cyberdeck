# Building a RPi-5 Pelican Cyberdeck
A parts list, cost, features, and complete tutorial to building a RPi-5 Pelican case based cyberdeck.

# Purpose #
The point of this cyberdeck is to provide a functional Linux system. I want to learn more about networking, and since Kali Linux has many networking packages pre-installed, I decided on Kali Linux as my chosen Linux distro, and a good way to obtain a Linux machine would be to make one. Building this project taught me a lot about how much information is out there in the DIY-electronics world (and how much you can do/learn through it), basic USB protocols, pinouts, power negotiation, and more. This is my first build, and I'm by no means an expert in any of the skills I mentioned, but I think starting a journey into the custom-electronics world with this is a good start.

Before I go into a complete tutorial to how I built it (and how you can too), I'll first go over the parts and specs.

# Parts List #

**SBC (Single Board Computer):**
- [Raspberry Pi, Active Cooler, and 32GB MicroSD Card](https://www.pishop.us/product/raspberry-pi-5-4gb/)
Ensure that you check "Raspberry Pi Active Cooler" and "MicroSD Card With Raspberry Pi OS 64-bit - 32GB. These are add-ons that I used in my build.
$140.90

**Screen:**
- [Waveshare 10.1 inch Screen](https://www.pishop.us/product/10-1inch-capacitive-touch-screen-lcd-e-1024x600-hdmi-ips/)
$114.95

**Power:**
- [GeeekPI PD Power Expansion Board](https://www.amazon.com/dp/B0CYPRDY9Q?ref=ppx_yo2ov_dt_b_fed_asin_title)
This will allow you to use the following power bank as it converts the watts into the correct Amps/Volts required by the RPi5. I'll go into more detail on this later.
$29.99

- [20,000mAh Anker Power Bank](https://www.amazon.com/dp/B0CXDXP8VR?ref=ppx_yo2ov_dt_b_fed_asin_title&th=1)
$69.99

**Keyboard:**
- [Holy60 Keyboard Kit](https://kbdfans.com/products/holy60-keyboard-kit)
$171.00

- [Gateron Smoothie Switches (7x Quantity)](https://kbdfans.com/products/gateron-smoothie-linear-switch?_pos=2&_sid=1c38d201f&_ss=r)
$21.00
 
- [Spider Web Keycaps](https://www.amazon.com/dp/B0DT64PW3C?ref=ppx_yo2ov_dt_b_fed_asin_title&th=1)
$31.99

- OPTIONAL: [Dielectric Grease](https://www.amazon.com/dp/B000AL2RI2?ref=ppx_yo2ov_dt_b_fed_asin_title&th=1)
$7.00

**Case:**
- [Pelican 1400 Case With Foam](https://www.amazon.com/dp/B00009XVKY?ref=ppx_yo2ov_dt_b_fed_asin_title&th=1)
$124.95

**Mounting:**
- [3M Dual Lock Fastener](https://www.amazon.com/dp/B00AQ6IS1G?ref=ppx_yo2ov_dt_b_fed_asin_title&th=1)
$19.88

**Mouse:**
- [TECKNET Wireless Mouse](https://www.amazon.com/dp/B0DW7M2JY1?ref=ppx_yo2ov_dt_b_fed_asin_title&th=1)
$16.99

**Cords:**
- There are no additional cords that are required for this build. Every part that needs a cord comes with its own.

# Total Cost #
Excluding tax, the total is **$748.64**. Which obviously isn't ideal. However, there are several things you could do to reduce cost. For example, a large chunk of that cost is from the keyboard. Purchasing a regular keyboard or using one that you already have that outputs a USB-A connection is enough. I decided to spend a lot on a custom keyboard knowing that I could use it for any project down the line. 

Additionally, you could use a mouse that you already have in your house, again just needing a USB-A connection. Unfortunately, because of the AI datecenter boom, RAM has skyrocketed throughout all of computing which effectively doubled the price of RPis. 

The core of the build (and cyberdecks in general) is SBC + monitor + keyboard + mouse/trackpad + case. Adjusting any one of those options can save you money, and the cost of this build could *easily* be cut in half if you use cheaper parts.

# Features #
**Board**

- Raspberry Pi 5 quad-core 2.4 GHz ARM Cortex-A76 CPU and VideoCore VII GPU
- Gigabit Ethernet port, 2 USB-A 3.0 ports, 2 USB-A 2.0 ports, MicroSD card slot, Micro-HDMI in/out ports, USB-C power port, etc.
- Cooled with the bundled Active Cooler + heatsink (the heatsink comes with the Active Cooler add-on)
- 32GB Flashdrive

**Screen**
- 10.1 inch 1024x600 Touch Screen, 3.5mm Jack and 4PIN Header

**Power**
- Flexibly chooses the correct power output to give to the Pi (given the power bank wattage is enough)
- 87W power bank capable of providing an estimated 5-6 hours of runtime (I haven't run the battery all the way yet, but based on how slow it drains I estimate this amount of time). 

**Keyboard + Mouse**
- Hotswap PCB with RGB underglow
- USB-C port with USB Blocker
- 7 degree typing angle
- Pre-lubed switches
- Bluetooth mouse

**Case**
- The computer, power bank, keyboard, and mouse, are held in place just with foam that I've cut out to fit each part. Surprisingly, this method is really stable and even when I shake the case I'm not able to hear anything moving around inside. When I open the case everything is in the exact spot I left it in.
- The monitor is mounted with "3M Dual Lock Fastener" which is basically just strong velcro. It seems to adhere well to the polypropelene case.
- There are *no* permanent changes to the case. I could take everything out and use the case for a different purpose.

**OS**
- Running Kali Linux (64-bit) downloaded through the official RPi imager

# Additional Notes #
Before I get to the tutorial of how to set everything up, I want to be clear that everything will work fine if you use a cheap mouse and keyboard or one you already have. 

The main changes that would alter the build and negate the helpfulness of this tutorial would be changing the ***Monitor***, the ***Raspberry Pi***, and the ***Expansion Board***. 

I haven't tried other power banks, but you would have to ensure it has enough mAh to get a decently long runtime (ideally 15,000mAh+). Increasing the size of the screen would also increase power draw and thus decrease battery life.

It's possible to change the case and still follow this tutorial for the RPi + PD Expansion Board + Monitor setup, provided that you've measured everything and have a way for everything to fit (ideally securely).

Finally, I can't verify that all of the parts listed will be available or at the same price at the time I made this repository.

**Assuming you have read over the preceding part of this README, and have the parts you want to use in front of you, you can move on to the *Tutorial* section.**

# Tutorial #
I am going to go part by part, as I think that is most efficient. Additionally, I'll go through my thinking process and the resources I used to give you some insight on how I approached this projects and things to keep in mind when building your own. Note that it was not as easy for me to build it myself; I faced several challenges like the keyboard shorting (I was unaware it needed rubber standoffs, more on that later), an actual issue with a different Power Expansion Board I used before the GeeekPi one (back and forth with support to eventually find out it was a hardware issue with the CC line of the USB port), and other time spent on things like researching the best way to mount everything without modifying the case (which don't come with mounting screw holes). I hope that this can help someone on their cyberdeck journey and hopefully have a more graceful time building their project while still having ample challenge to make it a learning process. 

**Keyboard**
If you are planning to not build a custom keyboard, you can skip this section.

I first built a keyboard when I was around 14 or so, but I completely forgot how to approach it. After some research, I ended up deciding to go with a keyboard kit. **Kbdfans.com** is a very populsar website that many people get their keyboard parts from. Additionally, they have a discord which has a community of people that are willing to help if you have any difficulty. 
A [keyboard kit](https://keebsforall.com/blogs/mechanical-keyboards-101/mechanical-keyboard-kits-vs-prebuilt-keyboards) essentially have everything you need to build a keyboard, excluding switches and keycaps. I'd recommend them because it saves you the annoyance of ensuring that your case, pcb, stabs, and plate all work together. Building keyboards is a big hobby and many people tinker with and mod custom keyboards that they make.
I chose my switches because I saw a video where they sounded nice. I just thought my keycaps looked cool, although there can be a lot of nuance with how the keys bottom out (when you press them fully) and the material of the keycaps, and the sound difference that it makes.
If you decide to go with a keyboard kit, there are many videos online of how to put them all together. For the sake of space, I won't go too deep into it, but if you go into the kbdfans discord, there are lots of resources there (like lubing stabilizers, how to put stabs together, the way the parts of a keyboard come together and how to set it up).  
I basically just took out all the parts and tried to figure it out based on what made sense. The only thing I could tell you that genuinely would save time is that the detachable golden stand-offs that mine came with (essentially a threaded fastener to close a gap between two objects) actually shorted several of the keys together. When I had everything set up and pressed the H key, several other keys would also be pressed that were close to the H key. To combat this, you can purchase [silicone covers](https://kbdfans.com/products/kbdfans-standoff-silicone-cover) for the standoffs that prevent this issue. I ended up just covering the standoff with electrical tape, which was slightly janky given how small the standoff is, but it ended up working fine, and I haven't had any issues since.
The only other consideration to make when building a keyboard is if you want to lube the stabs/switches or not. There are many videos out there on how to do this, but the main idea is that Dielectric Grease can be used for the metal part of the stab, and you can use Krytox 205g0 to lube the plastic part of the stab. Dielectric grease is kind of like a vaseline-consistency and is used for spark plugs, which makes sense that it's not used on the inner housing of the stab (it would likely be too thick and result in a mushy key press). Krytox is a lot lighter.

A fun part about making a custom keyboard is configuring the keys and light patterns. There are websites online where you can do this, and it depends on your PCB, but the one for my keyboard is [Via](https://usevia.app/). All you have to do is connect your keyboard and the software is fairly intuitive to use. For me, I have the very bottom right key set to change layers. Layers is a way to add more functionality to your keyboard. On a 60% keyboard like mine, there aren't many keys to work with. If you add multiple layers, you can basically customize it so that if you click a certain button, you go up or down a layer, and you are then able to use completely different keys. In layer 0, I have my default keyboard layout, and on layer 1, I have light pattern switching, brightness up and down, and arrow keys. I also put the backtick symbol (`) in the top left because the default output for the top left key is escape. 

