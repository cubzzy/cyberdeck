# Building a RPi-5 Pelican Cyberdeck
A parts list, cost, features, and complete tutorial to building a RPi-5 Pelican case based cyberdeck.

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

**OS**
- Running Kali Linux (64-bit) downloaded through the official RPi imager

# Additional Notes #
Before I get to the tutorial of how to set everything up, I want to be clear that everything will work fine if you use a cheap mouse and keyboard or one you already have. 

The main changes that would alter the build and negate the helpfulness of this tutorial would be changing the ***Monitor***, the ***Raspberry Pi***, and the ***Expansion Board***. 

I haven't tried other power banks, but you would have to ensure it has enough mAh to get a decently long runtime (ideally 15,000mAh+). Increasing the size of the screen would also increase power draw and thus decrease battery life.

It's possible to change the case and still follow this tutorial for the RPi + PD Expansion Board + Monitor setup, provided that you've measured everything and have a way for everything to fit (ideally securely).

Finally, I can't verify that all of the parts listed will be available or at the same price at the time I made this repository.

**Assuming you have read over the preceding part of this README, and have the parts you want to use in front of you, you can move on to the *Tutorial* section.**
