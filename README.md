Simple Hardware Teardown of the Telstra Smart Modem 4 

Model No. Telstra Smart Modem 4 5G
Model Name: Mongoose-5GFW

Input Voltage: 
12V / 3A

It's a white labelled modem/router rebranded by Telstra

Ports: (rear)
Power Input: DC Barrel Jack 2.1mm
DSL: 1X RJ11
USB 2.0
Reset (pin hole)
WAN: 1X RJ45
LAN: 4X RJ45
VOIP: 1X RJ11

Connectors: (rear)
2X SMA female bulkhead mounts 
Not labelled up but these are for external LTE antennas.
Use an external SMA Male antenna or SMA Male -> Fakra adapter cable for antennas. 

Buttons: (rear)
Lights button - hold for 3s to turn on & off front LED light
WIFI - press to enable/disable wifi
WPS - press to enable WPS 

Lights: (rear)
WAN/DSL Indicator light
Mobile signal (3 bars small to large - these have been all lit, even though I'm only getting 10Mbps....)
[ in comparison an iPhone 16 alongside the router also on the Telstra network shows 3 of 5 bars]
Phone Indicator light
WIFI Indicator

Lights: (front)
Single RGBW LED indicator
- White - blinking 
- Blue - Connected to 4G/5G
- Green - Connected to NBN
- Red - No Connection


Dissassembly:
2X  TX10 (torx) screws located under the rubberised feet.
Split shell design, slide the front half up to seperate the modem-router

General Assembly:
Plenty of heatstinks, thermal pads & shielding on the board which is good to see.

PCB Notation:
SAGEMCOM FAST 5988TA V2.1


Notable Internals:

Power Supply Input Circuitry:
- Main Power FET
- Si 4435D
- https://www.infineon.com/assets/row/public/documents/24/49/si4435dypbf.pdf?fileId=5546d462533600a4015356847c882983

Voice Signal:
- Si32184 A-FM
- https://www.skyworksinc.com/Products/Voice/Si3218x-Single-Channel-ProSLIC/Si32184

2.4/5Ghz Internal Antennas:
- 4X U.FL antennas to internal Inverted F type antennas mounted inside the case
- Antennas are offset from the PCB at a angle & mounted on plastic spacers/ brackets
- Wire Colours: Green, Black, Blue, Red

LTE Antennas
 - Internal: 
    - Part of the PCB 
    - Wire Colours: Yellow & Orange

 - External: 
    - U.FL connectors which are routed to U.FL > SMA pig tails mounted in the case
    - Under the settings section you can select "Internal, External, Auto" for mobile antenna selection. 
    - Wire Colours: Brown & White


Ethernet Switch:
Realtek RTL8367S
- https://www.realtek.com/Product/Index?id=3699
- https://www.lcsc.com/datasheet/C2760849.pdf

Ethernet Magnetics:
WAN: G24107MN-R
- https://www.alldatasheet.com/datasheet-pdf/view/1776941/FPE/G24107MN-R.html

LAN: GST5009BM LF
- https://mm.digikey.com/Volume0/opasdata/d220001/medias/docus/6166/GST5009xx_NA0069xx.pdf

CPU's
2X Qualcomm QFW7114 
- Qualcomm link.... 
- Front end modules unknown, 4 per CPU

LTE Modem:
- Quectel 
- RG650V-TL
- https://www.quectel.com/product/5g-rg650v-series/
- https://www.quectel.com/content/uploads/2024/03/Quectel_RG650ERG650V_Series_5G_Specification_V1.0.pdf?wpId=114144

eSIM:
unknown part number - but assume it matches the same pinout as the standard MFF2 footprint, DFN8 5X6mm

Power Supply (I assume this is setup as a HW Power watchdog?)
MP111 'Dying gasp storange & release control IC'
- https://www.monolithicpower.com/en/documentview/productdocument/index/version/2/document_type/Datasheet/lang/EN/sku/MP111/document_id/1088/?utm_source=chatgpt.com

Level Shifters:
- TXS0104ERGYR
- https://www.ti.com/lit/ds/symlink/txs0104e.pdf?ts=1756473294173

