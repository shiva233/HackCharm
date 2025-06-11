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

Tada!! This is what the back looks like :D

**Total time spent: 1h**

# June 6th

![image](https://github.com/user-attachments/assets/899f5359-3983-40c7-ae91-70b02ef63c54)

I wanted to write some code but since I dont have the components physically yet I used a [simulator!]([wowki.com](https://wokwi.com/)) 

And then..., I realized the simulator with the above screenshot could not actually simulate the components so I used another one!! this time with just the display so I could focus on figuring that out:

![image](https://github.com/user-attachments/assets/7f91de0f-eb96-471e-bcea-e2e3991b6a6a)

Here is the face I drew in Aseprite:

![image](https://github.com/user-attachments/assets/72afe30a-6a0a-4577-acfc-332dba80066b)


To make the image readable/displayable by the esp32/oled I had to convert it to Byte Arrays using this website: [image2cpp]([url](https://javl.github.io/image2cpp/))

![image](https://github.com/user-attachments/assets/efc9dde7-778d-414a-bc2d-170dd4981227)

**IMPORTANT:** When using image2cpp you must check the "swap" checkmark since we are using the u8g2 library   

![image](https://github.com/user-attachments/assets/d2137b67-915b-48cd-9a71-16c2e9828eb6)

Im still trying to figure some things out and I have no idea if it works but tada! below I have the code that makes HackCharm display a lil face on its screen :D

Here is the simulator displaying the face!

![image](https://github.com/user-attachments/assets/1a33e856-0fd0-4cd5-9785-dc142b0808e5)

Im super excited because now the project feels like, extra real?? Finishing the PCB also made me feel kinda like this but this like a different version of that if it makes sense.

**I have pushed this simulator version of the sketch to the [repo](HackCharm/sketch.ino), once I actually get the components and pcb I will work on the final version of the sketch (with accelerometer, button etc)**

Now all I need to do is CAD the case for HackCharm and im done the design phase!!

also bonus sketches:

![image](https://github.com/user-attachments/assets/ac339692-70fe-449a-85dc-0bdaa39d6ccf)

**Total time spent: 2h**

# June 7th


I decided to reroute the PCB after moving the esp32 up so that the usb-c port could be accessed more easily

Before: 
![image](https://github.com/user-attachments/assets/ea84430f-c7e4-40d5-b32e-51a8a6799e7b)

After:
![image](https://github.com/user-attachments/assets/37b8401c-6994-4eab-a3c4-d9b50d3ffac8)


Turns out that top part of the footprint IS supposed to be outside the PCB so the USB-C port is accessible. U can see it in this 3d model !!

![image](https://github.com/user-attachments/assets/80a52c1b-d74c-4db8-891a-7f84c715bfe4)

![image](https://github.com/user-attachments/assets/4750a183-8f86-442a-a4f9-7b841e2be54f)

Update: I have also started to work on the CAD model!! I am still learning fusion360 so I dont know a lot of things but here is my progress so far:

![image](https://github.com/user-attachments/assets/4d55491b-0c7a-49eb-8a2a-12410369172c)


**Total time spent: 2h**

# June 10th

AAAA ITS EXAM WEEK IM SCARED, so I work on this to distract myself.

Restarted the cad model cuz the previous one was kinda stinky:

![image](https://github.com/user-attachments/assets/91694027-de50-45f1-b312-46660320cd81)

Progress so far!! 

Sketch:
![image](https://github.com/user-attachments/assets/e0abdea3-ac84-422f-9492-04daa4e2504f)

Basically, what I did is make a square cut out into a circle and then like a rectangular slot behind it. Basically what im trying to do is have a square screen on the final product while using a rectangular screen!!

Now all I need to figure out is how to make a usb-c cutout and make a lid for this. Oh, and the keychain slot!!

**Note: I am inexperienced with Fusion360 and CAD in general so the methods I used may be unorthodox and are usually just me guessing/experimenting on my own. By no means are these best practices**

UPDATE 1:

![image](https://github.com/user-attachments/assets/9d3d078d-fa3a-4bfe-90a4-7000745d9dc9)

Added the cutout for the USB-C cable to go through! I did this by making a rectangular sketch of 6mm by 10mm (I straight up just measured my USB-C cable with callipers and added a few mm for safety!!) then I extruded it backwards to make the cutout :D

Next I will add the keychain hook!

UPDATE 2:

![image](https://github.com/user-attachments/assets/ba3ae7fc-1c12-479a-a44a-04473ce40d84)

Made a sketch for the hook, not sure if this is the most optimal way but based on what I know about using fusion360 so far this is how I would go about it.

I went to my original sketch on the plane where I made the actual frame it self, and I added a circle to the end of one side for the hook and made half of it inside and half of it outside, and then I gave that circle an offset of 2mm for the thickness of the hook.

![image](https://github.com/user-attachments/assets/23d1f1cb-1878-4e88-b99d-087476c664ec)

It worked!! but oops the hook in relation to the usb-c cutout is in a weird spot, so I will change it in the sketch!!

Tada new sketch:

![image](https://github.com/user-attachments/assets/199b1c37-de24-4012-8e31-25ec28d732fa)


And this is what it looks like after extrusion:

![image](https://github.com/user-attachments/assets/59d202c3-e15d-4392-9bb8-67997e4198d9)

So I'm basically done with everything except for the lid!! (this is the part I have no idea how to do so I need to do some googling and or watch youtube videos on it).

UPDATE 3:

Im done!! and I have made it look slightly nicer by messing with fillets to round the edges on the frame, hook, and screen cutout!

Before:

![image](https://github.com/user-attachments/assets/8d910c7e-68e3-4f8a-bec9-ed47e2272505)


After:

![image](https://github.com/user-attachments/assets/fb6e7960-43b3-48d7-ba18-f87b75756452)

UPDATE 4:

look! I made a lil orthographic drawing thingy for the model!!

![image](https://github.com/user-attachments/assets/eae0dfcc-f628-4293-aa6b-940ce24b5ebd)


**Total time spent: 5h**

# June 11th - GREAT MISFORTUNE


**Bad News:**

![image](https://github.com/user-attachments/assets/f8352acd-974f-4a64-a82b-7795514fd885)


Sooo as it turns out I CANT GET MY ACCELEROMETER ASSEMBLED BY JLC PCB WITHOUT DOING STANDARD ASSEMBLY

And I dont want to do standard assembly because:
- it costs 50 dollars,
- it FORCES me to make my board twice as big
- and it forces me to add edge rails to my board


**Good News:**

I can replace the ADXL362 Chip with a breakout board I found on aliexpress and through-hole solder that onto my PCB!

The breakout board:
![image](https://github.com/user-attachments/assets/739b69ef-8aaf-494e-b958-6ebc73dd74e3)

Unfortunately, this means I will have to pretty much restart my PCB and learn how to make a custom footprint for the breakout board to plug into, but how hard could that be right??

### UPDATE 1:

I have made my own symbol and footprint for the breakout board from aliexpress:

![image](https://github.com/user-attachments/assets/7563137d-1de2-481e-997f-51adad80db4e)
![image](https://github.com/user-attachments/assets/88b3583f-902b-4314-b440-15051409f3be)

**This took me 1.5 hours**

And I have updated the schematic with the breakout board. I also removed the decoupling cap from the old schematic since it is no longer needed.

![image](https://github.com/user-attachments/assets/02687a38-02f6-479b-8af2-51f51816c2f0)

### UPDATE 2:

I LOCKED IN!! I remade the entire pcb RAHHH

![image](https://github.com/user-attachments/assets/dec13835-8def-4a88-8a30-70fbd0f3c82a)

![image](https://github.com/user-attachments/assets/4f720d83-9f7d-4cb7-ad08-1ff185551a1e)

![image](https://github.com/user-attachments/assets/3be39cb3-cc19-4ea0-be70-7af098112e28)


and no DRC errors baby lets go!

![image](https://github.com/user-attachments/assets/ae30869e-763b-4378-bbfc-bd87d46deee8)

Now I gotta upload this to jlc pcb and hope nothing goes wrong!

This took me **0.5 hours**
