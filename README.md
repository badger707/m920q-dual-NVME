# m920q-dual-NVME

![Lenovo M920Q](https://github.com/badger707/m920q-dual-NVME/blob/main/pictures/20180508_lenovo_tiny.jpg)

Goal of this personal project is to add 2nd M.2 NVME drive to Lenovo M920Q (M.2 SATA for M720Q) Tiny by soldering missing SMD components to the board.

Models overview:

| Model | Supported CPU | Chipset | SODIMM RAM | PCIE slot | NIC | Drives| Board Model|
|-------|-----------------------|------------|-----------------------|-------------|----------------------|-----------------|----------------------|
| M920Q | Coffee Lake (8/9x00T) | Intel Q370 | 2 x 32GB 2666MHz DDR4 | PCIe 3.0 x8 | Intel l219-LM (vPro) | 1x M.2, 1x 2.5" | IQ3XOIL Q370 NM-B551 |
| M920X | Coffee Lake (8/9x00T) | Intel Q370 | 2 x 32GB 2666MHz DDR4 | PCIe 3.0 x8 | Intel l219-LM (vPro) | 2x M.2, 1x 2.5" | IQ3XOIL Q370 NM-B551 |
M720Q | Coffee Lake (8/9x00T) | Intel B360 | 2 x 32GB 2666MHz DDR4 | PCIe 3.0 x8 | Intel l219-V | 1x M.2, 1x 2.5" | IQ3XOIL Q370 NM-B551 |

M920Q, M920X and M720Q are using same board model.
<br><br>

## TLDR
M920q -- one M.2 NVME drive in original (white) slot, and one M.2 NVME drive in soldered slot. <br>
M720q -- one M.2 NVME drive in original (white) slot, and one M.2 SATA drive in soldered slot ![confirmed](https://github.com/badger707/m920q-dual-NVME/issues/4#issuecomment-1706374243).
<br><br>

## DISCLAIMER
USE AT YOUR OWN RISK. MICRO SOLDERING REQUIRED. I'M NOT RESPONSIBLE IF YOU WILL DAMAGE YOUR BOARD OR BURN DOWN YOUR HOUSE WITH THIS EXERCISE. IF YOU DONT KNOW WHAT YOU'RE DOING - DON'T DO IT.
<br><br>
## FUN PART

Items on hand:
* M920Q Tiny
* tons of pictures of M920X board in high resolution, found on internet.
* M920X Tiny schematics (circut diagrams)
* M720Q pictures provided/shared by friendly user on Reddit

In firs steps I started to visually compare M920X board pictures to my M920Q, just to see how many missing components I will find.
Most of (missing) components are located on top side of the board around SATA and Wi-Fi connectors area.
Few components are on the bottom side of the board where NVME slot is located.

Looking at the schematics for the 2nd NVME drive circuit - 16 capacitors and 11 resistors needs to be soldered on board, together with M.2 NVME connector.
By comparing my visual findings with schematics and "board view", I was able to locate & identify all of them.

* ### Components list for M920Q and M720Q
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
| Resistor | R1302 | 0402 | 0 ohm | - | top |
| Resistor | R1303 | 0402 | 0 ohm | - | top |
| Resistor | R631 | 0402 | 0 ohm | - | top |
| Resistor | R632 | 0402 | 0 ohm | - | top |
| Resistor | R633 | 0402 | 33 ohm | - | top |
| Resistor | R634 | 0402 | 0 ohm | - | top |
| Resistor | R635 | 0402 | 0 ohm | - | top |
| Resistor | R637 | 0402 | 0 ohm | - | top |
| Capacitor | C377 | 0402 | 0.01uF | 25V7-K | top |
| Capacitor | C378 | 0402 | 0.01uF | 25V7-K | top |
| Capacitor | C379 | 0402 | 0.1uF | 16V7-K | top |
| Capacitor | C380 | 0603 | 10uF | 6.3V6-M | top |
| Resistor | R639 | 0402 | 0 ohm | - | top |
| Resistor | RC24 | 0402 | 10 Kohm | - | top |
| M.2 NVME connector | - | 3.2mm/4.2mm | - | - | bottom |
| M.2 NVME plastic retention clip | - | - | - | - | bottom |

\
Note on M.2 NVME edge connector:
> I have used 4.2mm height connector (Gen5, expensive), however 3.2mm from Gen3/4 would be recommended (cheaper), see link bellow.

<br>

* ### Components list summary:
| Type | Size | Value | Voltage | Count | Mouser links |
|-----------|-------|--------|----------|---|------|
| Capacitor | 0402 | 0.01uF | 25V7-K | 4 | ![581-04023D103KAT2A](https://www.mouser.ie/ProductDetail/581-04023D103KAT2A)|
| Capacitor | 0402 | 0.1uF | 16V7-K | 2 | ![581-0402YD104K](https://www.mouser.ie/ProductDetail/581-0402YD104K)|
| Capacitor | 0402 | 0.22uF | 25V7-K | 8 | ![581-0402YC224KAT2A](https://www.mouser.ie/ProductDetail/581-0402YC224KAT2A)|
| Capacitor | 0603 | 10uF | 6.3V6-M | 2 | ![810-C1608X5R0J106K ](https://www.mouser.ie/ProductDetail/810-C1608X5R0J106K)|
| Resistor | 0402 | 0 ohm | - | 8 | ![603-RC0402FR-070RL](https://www.mouser.ie/ProductDetail/603-RC0402FR-070RL)|
| Resistor | 0402 | 10 Kohm | - | 2 | ![71-RCC040210K0FKED](https://www.mouser.ie/ProductDetail/71-RCC040210K0FKED)|
| Resistor | 0402 | 33 ohm | - | 1 | ![71-CRCW040233R0FKEDC](https://www.mouser.ie/ProductDetail/71-CRCW040233R0FKEDC)|
| M.2 NVME connector | 3.2mm/4.2mm | - | - | 1 | see useful link section |
| M.2 NVME plastic retention clip | - | - | - | 1 | see useful links section |

<br>
<br>

* ### Components location for M920Q and M720Q - TOP side of the board<br>

9 components on the Left side of SATA port, highlighted in green:<br>
![](https://github.com/badger707/m920q-dual-NVME/blob/main/pictures/IMG_5877_x.png)
<br><br>
12 components on the Right side of SATA port, highlighted in green:<br>
![](https://github.com/badger707/m920q-dual-NVME/blob/main/pictures/IMG_5878_x.png)
<br><br>
<b>For M920Q</b> -- move resistor from R150 to R162. This will switch PCH to work in M920X mode:
![](https://github.com/badger707/m920q-dual-NVME/blob/main/pictures/IMG_5883_x.png)
<br><br>
<b>For M720Q</b> -- move resistor from R151 to R157. This will switch PCH to work in M920X mode:
![](https://github.com/badger707/m920q-dual-NVME/blob/main/pictures/m720q_pch_jump.jpeg)
<br>
Note on above M720Q picture components location:
> According to this ![post](https://github.com/badger707/m920q-dual-NVME/issues/4#issuecomment-1706272665) soldered M.2 slot will work with M.2 SATA drive only.

<br><br>
* ### Component location - BOTTOM side of the board

Only 4 capacitors at the side of NVME connector pads, highlighted in green:<br>
![](https://github.com/badger707/m920q-dual-NVME/blob/main/pictures/IMG_5885_x.png)
<br>
> Ignore RC27 highlighting in above picture.<br>

<br>
## Soldering in progress<br>

> <b>For M920Q</b> -- solder all components and move R150 resistor.<br>
<b>For M720Q</b> -- solder all components and move R151 resistor.
<br>
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
Board view from the TOP, with marker of R150 location:<br>
![](https://github.com/badger707/m920q-dual-NVME/blob/main/pictures/completed_view_.jpeg)
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
* Machine does post but BIOS does not show "M.2 Drive 2" option --> move resistor R150 (or R151 for M720q) as per instructions.
* Machine does post, "M.2 Drive 2" option is available, no drive model shown/recognised --> bad solder join in one of components, or, NVME edge connector is not soldered properly. Check & re-flow suspicious joins.
<br><br><br>

# FINAL NOTES

As you can see, we can convert m920Q and add second M.2 NVME drive, this is exactly same as m920X.<br>
For m720Q -- according to this ![post](https://github.com/badger707/m920q-dual-NVME/issues/4#issuecomment-1706272665) soldered M.2 slot will work with M.2 SATA drive only.<br>
Budget/cost - under 20EUR for all SMD components and edge connector.<br>
This hardware mod is not difficult but requires proper tools and good experience with soldering.<br>
I hope this will be usefull.<br><br>

I do not provide professional services, however, feel free to reach out if you have any chalenges or questions related to this project.
<br><br>

### Useful links:
* [STH - Lenovo Thinkcentre/ThinkStation Tiny (Project TinyMiniMicro) Reference Thread](https://forums.servethehome.com/index.php?threads/lenovo-thinkcentre-thinkstation-tiny-project-tinyminimicro-reference-thread.34925/)
* [M.2 NVME edge connector - I have ordered/used this one, M Key, H=4.2mm, 6EUR, Mouser](https://www.mouser.ie/ProductDetail/Amphenol-FCI/MDT420M01501?qs=doiCPypUmgHNRCMog9PEkQ%3D%3D)
* [M.2 NVME edge connector -- better/cheaper option - M Key, H=3.2mm, 1.9EUR, Mouser](https://www.mouser.ie/ProductDetail/Amphenol-FCI/MDT320M03001?qs=L0rBtNYaw0mrZfzBsyqFRg%3D%3D)
* [M.2 Plastic Retention Clip Fastener for Lenovo, ebay.com, US based, 10USD](https://www.ebay.com/itm/224828071622)
* [Lot of 5pc Lenovo Thinkcentre M.2 SSD Kit Tray Anchor Tool PN. 4XF0P01011, ebay.com, 20USD](https://www.ebay.com/itm/403581452094) Note:  1 kit includes 2 red retention clips, so with lot of 5 you'd get 10 clips in total, thats ~2USD per one clip.
