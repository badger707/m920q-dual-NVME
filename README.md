# m920q-dual-NVME

![Lenovo M920Q](https://github.com/badger707/m920q-dual-NVME/blob/main/pictures/20180508_lenovo_tiny.jpg)

Goal of this personal project is to add 2nd NVME drive to Lenovo M920Q Tiny by soldering missing SMD component to the board.

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

* ### Component location - BOTTOM side of the board

Only 4 capacitors at the side of NVME connector pads, highlighted in green:<br>
![](https://github.com/badger707/m920q-dual-NVME/blob/main/pictures/IMG_5885_x.png)

### Useful links:
* [M.2 NVME edge connector, 5EUR, Mouser](https://www.mouser.ie/ProductDetail/Amphenol-FCI/MDT420M01501?qs=doiCPypUmgHNRCMog9PEkQ%3D%3D)
* [M.2 NVME drive latch/clip, 0.42EUR, Aliexpress, item 1005004160639253](https://www.aliexpress.com/item/1005004160639253.html)
* [M.2 Plastic Retention Clip Fastener for Lenovo, ebay.com, US based, 10USD](https://www.ebay.com/itm/224828071622)
* [STH - Lenovo Thinkcentre/ThinkStation Tiny (Project TinyMiniMicro) Reference Thread](https://forums.servethehome.com/index.php?threads/lenovo-thinkcentre-thinkstation-tiny-project-tinyminimicro-reference-thread.34925/)
