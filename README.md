# m920q-dual-NVME

![Lenovo M920Q](https://github.com/badger707/m920q-dual-NVME/blob/main/pictures/20180508_lenovo_tiny.jpg)

Goal of this personal project is to add 2nd NVME drive to Lenovo M920Q Tiny by soldering missing SMD components to the board.

Models overview:

| Model | Supported CPU | Chipset | SODIMM RAM | PCIE slot | NIC | Drives| Board Model|
|-------|-----------------------|------------|-----------------------|-------------|----------------------|-----------------|----------------------|
| M920Q | Coffee Lake (8/9x00T) | Intel Q370 | 2 x 32GB 2666MHz DDR4 | PCIe 3.0 x8 | Intel l219-LM (vPro) | 1x M.2, 1x 2.5" | IQ3XOIL Q370 NM-B551 |
| M920X | Coffee Lake (8/9x00T) | Intel Q370 | 2 x 32GB 2666MHz DDR4 | PCIe 3.0 x8 | Intel l219-LM (vPro) | 2x M.2, 1x 2.5" | IQ3XOIL Q370 NM-B551 |

M920Q and M920X are using same board model.
<br><br>

## DISCLAIMER
USE AT YOUR OWN RISK. MICRO SOLDERING REQUIRED. I'M NOT RESPONSIBLE IF YOU WILL DAMAGE YOUR BOARD OR BURN DOWN YOUR HOUSE WITH THIS EXERCISE. IF YOU DONT KNOW WHAT YOU'RE DOING - DONT DO IT.
<br><br>
## FUN PART

Items on hand:
* M920Q Tiny
* tons of pictures of M920X board in high resolution, found on internet
* M920X Tiny schematics (circut diagrams)

In firs steps I started to visualy compare M920X board pictures to my M920Q, just to see how many missing components I will find.
Most of (missing) components are located on top side of the board around SATA and Wi-Fi connectors area.
Few components are on the bottom side of the board where NVME slot is located.

Looking at schematics for 2nd NVME drive circuit - 16 capacitors and 11 resistors needs to be soldered on board, together with M.2 NVME connector.
By comparing my visual findings with schematics and "board view", I was able to locate & identify all of them.

* ### Components list
| Type | Name | Size | Value | Voltage | Board Side |
|-----------|--------|-------|--------|----------|---|
| Capacitor | C363 | 0402 | 0.01uF | 25V7-K | bottom |
| Capacitor | C364 | 0402 | 0.01uF | 25V7-K | bottom |
| Capacitor | C365 | 0402 | 0.1uF | 16V7-K | bottom |
| Capacitor | C366 | 0603 | 10uF | 6.3V6-M | bottom |
| Capacitor | C367 | 0402 | 0.22uF | 16V7-K | top |
| Capacitor | C368 | 0402 | 0.22uF | 16V7-K | top |
| Capacitor | C369 | 0402 | 0.22uF | 16V7-K | top |
| Capacitor | C370 | 0402 | 0.22uF | 16V7-K | top |
| Capacitor | C371 | 0402 | 0.22uF | 16V7-K | top |
| Capacitor | C372 | 0402 | 0.22uF | 16V7-K | top |
| Capacitor | C373 | 0402 | 0.22uF | 16V7-K | top |
| Capacitor | C374 | 0402 | 0.22uF | 16V7-K | top |
| Rezistor | R1302 | 0402 | 0 ohm | - | top |
| Rezistor | R1303 | 0402 | 0 ohm | - | top |
| Rezistor | R631 | 0402 | 0 ohm | - | top |
| Rezistor | R632 | 0402 | 0 ohm | - | top |
| Rezistor | R633 | 0402 | 33 ohm | - | top |
| Rezistor | R634 | 0402 | 0 ohm | - | top |
| Rezistor | R635 | 0402 | 0 ohm | - | top |
| Rezistor | R637 | 0402 | 0 ohm | - | top |
| Capacitor | C377 | 0402 | 0.01uF | 25V7-K | top |
| Capacitor | C378 | 0402 | 0.01uF | 25V7-K | top |
| Capacitor | C379 | 0402 | 0.1uF | 16V7-K | top |
| Capacitor | C380 | 0603 | 10uF | 6.3V6-M | top |
| Rezistor | R639 | 0402 | 0 ohm | - | top |
| Rezistor | RC27 | ~~0402~~ | ~~10 Kohm~~ | - | bottom |~~
| Rezistor | RC24 | 0402 | 10 Kohm | - | top |
| M.2 NVME connector | - | - | - | - | bottom |
| M.2 NVME latch | - | - | - | - | bottom |

Note to self:
> RC27 appears to be not needed, its already on the board(?), however it is listed in slot #2 circuit.

* ### Components list summary:
| Type | Size | Value | Voltage | Count |
|-----------|-------|--------|----------|---|
| Capacitor | 0402 | 0.01uF | 25V7-K | 4 |
| Capacitor | 0402 | 0.1uF | 16V7-K | 2 |
| Capacitor | 0402 | 0.22uF | 25V7-K | 8 |
| Capacitor | 0603 | 10uF | 6.3V6-M | 2 |
| Rezistor | 0402 | 0 ohm | - | 8 |
| Rezistor | 0402 | 10 Kohm | - | 2 |
| Rezistor | 0402 | 33 ohm | - | 1 |
| M.2 NVME connector | - | - | - | 1 |
| M.2 NVME latch | - | - | - | 1 |

* ### Components location - TOP side of the board

9 components on the Left side of SATA port, highlighted in green:<br>
![](https://github.com/badger707/m920q-dual-NVME/blob/main/pictures/IMG_5877_x.png)

12 components on the Right side of SATA port, highlighted in green:<br>
![](https://github.com/badger707/m920q-dual-NVME/blob/main/pictures/IMG_5878_x.png)

Move resistor from R105 to R162. This will switch PCH to work in M920X mode:
![](https://github.com/badger707/m920q-dual-NVME/blob/main/pictures/IMG_5883_x.png)

* ### Component location - BOTTOM side of the board

Only 4 capacitors at the side of NVME connector pads, highlighted in green:<br>
![](https://github.com/badger707/m920q-dual-NVME/blob/main/pictures/IMG_5885_x.png)

## Soldering in progress

Now that we know location of all components, its time to solder them, one by one...

First we need to prep the pads -- clean all pads from factory solder using flux and desoldering braid...:<br>
![](https://github.com/badger707/m920q-dual-NVME/blob/main/pictures/IMG_5888_.PNG)

4 caps placed on NVME power rail (yeah, I know they're not perfectly soldered, dont care, works for me)<br>
![](https://github.com/badger707/m920q-dual-NVME/blob/main/pictures/IMG_5889_.PNG)

Keep cleaning the pads, and keep going. 

Now starting to solder components on the TOP side of the board, right side from SATA port:<br>
![](https://github.com/badger707/m920q-dual-NVME/blob/main/pictures/IMG_5890_.PNG)

Right side from SATA port is completed, all components soldered:
![](https://github.com/badger707/m920q-dual-NVME/blob/main/pictures/IMG_5894_.PNG)


Left side from SATA port is completed, all components are soldered. Yes I missed one cap and thats intentional -- I didnt wanted to take any risk and melt the SATA port, cap is just too close to it. So I skipped C377 and placed C379 to its place:<br>
![](https://github.com/badger707/m920q-dual-NVME/blob/main/pictures/IMG_5896_.PNG)

## SOLDERING COMPLETED
Board view from the TOP:<br>
![](https://github.com/badger707/m920q-dual-NVME/blob/main/pictures/completed_view.jpeg)
<br><br>
## CHECKING BIOS

Main view of my M920Q machine:<br>
![](https://github.com/badger707/m920q-dual-NVME/blob/main/pictures/bios_view_1.jpeg)

Main > System Summary > Here you go -- 2 NVME drives:<BR>
![](https://github.com/badger707/m920q-dual-NVME/blob/main/pictures/bios_view_2.jpeg)

## BOOTING UBUNTU AND CHECKING IF ALL GOOD - OH YES IT IS!
![](https://github.com/badger707/m920q-dual-NVME/blob/main/pictures/nvme_list_and_lshw_.png)
<br><br>
## TROUBLESHOOTING

If things didnt worked for you, here is what I'd check:
* Machine does not post --> you created short circuit somewhere while soldering components, find & fix.
* Machine does post but BIOS does not show "M.2 Drive 2" option --> move resistor R105 as per instructions.
* Machine does post, "M.2 Drive 2" option is available, no drive model shown/recognised --> bad solder join in one of components, or, NVME edge connector is not soldered properly. Check & re-flow suspicious joins.
<br><br><br>

# FINAL NOTES

As you can see, we can convert M920Q and add second NVME drive, this is exastly same as M920X.<br>
Budget/cost - under 20EUR for all SMD components and edge connector.<br>
This hardware mod is not difficult but requires proper tools and good experience with soldering.<br>
I hope this will be usefull.<br><br>

I do not provide professional services, however, feel free to reach out if you have any chalenges or questions related to this project.
<br><br>

### Useful links:
* [STH - Lenovo Thinkcentre/ThinkStation Tiny (Project TinyMiniMicro) Reference Thread](https://forums.servethehome.com/index.php?threads/lenovo-thinkcentre-thinkstation-tiny-project-tinyminimicro-reference-thread.34925/)
* [M.2 NVME edge connector, 6EUR, Mouser](https://www.mouser.ie/ProductDetail/Amphenol-FCI/MDT420M01501?qs=doiCPypUmgHNRCMog9PEkQ%3D%3D)
* [M.2 NVME drive latch/clip, 0.42EUR, Aliexpress, item 1005004160639253](https://www.aliexpress.com/item/1005004160639253.html)
* [M.2 Plastic Retention Clip Fastener for Lenovo, ebay.com, US based, 10USD](https://www.ebay.com/itm/224828071622)

