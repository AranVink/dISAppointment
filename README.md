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
* Foxconn H61MXV (confirmed by rasteri)
* Gigabyte GA-Z77X-D3H (confirmed by rasteri, requires modding by adding jumperwire)
* Gigabyte GA-P67A-D3-B3
* Z68A-D3H-B3
* DFI HD100 (confirmed by rasteri, requires modding by adding a jumperwire)
* Asrock Z87M-Pro4 (confirmed by vhsarun, requires modding by adding a jumperwire)
* Gigabyte B85M D3H (confirmed by vsharun, requires modding by adding a jumperwire)
* Asrock B85M Pro4 (confirmed by vsharun, requires modding by adding a jumperwire)

### Could work
The following boards have a DLRQ pin:
* SuperMicro X9DRL-3F
* SuperMicro X10SLL-F

## Unsupported motherboards
The following board have a TPM header, but have DLRQ pins missing. Potentially these could be modded to support it, but this will require soldering a jumper wire somewhere on the board:
* MSI P55-GD85
* MSI B75MA-E33
* ASRock J3455B-ITX (does have blank LPC pins on MB with TPM header next to it)
* Asus P8B-WS
* MSI X58 Pro
* Gigabyte GA-B150-HD3P
* MSI H87-G43
* ASUS Z170-A
* Gigabyte Z77M-D3H
* Gigabyte Z68A-GD65 (G3)
* Asus Prime Z270-A

### Missing TPM header:
* ASRock Z77 Extreme6
* ASRock H61M-S
* Biostar B75MU3B
* Asus P5Q3 Deluxe/WiFi-AP
* Gigabyte GA-X58A-UD7`
* Asus P5KPL-AM EPU
* Asus P5KPL-VM
