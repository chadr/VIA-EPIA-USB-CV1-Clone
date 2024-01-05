# VIA EPIA USB CV1 clone
This is an open source clone of VIA's EPIA USB 1.1 Daughterboard USB-CV1. USB-CV1 is required to use the proprietary internal USB 1.1 header on some VIA EPIA motherboards like the EPIA-800AG.

## Why do I need this?
You can't just make an adapter cable to connect the VIA EPIA proprietary internal USB 1.1 header to a standard USB header cable. The internal EPIA header is directly connected to the raw output of the chipset south bridge. Doing so will fry your chipset in short order! And the ports will not work due to lack of bus termination and port enable signals.

For USB to work without damaging the chipset, you must provide the following:
* over voltage protection / transient protection
* over current protection
* power filtering / stiffening
* ESD protection
* bus termination
* EMI filtering / low-pass filter
* port enable signal

This clone of the USB-CV1 provides all of the above features.

## Bill of Materials
**Item**|**Qty**|**MFG Part Num**|**Mouser Part Num**
:-----:|:-----:|:-----:|:-----:
5.5V 30A Varistor|1|V5.5MLA0603NH|576-V5.5MLA0603NH
6V 2.6A Resettable Fuse|1|MINISMDC260F-2|650-MINISMDC260F-2
Ferrite Bead|1|-|-
USB 1.1 Bus IC|2|USBDF01W5|511-USBDF01W5
Wurth 1000uF 10V Cap|1|860020275015|710-860020275015
560K 1/8w Resistor|2|-|-
2x4 2.0mm female pin header|1|-|-
2x5 2.54mm male pin header|1|-|-

## PCB Info
4 Layer
1.2mm thickness
32mm by 20mm
