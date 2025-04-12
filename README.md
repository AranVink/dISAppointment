# dISAppointment

## Introduction

This project is about adding ISA slots to modern motherboards, by using the TPM header which have LPC pins.

[Video of it in action](https://www.youtube.com/watch/IXr-VEpQ1lg)

[Link to VOGONS thread](https://www.vogons.org/viewtopic.php?t=93291)


## Hardware

Everything related to hardware (Kicad/gerber files) can be found under [Hardware](./hardware/).

## Required software
Before using the sound card with the adapter, it needs to be initialized using SAPPHISA.EXE, which can be found under [software](./software/).

## Supported motherboards
You need a TPM header, with the LPC pins exposed. Most notable is the LDRQ pin, which is required to get IRQ working.

For now only Intel motherboard with a pre-PCH100 chipset are known to expose these pins.
The possibly latest/fastest are X99 motherboards, newer ones will probably never expose the correct pins since Intel dropped support after.

### Motherboards confirmed working:
| Brand    | Type           | LDRQ location     | Free IRQ status | Test status |
| ---      | ---            | ---               | ---       | ---         |
| Foxconn  | H61MXV         | TPM Header        | OK | [Confirmed by rasteri](https://www.vogons.org/viewtopic.php?p=1149862#p1149862) |
| Gigabyte | GA-Z77X-D3H    | Not on TPM header | OK | [Confirmed by rasteri](https://www.vogons.org/viewtopic.php?p=1149862#p1149862)
| DFI      | HD100          | Via backside      | OK | [Confirmed by rasteri](https://www.youtube.com/watch?v=7LIPTQjQAPE&ab_channel=TheRasteri)
| Asrock   | Z87M-Pro4      | ? | OK | [Confirmed by vsharun](https://www.vogons.org/viewtopic.php?p=1343053#p1343053)
| Asrock   | B85M Pro4      | ? | OK | [Confirmed by vsharun](https://www.vogons.org/viewtopic.php?p=1343220#p1343220)
| Gigabyte  | B85M D3H      | ? | OK | [Confirmed by vsharun](https://www.vogons.org/viewtopic.php?p=1343220#p1343220)

### Tested without success:
| Brand    | Type           | LDRQ location     | Free IRQ status | Test status |
| ---      | ---            | ---               | ---       | ---         |
| Gigabyte | GA-P67A-D3-B3  | Not on TPM header | ? | Tested by RayeR

### Could work
The following boards have a DLRQ pin on the TPM header:
| Brand    | Type        | LDRQ location     | Test status |
| ---      | ---         | ---               | ---         |
| SuperMicro | X9DRL-3F  | TPM header        | Untested
| SuperMicro | X10SKK-F  | TPM header        | Untested
| SuperMicro | X10SAE    | TPM header        | Untested
| Asrock     | Z87M Pro4 | Not on TPM header | Untested

## Unsupported motherboards
The following board have a TPM header, but have DLRQ pins missing. Potentially these could be modded to support it, but this will require soldering a jumper wire somewhere on the board:
* MSI P55-GD85
* MSI B75MA-E33
* ASRock J3455B-ITX (does have blank LPC pins on MB with TPM header next to it)
* Asus P8B-WS
* MSI X58 Pro
* MSI H87-G43
* Gigabyte Z77M-D3H
* Gigabyte Z68A-GD65 (G3)

### TPM header but no DMA support
* Asus Prime Z270-A
* ASUS Z170-A
* Gigabyte GA-B150-HD3P

### Missing TPM header:
* ASRock Z77 Extreme6
* ASRock H61M-S
* Asus P5Q3 Deluxe/WiFi-AP
* Asus P5KPL-AM EPU
* Asus P5KPL-VM
* Biostar B75MU3B
* Gigabyte GA-X58A-UD7`
