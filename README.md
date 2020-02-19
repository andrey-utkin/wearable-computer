# My Wearable Computer

![Photo of me using my wearable computer](https://raw.githubusercontent.com/andrey-utkin/wearable-computer/master/img/my/front.jpg)

[More photos](https://github.com/andrey-utkin/wearable-computer/wiki/Photos-and-video)

## Motivation

I am proficient in software engineering in Unix-like environments. Until I have built and polished the wearable computer, I couldn't get full benefits of this in all sorts of 'on the go' environments, for example, while walking or looking after my kid.

The advancement of the smartphone technology has brought huge benefits to the civilisation, making it affordable for many people to have a portable multi-purpose digital assistant with a powerful computing unit and a mind blowing amount of data storage.

However great it is, Unix geeks know we could do better. Being used to modifying and combining the software in our systems easily, it's hard to give up these freedoms. Both iPhone and Android, while having FOSS components, make it very hard and risky to modify the software. The only approved way to extend the functionality of the system is to (create and) install a necessary purpose-built application. But developing even a simple mobile app on these mainstream platforms requires orders of magnitude more effort than writing a simple Unix script, needs more rare skills, and in the end, mobile apps don't lend their power to each other as Unix programs do. This is why the community effort for making the traditional Unix-style environment available to users never stops, despite the lack of backing by large corporations: affordability of custom computing.

## Specification

### Hardware

#### Chassis

['VIA Gecko' running vest by Montane](https://www.montane.co.uk/packs-c98/via-gecko-vest-p769).
![Photo of the vest](https://raw.githubusercontent.com/andrey-utkin/wearable-computer/master/img/via-gecko-vest.jpg)

There are many manufacturers making such vests. My choice was based on such factors:

* big enough side pockets,
* discreet appearance.

#### Power supply

[RAVPOWER RP-PB19](https://www.ravpower.com/products/rp-pb19-16750mah-power-bank)
![Photo of the USB Power Bank used as the power supply](https://raw.githubusercontent.com/andrey-utkin/wearable-computer/master/img/rp-pb19.png)

Two ports: 2.1A and 2.4A max.
2.1A port delivers stable power even when you start and stop charging it. This makes it an uninterruptible power supply, making it possible to have uptime of many days.

Capacity: 16750 mAh/61.9 Wh  
Input: DC5V/2A  
Output: DC5V/4.5A Max Total

#### Computing core

Raspberry Pi 4. 4 GB RAM edition.

Enclosed in a FLIRC metal case for heat dissipation.

#### Input and output devices

##### [Twiddler 3](https://twiddler.tekgear.com/)
![Photo of Twiddler](https://raw.githubusercontent.com/andrey-utkin/wearable-computer/master/img/twiddler.png)

A joystick and a chorded keyboard.

Can be used via Bluetooth or via USB cable.

##### Bluetooth earpiece

[Jabra Mini](https://www.jabra.co.uk/bluetooth-headsets/jabra-mini)

Optional.

I just had it before, and I used it paired to both the wearable computer and my Android phone, which works flawlessly.

##### Wired earbuds

[Avantree Sports Headphones](https://www.amazon.co.uk/gp/product/B078T9HFDJ/ref=ppx_yo_dt_b_asin_title_o00_s00?ie=UTF8&psc=1)

Just any cheap earbuds. Wires are messy, but more reliable audio delivery than Bluetooth is handy to have as an option.

Most of time I keep them in the upper pocket of the vest, so that I hear the notifications.

#### Accessories

##### Arm mount for a smartphone

[Rotatable and detachable armband phone mount by VUP](https://www.amazon.co.uk/VUP-Rotatable-Universal-Compatible-Smartphone-Black/dp/B06XSZ375C)
![Photo of the armband](https://raw.githubusercontent.com/andrey-utkin/wearable-computer/master/img/armband.jpg)

Android phone turned out to be a very good display for the wearable computer, it just needs to be connected to it via VNC protocol.

Strap your phone to the wrist of the same hand which holds Twiddler.

#### Bill of materials


|Item          | Price
|--------------|---------
|vest          | 75 GBP
|power bank    | 22 GBP
|rpi4          | 55 GBP
|twiddler      | 200 GBP
|wrist band    | 8 GBP
|wired earbuds | 14 GBP
|earpiece      | 20 GBP

### Software

#### Operating System

Raspbian Linux is a good starting point, but as  person with Gentoo background I am now using gentoo-on-rpi-64bit - rpi-targeted gentoo-based downstream distro by Sakaki.

#### Applications

##### VNC

The tool of my choice for getting visual information from my wearable computer is VNC (I used Vufine+ HMD but it is not as productive and comfortable).

To share an existing X11 session via VNC, i use `x11vnc` package.

To connect to it from Android phone, I use `MultiVNC` package from F-Droid.

To get network connectivity between them I use many different methods.

* Use local wireless LAN.
* Enable Wifi tethering on Android.
* Connect with a USB cable and enable USB networking.
* Plug an additional Wifi adapter into Raspberry Pi, run `hostapd`, use that access point by Android.

##### Calendar notifications

I get notifications about upcoming calendar events via

* synthesized speech to audio outputs (all connected - bluetooth and wired),
* text message to my MiBand 3 wristwatch.

I use a small program I wrote myself for this. I will publish it soon.

##### Web browser

Normal, full-blown desktop browsers such as Firefox and Chromium are available.

This means all sorts of good things. For example, following Google Maps URL doesn't redirect you to the phone application, which in turn requires you to log in with Google Account on your device. It just opens the web application of Google Maps.

##### Any Linux desktop applications

It is very nice to be able to use the same applications, and hence workflows, on the go. Whatever you use, as long as it runs on aarch64 architecture and with 4 GB of RAM, will work.

## Rationale

## References

### My primary inspiration

In this short article on a mainstream technology news site, Paul Miller demonstrates how trivial it is to build a wearable Linux computer in 2017.

https://www.theverge.com/platform/amp/circuitbreaker/2017/7/27/16035508/diy-wearable-computer-google-glass-raspberry-pi-instructions

### Pioneers of wearable computing

#### Steve Mann

http://wearcam.org/steve5.jpg

#### Greg Priest-Dorman

https://www.cs.vassar.edu/people/priestdo/wearables/top

I like how he uses a term "On Body Linux".
