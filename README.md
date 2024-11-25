# POE ESP32S3

POE enabled ESP32S3 dev board with onboard programming via USB-C,
and an OTG USB-A port. The repo contains the Kicad schematic and PCB
design.

It is ok to apply power via USB-C and POE simultaneously. The board
gives preference to the POE, if it is present.

While this can be used as a general purpose POE dev board, I personally
use it to network enable a Aeotec Zwave stick using the ser2net protocol.

![top_pcb_image](images/top.png?raw=true "top pcb image")

## "Inspiration"

I copied the POE schematic and layout directly from [OLIMEX](https://github.com/OLIMEX/ESP32-POE-ISO/blob/master/HARDWARE/ESP32-PoE-ISO-Rev.K/ESP32-PoE-ISO_Rev_K.pdf).

The Wiznet 5500 ethernet to SPI circuit was copied directly from the
[WS5500 reference circuit](https://docs.wiznet.io/img/products/w5500/W5500_ds_v110e.pdf)

Everything else is from the [ES32-S3 reference circuit](https://dl.espressif.com/dl/schematics/SCH_ESP32-S3-DEVKITM-1_V1_20210310A.pdf).

## General Caveats

This was my very first PCB and there is a lot I don't like about both
the schematic and the PCB layout. I'm only making this repo public
because someone on Reddit asked for the Kicad files.

More importantly, the Olimex POE design is very noisy. It's fine for
my use, but I heard from someone else that used an Olimex like design
that it was too noisy to use directly with an ADC.

If I were to do this again, I would base the POE design around Silvertel
POE modules, potentially using them directly. I measured one and it's
power was far less noisy. The entire unit is cheaper than trying to
source individual parts, and they come in form factors that should be easy
to integrate.

## Production and Update Caveats

I don't think part numbers were populated, and this may nor may not
seamlessly export with the JLCPCB exporter. The library management
is likely bad, and there is a possibility that I edited symbols or
footprints directly, without doing so in the library. There might
be non-relative paths in the library configs as well. I hadn't yet
established best practices for any of that back when I did this. So,
updating symbols and footprints might mess up the schematic and PCB.
