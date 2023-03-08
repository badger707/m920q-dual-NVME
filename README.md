# m920q-dual-NVME

![Lenovo M920Q](https://github.com/badger707/m920q-dual-NVME/blob/main/pictures/20180508_lenovo_tiny.jpg)

Goal of this personal project is to add 2nd NVME drive to Lenovo M920Q Tiny by soldering missing SMD component to the board.

Models overview:

| Model | Supported CPU | Chipset | SODIMM RAM | PCIE slot | NIC | Drives| Board Model|
|-------|-----------------------|------------|-----------------------|-------------|----------------------|-----------------|----------------------|
| M920Q | Coffee Lake (8/9x00T) | Intel Q370 | 2 x 32GB 2666MHz DDR4 | PCIe 3.0 x8 | Intel l219-LM (vPro) | 1x M.2, 1x 2.5" | IQ3XOIL Q370 NM-B551 |
| M920X | Coffee Lake (8/9x00T) | Intel Q370 | 2 x 32GB 2666MHz DDR4 | PCIe 3.0 x8 | Intel l219-LM (vPro) | 2x M.2, 1x 2.5" | IQ3XOIL Q370 NM-B551 |

M920Q and M920X are using same board model.


## DISCLAIMER
USE AT YOUR OWN RISK. MICRO SOLDERING REQUIRED. I'M NOT RESPONSIBLE IF YOU WILL DAMAGE YOUR BOARD OR BURN DOWN YOUR HOUSE WITH THIS EXERCISE. IF YOU DONT KNOW WHAT YOU'RE DOING - DONT DO IT.

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
| Type | Name | Size | Value | Voltage | Count |
|-----------|--------|-------|--------|----------|---|
| Capacitor | C363 | 0402 | 0.01uF | 25V7-K | 1 |
| Capacitor | C364 | 0402 | 0.01uF | 25V7-K | 1 |
| Capacitor | C365 | 0402 | 0.1uF | 16V7-K | 1 |
| Capacitor | C366 | 0603 | 10uF | 6.3V6-M | 1 |
| Capacitor | C367 | 0402 | 0.22uF | 16V7-K | 1 |
| Capacitor | C368 | 0402 | 0.22uF | 16V7-K | 1 |
| Capacitor | C369 | 0402 | 0.22uF | 16V7-K | 1 |
| Capacitor | C370 | 0402 | 0.22uF | 16V7-K | 1 |
| Capacitor | C371 | 0402 | 0.22uF | 16V7-K | 1 |
| Capacitor | C372 | 0402 | 0.22uF | 16V7-K | 1 |
| Capacitor | C373 | 0402 | 0.22uF | 16V7-K | 1 |
| Capacitor | C374 | 0402 | 0.22uF | 16V7-K | 1 |
| Rezistor | R1302 | 0402 | 0 ohm | - | 1 |
| Rezistor | R1303 | 0402 | 0 ohm | - | 1 |
| Rezistor | R631 | 0402 | 0 ohm | - | 1 |
| Rezistor | R632 | 0402 | 0 ohm | - | 1 |
| Rezistor | R633 | 0402 | 33 ohm | - | 1 |
| Rezistor | R634 | 0402 | 0 ohm | - | 1 |
| Rezistor | R635 | 0402 | 0 ohm | - | 1 |
| Rezistor | R636 | 0402 | 0 ohm | - | 1 |
| Capacitor | C377 | 0402 | 0.01uF | 25V7-K | 1 |
| Capacitor | C378 | 0402 | 0.01uF | 25V7-K | 1 |
| Capacitor | C379 | 0402 | 0.1uF | 16V7-K | 1 |
| Capacitor | C380 | 0603 | 10uF | 6.3V6-M | 1 |
| Rezistor | R639 | 0402 | 0 ohm | - | 1 |
| Rezistor | RC27 | 0402 | 10 Kohm | - | 1 |
| Rezistor | RC24 | 0402 | 10 Kohm | - | 1 |
| M.2 NVME | - | - | - | - | 1 |

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
| M.2 NVME | - | - | - | 1 |

### Components location - TOP side of the board

9 components on the Left side of SATA port, highlighted in green:<br>
![](https://github.com/badger707/m920q-dual-NVME/blob/main/pictures/IMG_5877_x.png)

12 components on the Right side of SATA port, highlighted in green:<br>
![](https://github.com/badger707/m920q-dual-NVME/blob/main/pictures/IMG_5878_x.png)
