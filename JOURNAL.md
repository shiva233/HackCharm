---
title: "HackCharm"
author: "Shiva Prakash"
description: "HackCharm is a tiny, keychain-sized pixel buddy that lives on your hip, lights up with adorable faces, and reacts to your taps, shakes, and love :D"
created_at: "2025-05-22"
---

# HackCharm Devlog / Creation Journal


## Total Hours spent on Design Phase: 25 Hours


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

This took me **1 hour**

### UPDATE 3:

NOTHING WENT WRONG WITH JLC PCB WOOO!!

![image](https://github.com/user-attachments/assets/08a71a01-058e-487e-85ae-e75e41a7e15b)

Look at that price difference wow! This was all worth it :D

With that I can make the final BOM:

### BOM

|**Item**|**Purpose**                     |**Source**|**Price (CAD)**                                 |
|----|-----------------------------|------|---------------------------------------------|
|Xiao-ESP32-S3|Controller                   |AliExpress([Link](https://a.aliexpress.com/_mr6FPuF))|$11.08                                       |
|128x128 OLED Display|Output                       |AliExpress([Link](https://a.aliexpress.com/_mNI13Ir))|$8.44                                        |
|GY-362 ADXL362 Accelerometer|Input                        |AliExpress([Link](https://www.aliexpress.us/item/1005007113522695.html?spm=a2g0o.productlist.main.1.41835e6cqzVJ25&algo_pvid=fee97835-5e5c-4af8-af68-d18792b41281&algo_exp_id=fee97835-5e5c-4af8-af68-d18792b41281-0&pdp_ext_f=%7B%22order%22%3A%2216%22%2C%22eval%22%3A%221%22%7D&pdp_npi=4%40dis%21CAD%213.55%213.55%21%21%2118.22%2118.22%21%402101effb17496335958893809e6e64%2112000039448744636%21sea%21CA%210%21ABX&curPageLogUid=qWPVdHTwuQrT&utparam-url=scene%3Asearch%7Cquery_from%3A))|$5.35                                        |
|2.54mm Headers |Connector                    |AliExpress([Link](https://www.aliexpress.us/item/3256805470972472.html?spm=a2g0o.cart.0.0.624538daxjmIoN&mp=1&pdp_npi=5%40dis!CAD!CAD%203.12!CAD%203.12!!CAD%203.12!!!%402103244417496191960858421e5267!12000033913162578!ct!US!4143424543!!1!0&pdp_ext_f=%7B%22cart2PdpParams%22%3A%7B%22pdpBusinessMode%22%3A%22retail%22%7D%7D&gatewayAdapt=glo2usa))|$3.43                                        |
|2.54mm Headers (Right Angle)|Connector                    |AliExpress([Link](https://www.aliexpress.us/item/32980998451.html?spm=a2g0o.productlist.main.16.1e206f5diQ6mzC&aem_p4p_detail=202506110216214608937190897820001237152&algo_pvid=1bfe327d-1faf-4c35-8583-72ae0c25e16f&algo_exp_id=1bfe327d-1faf-4c35-8583-72ae0c25e16f-15&pdp_ext_f=%7B%22order%22%3A%22226%22%2C%22eval%22%3A%221%22%7D&pdp_npi=4%40dis%21CAD%212.42%211.72%21%21%211.73%211.23%21%402101c67a17496333817923185ec293%2112000036953272482%21sea%21CA%210%21ABX&curPageLogUid=yeAT6i39rNGo&utparam-url=scene%3Asearch%7Cquery_from%3A&search_p4p_id=202506110216214608937190897820001237152_5))|$2.60                                        |
|TS-1088 Button|Input                        |JLCPCB (PCBA)|        ----                                |
|PCB |PCB                          |JLCPCB|   $5.77                                          |
|LI-PO Battery 3.7v 450mAh|Power                        |Self-Sourced|$12.99                                       |
|3D Printed Casing|Housing                      |Self-Sourced|$0.00                                        |
|**Total (CAD)**|       ----                      |   ----   |**$49.66**                                      |
|**Total (USD)**|           ----                  |   ----   |**$36.25**                                       |

**Total time spent: 3h**

Which means...

# I AM OFFICIALLY DONE WITH THE DESIGN PHASE!! (Thank you for reading my entire journal! (design phase)


# June 28th - THE PARTS HAVE ARRIVED MWEHEHE

![image](https://github.com/user-attachments/assets/7dcc5d46-97bb-4d5e-97a6-08f253861383)

IM SUPER EXCITED CUZ ALL OF THE PARTS ARE HERE AND NOW I CAN START BUILDING IT YIPPEEE

Update 1:

Everything has been soldered!! I inhaled a lot of yummy solder fumes (dont do this I just did not lock in with my ventilation)

Update 2:

YEYSYSYSY YESS I GOT A FACE TO SHOW UP ON THE SCREEN!! THAT MEANS MY PCB WORKS AND I DIDNT FUCK UP YAYYYYYYYYYYY

I had to do a lot of messing around for the image to show up properly, I forgot to take pics while it was not working properly but basically it all boiled down to me declaring the oled wrong oops. but now its works!! >:D


![image](https://github.com/user-attachments/assets/a683bc1d-2bda-4237-9c8b-d51185638dd4)

I am very proud of myself!!

here is a pic of it in the case :0

![image](https://github.com/user-attachments/assets/ae8f1bfa-1b8c-426e-8ad6-850d878068b8)

I did notice however some problems in the case: the tolerances for the oled display hole, the location of the keychain hook, and usbc port.

I will be changing these things and reprint tmrw!!

**Total time spent: 4h**

# June 29th - Mostly worked on the magazine page today :0

I didnt really document majority of the poster making process but I wanna show it off anyways :D

here u go: 
![HackCharm - Shiva Prakash _D](https://github.com/user-attachments/assets/ed7028e8-7035-4e55-b2e2-82c096a017a8)

Also bonus but I made an owo? screen hehehe

tadaaa: 
![image](https://github.com/user-attachments/assets/77c0a0e3-28a4-455f-ba35-a646bfd468e7)

**Total time spent: 2h**

## June 30th - Case reworks + Ideas for more expressions :D

Alright so the case has a few problems like I mentioned before, the display is way too tight and doesnt fit properly, I have to rotate the image to make it make sense with the keychain hook (like the face is facing sideways if you hold it with the keychain hook facing up), and the usb-c ports placement is kinda messsed up like its not in the best spot to make everything fit properly, and finally the pcb didnt fit snugly into the case without me extruding a bit further down :0

Tada: This is v1, v2, and v3 of the HackCharm case :D

![image](https://github.com/user-attachments/assets/69dd6537-4741-4c2d-9c6c-ba95cb9cce39)

also if you are wondering why the third one suddenly looks so much smoother, its actually because im a 3d printing genius who was able to dial all of his settings in perfectly! (im joking its because I decided to stop being dumb and print the flat side facing down instead of facing up with supports below)

![image](https://github.com/user-attachments/assets/38f61e87-99ba-4ff8-aed1-ba690eb54446)

2nd thing I did, I realized that the jumper wires were being annoying and requiring way too much space to fit into the case without manuevering it in some weird way (how evil you vile jumper wires) or making the case bigger (which I dont wanna do!)

Anyways to combat these evil jumper wires I cut off their heads and soldered the ends directly to the PCB >:D (I have like a ton of these so i dont feel that badd)

Anyways the soldering job was really bad because I am really bad at soldering wires compared to THT D: but oh well it works yayay

![image](https://github.com/user-attachments/assets/ad4ccacb-a361-426b-9f10-00d212d437ad)
![image](https://github.com/user-attachments/assets/49ee170e-3ef8-4a2e-9c5a-3716d003faae)
It still works^ YIPPEEE

So yeah basically I realized that using the right angle jumper wires ended up just taking way too much space and so soldering it was the best option. I think this is one of those things I wouldnt have realized until I actually started building it physically so I dont really regret designing around the right angle jumper wires originally :0

ok and then I put some electrical tape over the back of the OLED because I was concerned about something from the pcb touching it and shorting it D:
![image](https://github.com/user-attachments/assets/90a8c98a-f675-465a-9fcb-857ae6eea8b5)

![image](https://github.com/user-attachments/assets/ed1f4d04-359a-40ec-a8a8-e1a55a1f5813)

Too tired to make the lid today sooo im gonna improvise >:)
![image](https://github.com/user-attachments/assets/6187f49d-e1c5-4c3f-8faa-4b6e6c9a63cd)

hehehe

And final thing that im probably gonna work on tmrw, I planned out a few more faces/expressions/animations HackCharm could have and what triggers them. I drew out a state machine (barely know what this means not sure if im using it right) in my notebook that I will show in tmrws entry :D

**Total time spent: 2h**


## July 2nd - Messing around with the accelerometer!

Hi hi today I tried to get the accelerometer to work so I can start actually interacting with HackCharm, I know I said I would work on more expressions and stuff next but I wasnt really feeling.

Anyways I figured out after a lot of googling and worrying that I messed up my PCB how to read values from the accelerometer :D

Tada:

![image](https://github.com/user-attachments/assets/905753b4-e5d7-4b82-83fa-559baac8faa3)
 
Now I need to figure out how to make this interactive hmm


# July 4th - Locking in for the firmware!

Ok so here is how the firmware is going to work in my mind, basically there is going to be a bunch of seperate gifs for each 'state' of HackCharm like sleepy, idle, shaking reaction, tapping reaction, dizzy etc etc!

and I am going to use a function with a switch case to go draw these states like this 
![image](https://github.com/user-attachments/assets/d3c15544-b663-417b-8998-0fa916574c61)

And within my loop I am going to call this function to draw the appropriate face/gif. So all I need to do after I set this up is make functions to detect tapping and shaking and change the variable used in the switch case apropriately when each is detected. I also need to make functions to detect other things like idling for too long which results in sleeping etc etc!!

So far I have spent around 1 hour on the firmware!! I will update in a bit

(so I did not get to work on it more today oops)

**Total time spent: 1h**

# July 5th - More locking in for firmware!

I present to you... shake detection!

Tada:

https://github.com/user-attachments/assets/b34e21b9-1d90-43d4-b4d2-34406f461e84

Our lil buddy can now detect if you are shaking him :D, for now its really simple but im super glad this worked because its kind of like a proof of concept?? a bit late I know but still im excited :D

here is the code or well part of the code that makes this work:

```c++
void loop(void) {

  xl.readXYZTData(XValue, YValue, ZValue, Temperature);  
 // Convert to m/s^2
  float x = XValue * 0.0098;
  float y = YValue * 0.0098;
  float z = ZValue * 0.0098;
  float avgAccel = (x+y+z)/3;

  // info in serial monitor
  Serial.println("m/s^2 --> x: " + String(x, 3) + "\t, y: " + String(y, 3) + "\t, z: " + String(z, 3));
  
  if (avgAccel >= 5|| avgAccel <= -5)
  {
    Serial.println("testing testing monkey monkey");
    
    if (currentState == TAP_REACTION){
      currentState = IDLE;
    }
    else
    {
     currentState = TAP_REACTION;
    } 
    
    delay(1000);
  }

  drawState(currentState);

  delay(500);

}
```

also bonus here is another face I drew:

![image](https://github.com/user-attachments/assets/a7fee61a-4ed6-4873-82ef-65668dbf808b)

hehe dizzy

Oh btw I put everything on an another PCB cuz the wires broke off and I was getting annoyed with the solder job on the old PCB anyways so here is the solder job on the new PCB!

here u go:

![image](https://github.com/user-attachments/assets/6b398135-9217-4ba2-b097-1d1231eefedb)

![image](https://github.com/user-attachments/assets/ba02b7a7-b422-45cb-9d76-71bd46ae7b9e)

time spent so far is an hour ish I think including the soldering

**total time spent: 1h**

# July 5th - Firmware for the prototype is almost done!

yayaya so basically its almost done I spent a lot of time working on this today, made a few functions and basically HackCharm is a lot more smart now!! (bro can go to sleep now and wake up, and also react to taps and shakes mwehehe)

So basically HackCharm's prototype's firmware is complete and now just needs some finetuning on the sensitivity/thresholds for triggering animations and well the actual animations themselves to be added (I havent drawn a lot of them yet, there are just placeholders and single frames for now).

But the transitions between animations/states works exactly like i want it to yay :D

This is what I want the HackCharm state machine to look like:

 ![image](https://github.com/user-attachments/assets/c04f1d2f-69b6-4254-a98a-fe28aeed2c2b)

So basically you start at the IDLE expression and based on if HackCharm is shaked ot tapped it goes into those respective reactions. For the prototype I want tap to have atleast 3 possible reactions that it chooses from randomly and for shake for the protoype it will have one reaction (wee) but if you keep shaking it while it is in the shake reaction it will go into dizzy mode hehe.

Oh and if you dont do anything for a bit (right now its set to 15 seconds) HackCharm will go to sleep (honk mimimimimi zzzzzzzz) and if you do any movement like tap or shake it will go into WAKE animation/state and then come back to IDLE :D

btw I think I will add on more animations but for the purpose of shipping the project in a good timeframe im gonna stick to 3 tap reactions and the pair of shake reactions and that should be good for now :0

So this is what I did with the firmware today :D here is a demo video (the thresholds for triggering the animations arent perfect yet, and obv these are placeholder images for the actualy gifs/animations and there will be a few more animations): 

https://github.com/user-attachments/assets/a061cae9-3c47-4f08-acf6-5f305ff23169


Next steps are gonna be actually having gifs for each state (so a lot of time in aesprite hehe) and then adjust the thresholds for triggering the animations a bit :0
**Total time spent: 4h**


# July 9th - Running out of time undercity is almost here D: but made progress!!

I finished one of the animations, the one for sleeping!

tada:


https://github.com/user-attachments/assets/e7540694-95f3-4715-bdbc-39b0418a3a95


