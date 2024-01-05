# VIA EPIA USB CV1 clone
This is an open source clone of VIA's EPIA USB 1.1 Daughterboard USB-CV1. USB-CV1 is required to use the proprietary internal USB 1.1 header on some VIA EPIA motherboards like the EPIA-800AG.

## Why do I need this?
You can't just make an adapter cable to connect the VIA EPIA proprietary internal USB 1.1 header to a standard USB header cable. The internal EPIA header is directly connected to the raw output of the chipset south bridge. Doing so will fry your chipset in short order.

For USB to work without damaging the chipset, you must provide the following:
* over voltage protection / transient protection
* over current protection
* ESD protection
* bus termination
* EMI filtering / low-pass filter

BOM
MFG / Mouser
5.5V 30A Varistor - V5.5MLA0603NH / 576-V5.5MLA0603NH
USB 1.1 Bus IC - USBDF01W5 / 511-USBDF01W5
Wurth 1000uF 10V - 860020275015 / 710-860020275015
