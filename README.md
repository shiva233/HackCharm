# HackCharm

![HackCharm - Shiva Prakash _D](https://github.com/user-attachments/assets/158f7c20-f73e-4ecc-8fd4-6e8544891299)

## What is HackCharm???

#### Note: HackCharm is not finished yet! It is still being developed, you can see the [journal/devlog here!](JOURNAL.md) :D It has updates around every week and you can see how I got to this point!

_**HackCharm**_ is a tiny, keychain / lil buddy that lives on your back or your keys and lights up with cute little faces! It will react to your taps, shakes, and any other love you show it!! It shows different emotions on its screen depending on how you interact with it. It's powered by an Xiao ESP32, a custom PCB, and lives inside a 3d printed shell! To sum it up HackCharm is a decorative and interactive no-maintenance tomagotchi mixed with a sci-fi gadget :D

![hackcharm1](https://github.com/user-attachments/assets/0f5f2d32-f441-41b5-a7b8-b7f0d974254a)

## Why did I make it?

I made HackCharm because I really just wanted to build something fun and full of personality! This project lets me bring all my favourite parts about building and tinkering together into this little cute device that I could carry around that can make me (and maybe other people too!!) smile every time I looked at it.  

![image](https://github.com/user-attachments/assets/ac339692-70fe-449a-85dc-0bdaa39d6ccf)


### 3D Model:

![image](https://github.com/user-attachments/assets/60be6617-ccea-4f78-b61b-7c2dc0e006e6)


### Wiring Diagram: (Everything but the screen and battery are on the PCB!
![image](https://github.com/user-attachments/assets/8a4f430f-c54a-4c7f-9d0d-814249a0308f)

### PCB Schematic:
![image](https://github.com/user-attachments/assets/1c08184f-9803-45f0-85b0-a55d2eedba79)


### PCB:

![image](https://github.com/user-attachments/assets/e22d347e-5617-426c-8254-703f25bf74f0)

![image](https://github.com/user-attachments/assets/215260bb-b041-460a-9170-50746c275d3f)

![image](https://github.com/user-attachments/assets/2992bb9d-a93a-40bc-857b-63156cadb17d)


### Simulating some Firmware!

![image](https://github.com/user-attachments/assets/f1a5eea9-8b90-4233-9f8b-234e290ebe85)


### BOM

|**Item**|**Purpose**                     |**Source**|**Price (CAD)**                                 |
|----|-----------------------------|------|---------------------------------------------|
|Xiao-ESP32-S3|Controller                   |AliExpress([Link]())|$11.08                                       |
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
