# Postage-Board
A repository for all information and files related to the Postage Board
![Postage Board](https://i.imgur.com/C38yho7.png)

**Postage Board**

Greetings everyone.  If you're here, then you are probably interested in hand-wiring a custom mechanical keyboard!

If this is your first time hand wiring a keyboard, I would recommend reading one of the several great guides out there for how to hand wire a keyboard.  [Matt3o's guide](https://deskthority.net/workshop-f7/brownfox-step-by-step-t6050.html) is the first one I read a long time ago.  [Cribbit's guide](https://geekhack.org/index.php?topic=87689.0) is newer, and more detailed.  

On this document, I will list any relevant specs and details about the Postage Board.  At the bottom I will list any FAQs that I come across.  

***What is the Postage Board?***

The Postage board is a controller board meant to aid people in making a hand wired keyboard.  Controller boards are essentially the brain of the keyboard.  It is similar to the common Teensy 2.0, and also the Pro Micro.  

However, neither the Teensy, nor the Pro Micro are designed for keyboards specifically.  They are just general Arduino-like boards meant for a variety of DIY projects.  The Postage Board is designed for mechanical keyboards specifically, and thus the process of assembling your keyboard is easier, and the final product is more refined.

**General details**

 - Uses an Atmega32u4 microcontroller.
 - Compatible with both Cherry MX and ALPS switches.
 - 25 IO pins available for your rows and columns, or other IO functions such as LEDs.
 - Can cover a TKL keyboard.  Could also cover a 104-key board if you got creative with your rows/columns.
 - Board is 5V, and the Atmega runs at 16mhz
 - USB Type-C connector

***What makes the Postage Board better?***

The Postage Board is designed to solve a variety of problems/annoyances that you might face if you built a hand wire keyboard using a Teensy or Pro Micro.

 - The controller board is designed to mount to the bottom of 3x switches on the top row of your keyboard, [See Pic](https://i.imgur.com/jqfdTKT.jpg).  
 - Because it is mounted to the underside of the switches, the board doesn't take up any extra space beneath the switches.  Many hand wire keyboards end up being 15mm or 20mm thick (distance from the top plate to the bottom) because you need to add extra space for your controller board.  With the Postage Board, you can easily build your keyboard 10mm thick, or possibly even 8mm thick with some trimming of the switch pins.
 - The Postage Board has a USB Type-C connector!  Compared to the Pro Micro having a USB Micro connector, and the Teensy having the *ancient* USB Mini.
 - The Postage Board has space designated for the user to solder on a 3.5mm TRRS headphone jack to be used for split builds using either Serial or I2C communication.  The board has pads ready for you to also solder on 0805-size 4.7k resistors for the I2C lines.  

**Is the Postage Board compatible with QMK firmware?  How do I make the firmware?**

The board is QMK compatible.  It is also compatible with GUI-based Firmware generators like http://config.qmk.fm and http://www.kbfirmware.com for those who don't want to learn how to write the firmware manually.  Just keep in mind that the Postage Board doesn't have a reset button (used for flashing), instead it has 2 pin holes in the bottom corner that you can short-out using a piece of wire, or a paperclip.

**How do I flash my firmware to the Postage Board**

Since the Postage Board uses the same Atmega32u4 as the Pro Micro, you can use most of the same flashing methods as the Pro Micro.  Including AVRDude, AVRDudess, or QMK Toolbox.  I'm a fan of QMK Toolbox, as it is GUI-based, and very simple to use.  Check out [Mechmerlin's tutorial on QMK Toolbox](https://www.youtube.com/watch?v=VR53Wo9Z960&).

**Can I mount the Postage Board to any of the keys on my top row?**

Yes!  You can mount the Postage Board wherever there are 3 keys on your top row (with 1u key sizing, and no spacing between the keys).

**Can I mount the Postage Board vertically along the side of the keyboard, to place the USB on the side?**

Yes.  However, keep in mind that you will also need to rotate the switches on that edge accordingly to allow the board to face that way.  This might create keycap/switch collision issues with some brands of Cherry Profile keycaps.  See the question at the bottom regarding this.

**Are there any issues that I might face needing to rotate 2nd Row switches 180 degrees?**

Yes, there is one possible issue.  Some brands of Cherry-Profile keycaps have clearance issues when the switches are rotated.  You don't need to rotate all of the switches on the 2nd Row, only the ones directly beneath the Postage Board.  I have tested this myself with a few brands of Cherry Profile keycaps, and here are my findings:


Gateron PBT (EnjoyPBT)-----No issues 

NPKC PBT (lots of Chinese sets)-----No issues 

GMK Double-shot-----Side-wall collides 

OEM Cherry-brand Double-shot-----Side-wall collides 

OEM Cherry PBT-----Untested 

OEM Cherry POM-----Untested 

*All other keycap profiles (that are known to me) have no issues with being rotated.*  Keycap profiles like DSA and XDA are symmetrical in shape, so there isn't even a difference in the shape of the 4 sides of the keycap.  Even asymmetrical keycap profiles like SA or OEM don't appear to have any issues with being rotated.

For Double-shot Cherry-profile keycaps that have collision issues, the only issue is that the side-wall of the keycap collides with the switch housing about 1mm before bottom-out.  It still functions, but you lose a bit of key travel.  Several keyboards natively use 180-degree rotated switches, and people have found some solutions.  Using rubber O-Rings beneath the keycaps is a good solution.  

Personally, the collision issue doesn't bother me.  I tried GMK caps on my first Postage Board build, and I couldn't actually tell that they lost 1mm of travel. To me, they feel like they are bottoming out normally.  I had to hold the keyboard up and press a rotated and non-rotated key side by side to see the difference.
