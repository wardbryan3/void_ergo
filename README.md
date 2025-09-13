# VOID Ergo S
*A handwired split keyboard, running QMK firmware with vial support*

![VOID Ergo S](https://i.imgur.com/aQ571vc.jpg)

| ![](https://i.imgur.com/X6qhLW8.jpeg) | ![](https://i.imgur.com/vaoo9bM.jpeg) | ![](https://i.imgur.com/nWaW7JV.jpeg) |
|---------------------------------------|---------------------------------------|---------------------------------------|

###### More renders [here](https://imgur.com/a/ki1BZij)

The VOID Ergo S is a 3d printed, handwired, split keyboard with a layout similar to the Iris/Corne/Kyria, running QMK Firmware on Pro Micro controllers. Connection between the two halves of the keyboard is made with an aux cable via serial.

I suggest printing the case using a 0.4 mm nozzle, supports are not needed but recommended for the bottom cases as the ports will print with less imperfections.

The brass inserts can be fixed in the bottom case by heating them and applying pressure with a soldering iron set to about 200-220C.

*VOID Ergo S with V1 of the VOID Ergo under it*

![VOID Ergo Fat](https://i.imgur.com/liKmJqt.jpg)

# My changes (wardbryan)

The most important change I am making is swappinf the pro micros for an rp2040-zero. these are cheaper and have more memory, which should allow me to enable more features in qmk/vial. 

I am also only going to be using a single encoder on the left half. (Originally I was going with 0 encoders, but was conviced that I needed to try them at least)


The other change I will be doing is updating the bill of materials to amazon links. Prices will be added as well, however thats just more to track it. Prices were added september of 2025. 

|---------------------------------------|---------------------------------------|---------------------------------------|

# Bill of Materials

* 46 diodes (tme.eu [link](https://www.tme.eu/ro/en/details/1n4148-dio/tht-universal-diodes/diotec-semiconductor/1n4148/)/aliexpress [link](https://www.aliexpress.com/item/32729204179.html))
* 44/46 cherry mx style switches
* 24 AWG (0.2 mm2) wire
* 2 x Pro Micro (aliexpress [link](https://www.aliexpress.com/item/32902569443.html))
* 2 x EC11 Rotary Encoder (optional/aliexpress [link](https://www.aliexpress.com/item/32872039030.html) mounted to the plate using [this adapter](https://www.thingiverse.com/thing:3770166))
* 10 x M2x12 allen head screws (aliexpress [link](https://www.aliexpress.com/item/32966941844.html), 14mm overall length, 4mm diameter head)
* 10 x M2 brass inserts (aliexpress [link](https://www.aliexpress.com/item/4000585933306.html), 3.5mm outer diameter)
* 2 x PJ320A 3.5mm female audio connectors (aliexpress [link](https://www.aliexpress.com/item/32368285821.html))
* 1 x 6x6x6 push button (optional (used to reset master)/aliexpress [link](https://www.aliexpress.com/item/32960657626.html))
* hot glue for securing the Pro Micros to the bottom case (optional, but recommended) the audio connectors and the reset push button.

# Pin assignment

    ROW0    ROW1    ROW2    ROW3
    B1      B3      B2      B6
    
    
    COL0    COL1    COL2    COL3    COL4    COL5
    D4      C6      D7      E6      B4      B5


    Encoder Pad A Left      Encoder Pad B Left
    F5                      F6

    Encoder Pad A Right     Encoder Pad B Right
    F6                      F5

    Serial Pin
    D1

*Matrix layout*

![VOID Ergo S matrix layout](https://user-images.githubusercontent.com/2669084/198817120-c0a429e6-7d4c-46c4-8828-728ca2bc882f.png)

# QMK Vial Fork

A QMK Vial fork can be found [here](https://github.com/victorlucachi/vial-qmk/tree/dev_void/keyboards/handwired/void_ergo).

Most features are disabled in order for the firmware to fit on the atmega32u4 present on the Pro Micro controllers, but if you want to tinker around with different features or if you're using a different MCU you can enable/disable them to suit your own needs by editing the rules.mk file in the vial keymap folder.

The web version of Vial is available at [vial.rocks](https://vial.rocks/); it runs in supported browsers (Chrome, Edge and Opera) without requiring an installation.

![VOID Ergo S Vial](https://user-images.githubusercontent.com/2669084/198691150-df30a285-044d-4926-9cd1-cb79812d75bd.png)

# QMK Fork

A fork containing the QMK config files can be found [here](https://github.com/victorlucachi/qmk_firmware/tree/dev_void/keyboards/handwired/void_ergo). Edit them to suit your own needs and build the firmware following the QMK docs.

If you plan on using the VIA configurator dont forget to download the json definitions file linked in this repository.

[![License: CC BY-NC-SA 4.0](https://img.shields.io/badge/License-CC%20BY--NC--SA%204.0-blue)](https://creativecommons.org/licenses/by-nc-sa/4.0/)

This work is licensed under a [Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License](https://creativecommons.org/licenses/by-nc-sa/4.0/).
