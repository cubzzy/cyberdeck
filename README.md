# Building a RPi-5 Pelican Cyberdeck
A parts list, cost, features, and complete tutorial to building a RPi-5 Pelican case based cyberdeck.

![Photo of cyberdeck](https://github.com/cubzzy/cyberdeck/blob/main/sideview1.jpg)

# Purpose #
The point of this cyberdeck is to provide a functional Linux system. I want to learn more about networking, and since Kali Linux has many networking packages pre-installed, I decided on Kali Linux as my chosen Linux distro, and a good way to obtain a Linux machine would be to make one. Building this project taught me a lot about how much information is out there in the DIY-electronics world (and how much you can do/learn through it), basic USB protocols, pinouts, power negotiation, and more. This is my first build, and I'm by no means an expert in any of the skills I mentioned, but I think starting a journey into the custom-electronics world with this is a good start.

Before I go into a complete tutorial to how I built it (and how you can too), I'll first go over the parts and specs.
Even if you don't plan on following the tutorial, it might be helpful to follow along and get some inspiration for how you want to approach your project.

# Parts List #

**SBC (Single Board Computer):**
- [Raspberry Pi, Active Cooler, and 32GB MicroSD Card](https://www.pishop.us/product/raspberry-pi-5-4gb/)
Ensure that you check "Raspberry Pi Active Cooler" and "MicroSD Card With Raspberry Pi OS 64-bit - 32GB". These are add-ons that I used in my build.
$140.90

**Screen:**
- [Waveshare 10.1 inch Screen](https://www.pishop.us/product/10-1inch-capacitive-touch-screen-lcd-e-1024x600-hdmi-ips/)
$114.95

**Power:**
- [GeeekPI PD Power Expansion Board](https://www.amazon.com/dp/B0CYPRDY9Q?ref=ppx_yo2ov_dt_b_fed_asin_title)
This will allow you to use the following power bank as it converts the power to the correct 5V/5A that the Pi 5 needs. I'll go into more detail on this later.
$29.99

- [20,000mAh Anker Power Bank](https://www.amazon.com/dp/B0CXDXP8VR?ref=ppx_yo2ov_dt_b_fed_asin_title&th=1)
$69.99

**Keyboard:**
- [Holy60 Keyboard Kit](https://kbdfans.com/products/holy60-keyboard-kit)
$171.00

- [Gateron Smoothie Switches (7x Packs)](https://kbdfans.com/products/gateron-smoothie-linear-switch?_pos=2&_sid=1c38d201f&_ss=r)
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

Additionally, you could use a mouse that you already have in your house, again just needing a USB-A connection. Unfortunately, because of the AI data center boom at the time of writing this, RAM has skyrocketed throughout all of computing which effectively doubled the price of RPis. 

The core of the build (and most cyberdecks in general) is SBC + monitor + keyboard + mouse/trackpad + case. Adjusting any one of those options can save you money, and the cost of this build could *easily* be cut in half if you use cheaper parts.

# Features #
**Board**

- Raspberry Pi 5 quad-core 2.4 GHz ARM Cortex-A76 CPU and VideoCore VII GPU
- Gigabit Ethernet port, 2 USB-A 3.0 ports, 2 USB-A 2.0 ports, MicroSD card slot, dual Micro-HDMI output ports, USB-C power port, etc.
- Cooled with the bundled Active Cooler + heatsink (the heatsink comes with the Active Cooler add-on)
- 32GB MicroSD card

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
- The monitor is mounted with "3M Dual Lock Fastener" which is basically just strong velcro. It seems to adhere well to the polypropylene case.
- There are *no* permanent changes to the case. I could take everything out and use the case for a different purpose.

**OS**
- Running Kali Linux (64-bit) downloaded through the official RPi imager

# Additional Notes #
Before I get to the tutorial of how to set everything up, I want to be clear that everything will work fine if you use a cheap mouse and keyboard or one you already have. 

The main changes that would alter the build and negate the helpfulness of this tutorial would be changing the ***Monitor***, the ***Raspberry Pi***, and/or the ***Expansion Board***. 

I haven't tried other power banks, but you would have to ensure it has enough mAh to get a decently long runtime (ideally 15,000mAh+). Increasing the size of the screen would also increase power draw and thus decrease battery life.

It's possible to change the case and still follow this tutorial for the RPi + PD Expansion Board + Monitor setup, provided that you've measured everything and have a way for everything to fit (ideally securely).

Finally, I can't verify that all of the parts listed will be available or at the same price at the time I made this repository.

**Assuming you have read over the preceding part of this README, and have the parts you want to use in front of you, you can move on to the *Tutorial* section.**

# Tutorial #
I am going to go part by part, as I think that is most efficient. Additionally, I'll go through my thinking process and the resources I used to give you some insight on how I approached this project and things to keep in mind when building your own. Note that it was not as easy for me to build it myself; I faced several challenges like the keyboard shorting (I was unaware it needed rubber stand-offs, more on that later), an actual issue with a different Power Expansion Board I used before the GeeekPi one (back and forth with support to eventually find out it was a hardware issue with the CC line of the USB port), and other time spent on things like researching the best way to mount everything without modifying the case (which doesn't come with mounting screw holes). I hope that this can help someone on their cyberdeck journey and hopefully have a more graceful time building their project while still having ample challenge to make it a learning process. 

**Keyboard**

If you are planning not to build a custom keyboard, you can skip this section.

- After some research, I ended up deciding to go with a keyboard kit. [Kbdfans.com](https://kbdfans.com/) is a very popular website that many people get their keyboard parts from. Additionally, they have a Discord which has a community of people that are willing to help if you have any difficulty. 

- A [keyboard kit](https://keebsforall.com/blogs/mechanical-keyboards-101/mechanical-keyboard-kits-vs-prebuilt-keyboards) essentially has everything you need to build a keyboard, excluding switches and keycaps. I'd recommend them because it saves you the annoyance of ensuring that your case, PCB, stabs, and plate all work together. 

- I chose my switches and keycaps based on their sound and look. There can be a lot of nuance with how the keys bottom out (when you press them fully down) and the material of the keycaps, and the sound difference that it makes.

- If you decide to go with a keyboard kit, there are many videos online of how to put them together. For the sake of space, I won't go too deep into it, but if you go into the Kbdfans Discord, there are lots of resources there (like lubing stabilizers, how to put stabs together, and generally how to put together all the parts).  

- I basically just tried to figure out how to put everything together based on what made sense. The only thing I could tell you that genuinely would save time is that the detachable golden stand-offs that mine came with (essentially a threaded fastener to close a gap between two objects) actually shorted several of the keys together. When I had everything set up and pressed the H key, several other keys would also output that were close to the H key. To combat this, you can purchase [silicone covers](https://kbdfans.com/products/kbdfans-standoff-silicone-cover) for the stand-offs that prevent this issue. I ended up just covering the stand-off with electrical tape, which was slightly janky given how small the stand-off is, but it ended up working fine, and I haven't had any issues since.

- Another consideration to make when building a keyboard is if you want to lube the stabs and switches or not. There are many videos out there on how to do this, but the main idea is that dielectric grease can be used for the metal part of the stab, and you can use Krytox 205g0 to lube the plastic part of the stab. Dielectric grease has a vaseline-consistency and is used for spark plugs, so it makes sense that it's not used on the inner housing of the stab (it would likely be too thick and result in a mushy key press). Krytox is a lot lighter.

- A fun part about making a custom keyboard is configuring the keys and light patterns. There are websites online where you can do this, and it depends on your PCB, but the one for my keyboard is [Via](https://usevia.app/). All you have to do is connect your keyboard and the software is fairly intuitive to use. For me, I have the very bottom right key set to change layers. [Layers](https://get.vial.today/manual/layers.html) are a way to add more functionality to your keyboard. On a 60% keyboard like mine, there aren't many keys to work with. If you add multiple layers, you can basically customize it so that if you click a certain button, you go up or down a layer, and you are then able to use completely different keys. In layer 0, I have my default keyboard layout, and on layer 1, I have light pattern switching, brightness up and down, and arrow keys. I also put the backtick symbol (`) in the top left because the default output for the top left key is escape. 

After configuring the keys and the RGB if your PCB supports that, you're good to go.

**Putting Together the Board and Related Components**

Assuming you're going with the RPi5 + PD Expansion Board mentioned in the parts list, you can follow these directions. Physically mounting everything is fairly straightforward.

- Ensure you have the RPi, Active Cooler, MicroSD card, and Expansion Board in front of you.
- First mount the Active Cooler. Directions come with the box, but it essentially just sticks on with an adhesive and two plastic pieces to mount it, and gets plugged in to the RPi. Make sure you plug it in the right way, as it can damage the connection if not. Also, as stated in the directions, don't try and remove the Active Cooler after installing it, as this can damage the plastic mounts that are holding it in place. 
- Next, you can mount the Expansion Board. Directions also come with the box, and it just involves screwing in some pieces with a screwdriver that comes with the Expansion Board.

**Flashing the OS**
- In order to flash a new operating system onto the Pi, you can use the official [Raspberry Pi Imager](https://www.raspberrypi.com/software/). Once you download the actual imager software, you can select Kali Linux and follow the onscreen steps to flash (write a new operating system to) the drive. You can now insert that into the Pi. 
 
**Connecting Peripherals**
- At this point, you can plug in the keyboard, mouse, monitor, and any other peripherals you may have. 

**Adding Power**
- If you *don't* use an Expansion Board, and try to plug in a power bank straight to the Pi, the voltage will likely be throttled. The Pi will go from being able to supply 1.6A to all peripherals down to 600mA. I haven't been able to find any power banks that are able to supply the 5V/5A that the Pi5 wants, and this is something that's documented online. Some people go around this by modifying a file that essentially allows the 5V/5A power draw anyways, even if the power bank can't support it, but it's risky to do that as it can damage components. Only do that if you're sure that your power bank can supply that. 
- Make sure that you charge your power bank fully, and then connect it to the USB-C input on the Expansion Board. Something that required more research when working with a Pi5 is that a Pi5 requires 5V/5A, which is not standard of PD (Power Delivery) protocol. The Expansion Board automatically deals with this power negotiation, provided that the power bank has enough wattage. You can find more information on the Pi5 power requirements [here](https://pip-assets.raspberrypi.com/categories/685-app-notes-guides-whitepapers/documents/RP-009856-WP-1-USB%20Power%20delivery%20on%20Raspberry%20Pi%205.pdf).

**Turning it On**
- Now that you supplied power, a blue light should appear on the Expansion Board. Click the "Power On" button on the Expansion Board, and the Pi should start booting.
![Power supplied RPI](https://github.com/cubzzy/cyberdeck/blob/main/frontview.jpg)
**Check-up**
- By this point, you should be booting up your Pi for the first time. All of the peripherals should be connected and working, and you should be at a log-in screen. You can now log in.

**Getting WiFi Working**
- You may notice that you don't have access to WiFi, even though you may have already set it up in the Raspberry Pi Imager. 
- They may have fixed this by the time you're reading this, but I'll explain the process I went through, to the best of my memory and my notes, to help solve this issue.
- I believe that netplan, a network configuration utility for Linux, was bypassing NetworkManager (no renderer: key was set in the netplan YAML). To solve this, I backed up the YAML file (just copied the file with the cp command), ran sudo nano /etc/netplan/50-cloud-init.yaml, then added "renderer: NetworkManager" right under version.
- Then, I ran sudo netplan apply. This should get WiFi working for your machine. 

You should now have a fully functioning Kali Linux machine that's capable of running on WiFi and connecting to the internet. If you have any issues, feel free to contact me (I put my information at the bottom of this README).

**Mounting**
- After getting all the parts working, I spent some time determing how and in what case I wanted to mount my cyberdeck.
- I scrolled through some posts in r/cyberdeck and eventually got inspired by [this post](https://www.reddit.com/r/cyberDeck/comments/15af8l5/wip_cyberdeck_build_in_pelican_case/). I liked the 3D printed baseplate design that this person made, but I also knew that learning how to 3D print would take some time and effort.
- The Pelican 1400 Case doesn't have any mounting screws, so this also made me averse to implementing the 3D-print idea, as it would either require me to modify the case or have the baseplate stay just through friction. 
- Eventually, I decided to go with the easiest option, which was 3M Dual Lock to mount the monitor, and foam to hold all the bottom components in place.
- Essentially, I just cut out four strips of the Dual Lock, attached it to the back of the monitor, and cut out the foam so that everything would fit snug. If four strips isn't enough to hold the screen for you, I'd recommend adding more. The foam comes already in a grid-like pattern, meaning cutting it was pretty trivial.
- I found using a pocket knife to cut along the edges of the grids to the size of each component (keyboard, Pi, power bank), was most efficient. Because there's no vertical grids built in to the foam, I would take out the foam after cutting the edges, and cut it vertically however much I needed so that it was deep enough for the respective part when I put it back in. 
- Everything fits snug and luckily I was able to achieve this without doing any modifications to the case, which is a big plus. As stated in the *Features* section, once the case is closed, I'm able to shake it and not hear any movement inside. Everything stays in the spot I left it in.

![Picture of foam holding components](https://github.com/cubzzy/cyberdeck/blob/main/foam.jpg)
# Limitations #
- On this screen, some things at the bottom of the screen get slightly cut off. I'm guessing that Kali just doesn't support the resolution that the screen gives, but I haven't really dug into this because it doesn't bother me too much, but it's something to consider if you want to try out a different screen.

# End #
I hope you enjoyed the recap of my project. If you have any questions, comments, or concerns, you can reach out to me at supercalifornia1992@proton.me. If you are planning or in the process of your own build, I wish you luck!

