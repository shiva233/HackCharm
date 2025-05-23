# HackCharm
A tiny circular keychain with a pixelated face on an OLED that reacts to taps/shakes to change its expression. It is basically a cute interactive keychain!!

# Hack-Charm Devlog / Creation Journal

## May 22nd: Planning/Designing on my notebook!

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
