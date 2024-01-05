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
ST USB 1.1 Bus IC|2|USBDF01W5|511-USBDF01W5
Wurth 1000uF 10V Cap|1|860020275015|710-860020275015
560K 1/8w Resistor|2|-|-
2x4 2.0mm female pin header|1|-|-
2x5 2.54mm male pin header|1|-|-

### Description and Function of Components
**5.5V 30A Varistor:** Protects +5V rail of motherboard from over voltage and transients. According to industry data, transients of up to +24V can be seen when hot plugging USB devices.  
**6V 2.6A Resettable Fuse:** Provides combined over current protection for both ports. USB 1.1 spec limits each port to 500mA for a combined rating of 1A for both ports. However, you must provide a 2.5x factor to allow for inrush current when hot plugging devices.  
**Ferrite Bead:** Filters high frequency digital noise (MHz range) from +5V rail. Any through hole ferrite bead that can handle > 2.5A will work fine here.  
**ST USB 1.1 Bus IC:** Provides ESD protection, bus termination, and EMI filtering (low pass filter) for USB 1.1 ports. Each chip handles one port, so two are required. Use of this reduces the component count by 20 compared to VIA's discrete design.  
**Wurth 1000uF 10V Cap:** Provides stiffening for the +5V rail when hot plugging devices cause an inrush. This is bulk capacitance only. It does not filter. There is no benefit to using a more expensive low ESR cap in this application. Any cheap electrolytic with a voltage rating > 10V will work fine.  
**560K 1/8w Resistor:** Pullup resistors for the port enable pins on the motherboard chipset. The value here is not that critical. I only used 560K because that's what VIA used on their original design. But I'd bet that anything from 100K to 560K would work just fine. Can be 1%, 5%, metal film, carbon, whatever.  

## PCB Info
4 Layer  
1.2mm thickness  
32mm by 20mm  
HASL is fine. Paying extra for ENIG will not improve anything in this application.  
