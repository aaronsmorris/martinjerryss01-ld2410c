# Smart Switch w/Presence Detection - ESPHome Version

![PoolPhoto](/img/mjss01.jpeg)

## Overview
This is how to outfit an LD2410C presence detector into a ESP based smart switch

## Requirements

* Sensor installed in a manner that it cannot be seen
* Integrates with Home Assistant via ESPHome
* Sensor connected to power and ESP inside of switch.

## Notes

Code is compatible with ESP8266 

### Bill of materials (BOM)

* [Martin Jerry SS01 Switch](https://www.amazon.com/dp/B0B7WC3LF2?ref=ppx_yo2ov_dt_b_product_details&th=1)
* [LCD2410C mmwave radar](hhttps://www.amazon.com/EC-Buying-HLK-LD2410-Presence-Millimeter/dp/B0BXDLHHH2)
* [30ga silicone wire](https://www.amazon.com/TUOFENG-30awg-Stranded-Wire-Kit/dp/B07G2SWB19)
* [3D printed bracket](/MartinJerrySS01-LD2410C-Mount.stl)

### Schematic 
Below is the schematic
![Schematic](/img/schematic.png)

### Printable Parts 

![LD2410C](/img/LD2410Placement.jpeg)

All parts print without support in the default orientation.

* [Bracket](/MartinJerrySS01-LD2410C-Mount.stl) - White PETG or something UV and heat resistant. 4 walls and top/bottom layers. 10-30% infill should be enough.

### Build & Assembly


## ESPHome YAML File

Here's an example of how I set up my ESPHome YAML for this sensor. It's a Dallas 18B20 temp sensor, and I use deep sleep to conserve power. Every 15m I report the temp and battery voltage. I use a deep sleep toggle entity on Home Assistant to tell the device when not to use deep sleep so that I can do OTA updates.

![ESPHome YAML](/mjss01-ld410c.yaml)
