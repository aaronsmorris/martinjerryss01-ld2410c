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

Open the switch up by prying the body open at the top with a thin bladed screwdriver or tool.
Disconnect the connector that connects the front of the switch to the back of it.
Remove the 4 screws that hold the PCB on the front of the switch.
Remove the 4 pin header or cut it completely down on the LD2410C module.
Place the LD2410C in the bracket and glue the bracket to the switch paddle.
Solder wires from the VCC and GND on the LD2410C to the 5V VCC on the 3pin connector on the switch PCB
Solder a wire from the OUT pin on the LD2410C to the ESP8266 bottom row, 5th pin in (GPIO14)

![LD2410C](/img/ESPWiring.jpeg)

Secure wires using hot glue.
Put kapton or other insulating tape on back of LD2410C module.
Reassemble switch.
Flash your switch from Tasmota to ESPHome.

## ESPHome YAML File

Here's an example of how I set up my ESPHome YAML for this sensor. You will have to build a new ESPHome device and then gzip the firmware and upload it to the Tasmota page for the device to flash it to ESPHome.

![ESPHome YAML](/mjss01-ld410c.yaml)
