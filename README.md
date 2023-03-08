# m920q-dual-NVME

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







