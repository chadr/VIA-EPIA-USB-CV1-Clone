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
USB 1.1 Bus IC|2|USBDF01W5|511-USBDF01W5
Wurth 1000uF 10V|1|860020275015|710-860020275015
Fuse|1|BK1/GMC-100-R|504-BK1-GMC-100-R
Fuse Holder|1|0PTF0078P|576-0PTF0078P
Fuse Clip|1|00BS0232P|576-00BS0232P

## PCB Info
4 Layer
1.2mm thickness
32mm by 20mm
