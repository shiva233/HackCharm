---
title: "HackCharm"
author: "Shiva Prakash"
description: "HackCharm is a tiny, keychain-sized pixel buddy that lives on your hip, lights up with adorable faces, and reacts to your taps, shakes, and love :D"
created_at: "2025-05-22"
---

# Hack-Charm Devlog / Creation Journal

# May 22nd: Planning/Designing on my notebook!

**Hi hi!! Today, I spent the majority of my day planning out HackCharm!! It is basically a no-maintenance little Tamagotchi-type thing that lives on your keychain and displays adorable faces on its screen. It will also react to stuff like tapping, shaking, or pressing a button!!**

I have a scan of my planning page in my notebook that I will explain:

![image](https://github.com/user-attachments/assets/e1e8352f-564e-4c1e-8981-4ad7a2d6b855)

### Design (The sketches): 
- Basically the design is pretty much shaped like a pocket watch but without the chain and the watch face is a little screen with an adorable face on it!!
- Back: The back would have some logo or symbol engraved (right now I'm debating between HC (for hack club or hack charm) or a smiley face :D)
- The back also has a button on it for controls.

### Tech / Circuitry

- HackCharm will be controlled with an **Xiao-ESP32-S3**
- It will be connected to an SSD1306 OLED Display Module
- The back of your HackCharm will have a button for some additional controls
- Your HackCharm will have an accelerometer (haven't found a specific one yet) to detect shaking and tapping
- Your HackCharm will have a rechargeable battery built in (haven't found a specific one yet). 
- Your HackCharm can be charged through a USB-C port on the bottom.
- Wiring!! Not everything is laid out yet, but basically for the Display it will be as follows: 

| Display Pin    | Xiao-ESP32-S3 |
| -------------- | ------------- |
| GND            | GND           |
| VCC            | 3.3V          |
| SCL            | D5            |
| SDA            | D4            |

- During this design phase, I completely forgot to think about the battery, and I still need to figure out how to implement that!!
 
### Faces / Expressions!

I want the faces and expressions to be triggered by a few different things, such as shaking, tapping, pressing the button, etc. But at a bare minimum, I want a cute idle animation and a "woken up" animation. I have a few sketches on potential face designs in the picture as well :D

### Build
 
On the top-right, you can see a sketch of how the build is going to look like, basically it's gonna be a PCB sandwiched between two 3d printed shells!! :D

### PCB

I laid out the basic layout for the PCB. Basically, the main points are:
- The Display and its pins will be on the front side of the PCB
- Everything else would be on the back, including the Xiao-ESP32-S3.
- I realized later that the ESP32-S3 needs to be near the top or bottom of the PCB so there is access to the USB-C port.
- I'm not really sure yet how I'm gonna maneuver the battery into all of this because the ESP32 has two SMD Pads for battery connections, and I'm not sure how to maneuver the ESP32 to solder the battery onto it while it's on the PCB or even connect those pads to the PCB.

### RAAAAA I'm SUPER EXCITED TO KEEP WORKING ON THIS!!

That is pretty much it for today. tmrw I will work on trying to make the circuit in a simulator so I can start PCB design :D

Other things that need to be done:
- Designing cute faces in Aesprite
- Learn the basics of KiCad since I have only used EasyEDA so far
- Make the PCB!!
- Model the enclosure/shells
- Make a logo/banner (gonna be inspired by AirTag promotional material since it would be a similar shape)

**Total time spent: 5h (spread across the day)**

# May 25-26th: Identified the rest of the components and completed the schematic!

TADA here is the schematic:
![image](https://github.com/user-attachments/assets/a31f697f-1793-4e53-af15-264d5255bcc2)

It is not really clean because I am not good at making schematics (yet!! I will clean it up later).

But as you can see we have chosen an accelerometer! I chose the adxl362 and I found [a breakout board from SparkFun](https://www.sparkfun.com/sparkfun-triple-axis-accelerometer-breakout-adxl362.html) that helped me make this schematic. I am going to be using this for majority of the interactions with the HackCharm. (speaking of I might change the name to something more interesting)

I am still learning how to use KiCad since I only have experience with easyEDA, but I feel like I did a good amount of work today with the schematic.

Also I figured out how to use a battery with the XIAO-ESP32-S3 from [their documentation](https://wiki.seeedstudio.com/xiao_esp32s3_getting_started/)
![image](https://github.com/user-attachments/assets/66cee0a5-315c-48a8-ab82-c7252b831783)

The one drawback is that you cant tell what the battery percentage is, so that is something I will have to work around.


**Total time spent: 3h**

# May 27th:
![image](https://github.com/user-attachments/assets/34da7635-175e-4302-b9a0-6685d26598e1)

So I had to change up my schematic because apparently the symbol/footprint I had for the accelerometer was kinda goofy. So I got a new one and I had to redo the schematic, which I think I spent around **1 hour** doing. 

So after doing that I worked on the PCB itself!! this is my first time using KiCad so I dont know if I did this right but tada:

![image](https://github.com/user-attachments/assets/16329d58-4848-4dc4-a271-25b75593ea1a)

I manually routed all of the connections except for the ground line where I just made a copper fill for that. I had to be a bit creative with some of the routing especially around the adxl362.

![image](https://github.com/user-attachments/assets/39a385f6-84a9-4db4-a213-d48312c58313)

I have no idea if the routing I did is "legal" or if it works but I will research that more before I finalize this pcb!!! Right now I am bored with routing so I am gonna focus on the aesthetics aka SILKSCREEN ART!!!

### UPDATE 2:

I have spent the last 2 hours thinking up lore and cryptic messages that I can hide/involve with this project and its been really fun but since its not directly working on the hardware end of this project im not going to include it. But anyways there is gonna be some cool stuff involved!! 

I have made a few documents of lore that I plan to hide in places around the project (like the pcb, flash memory etc). Obv I would really be the only person who would see this but who knows maybe one day I would try and sell this.

**Total time spent: 4h**

# May 28th: (DONE THE PCB!!! Moving on to 3d modelling)

I spent over like 2 hours making silkscreen art (really like 30 minutes of making the art and then an hour and a half trying to figure out how to make it look nice in KiCad)

Design:
![image](https://github.com/user-attachments/assets/9ccd7ec5-0f88-4c79-9b60-1e85f425fa5f)

Was trying to go for a made in a scifi lab vibes

![image](https://github.com/user-attachments/assets/575bd596-58ef-4e14-a149-045c796ae2e0)

Tada!! this is what the back looks like :D

**Total time spent: 1h**


