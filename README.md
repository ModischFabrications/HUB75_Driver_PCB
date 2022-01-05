[![KiCad Exports](https://github.com/ModischFabrications/HUB75_Driver_PCB/actions/workflows/exports.yml/badge.svg)](https://github.com/ModischFabrications/HUB75_Driver_PCB/actions/workflows/exports.yml)

# HUB75_Driver_PCB

This is the PCB for my custom HUB75 RGB Panel Display.

I bought [this 64x32 panel](https://www.aliexpress.com/item/32810362851.html) and [this ESP32 (ESP32-CH9102X)](https://www.aliexpress.com/item/32959541446.html) closely researching specifications, costing ~30€ in sum. Others will probably work too, no guarantees either way. 

Open like regular in KiCad. Look into the docs zip under [Actions/KiCad Exports](https://github.com/ModischFabrications/HUB75_Driver_PCB/actions/workflows/exports.yml) to see renderings. 

This schematic can be soldered manually onto a perfboard, but feel free to order a PCB instead. 

Use a **5V** power supply with 10W or more! 
Never connect USB Power and Matrix power together, make sure to remove the jumper when using the USB connector. 
Powering the Matrix via USB, without the terminals, is possible, but definitely not recommended, the devboard can't handle it. 

Max current is ~2A, typical ~0.7A, idle (without output) is still ~0.06A, split between devboard and RGB controllers. 
Being wireless it nice, but usually, especially in this case, not worth the effort for protoypes. 
While technically possible, the power draw will reduce battery runtime to less than a day.  

Feel free to add external solutions though, should be easy to cram a 18650 USP board into the case. 

## Decisions

Size and exact positioning is determined by the backing struts of my panel. 

### Electrical

Short-circuit-resistance of the power leads is archieved using a polyfuse. Resistance of the inputs is build-in, as they are high impedance, but the outputs are at risk. 

Reverse polarity protection is given through D1, which will trigger the fuse. Sure, it's not perfect, but it's simple. 

Introducing series resistances into every single connection could have made it safer, but I can't be arsed at the moment. Active-Low or High doesn't really matter either, a cross between adjacent leads would result in one overloading regardless. Feel free to insert ~300 ohm everywhere if you want to be safe. 

## References
To be honest, they are virtually identical solutions with just minor differences. Choose according to your needs. 

- https://github.com/rorosaurus/esp32-hub75-driver
- https://github.com/witnessmenow/ESP32-i2s-Matrix-Shield

