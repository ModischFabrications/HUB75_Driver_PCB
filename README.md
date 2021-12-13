# HUB75_Driver_PCB

This is the PCB for my custom HUB75 RGB Panel Display.

Open like regular in KiCad. Look into the docs zip under [Actions/KiCad Exports](https://github.com/ModischFabrications/HUB75_Driver_PCB/actions/workflows/exports.yml) to see renderings. 

This schematic can be soldered manually onto a perfboard, but feel free to order a PCB instead. 

## Decisions

Size and exact positioning is determined by the backing struts of my panel. 

### Electrical

Short-circuit-resistance of the power leads is archieved using a polyfuse. Resistance of the inputs is build-in, as they are high impedance, but the outputs are at risk. 

Reverse polarity protection is given through D1, which will trigger the fuse. Sure, it's not perfect, but it's simple. 

Introducing series resistances into every single connection could have made it safer, but I can't be arsed at the moment. Active-Low or High doesn't really matter either, a cross between adjacent leads would result in one overloading regardless. Feel free to insert ~300 ohm everywhere if you want to be safe. 
