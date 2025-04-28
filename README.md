# Hillside ZMK firmware

This firmware adds to Hillside 46 standalone radio trackball part.

![hillside](https://imgur.com/emWDXiT.png)
[![Build](https://github.com/mmccoyd/zmk-config/actions/workflows/build.yml/badge.svg)](https://github.com/mmccoyd/zmk-config/actions/workflows/build.yml)

This is the [ZMK](https://zmk.dev/docs) firmware
 for the [Hillside](https://github.com/mmccoyd/hillside) family of split ergonomic keyboards.

Contains only one board
 - Hillside 46 with 3x6+5 keys + 3button trackball

trackball connections mapping for nice! nano v2

 * connections to breakout board https://github.com/siderakb/pmw3610-pcb
 * 115 - motion
 * 002 - nCS (sel)
 * 029 - sclk 
 * 031 - sdio (MOSI/MISO)
 * vcc - vcc
 * gnd - gnd
 *
 * Buttons:
 * 008 to gnd - LMB
 * 017 to gnd - MMB
 * 020 to gnd - RMB


To build the firmware:

- Fork this repo on GitHub
- Clone your fork locally
- Trigger a build:
  - Make a trivial change to ./build.yaml (or any non *.md file)
  - Push that change
- Look in the [Actions](https://github.com/mmccoyd/zmk-config/actions) tab
     for the build triggered by that change. 
- Wait for the build to finish
- Click on the build link next to the green checkbox
- Download the artifact file with the firmware
- See [Installing The Firmware](https://zmk.dev/docs/user-setup#installing-the-firmware)
  for more details from there.

*Once* your board works with the default firmware,
  you can modify the keymap.
Your copies of the default Hillside keymaps are in:

- [./config/hillside52.keymap](./config/hillside52.keymap)
- [./config/hillside48.keymap](./config/hillside48.keymap)
- [./config/hillside46.keymap](./config/hillside46.keymap)

Modify those as needed. Pushing the change will trigger a build as above.

If you want to enable features,
  modify the appropriate ./config/hillside*.conf file.

To add RGB support, uncomment the lines in the ./config/hillside*.conf file
  and add the ```&rgb_ug RGB_TOG``` and other keycodes to the keymap adjust layer.
While RGB is disabled, any RGB control keys
  behave as transparent keys and activate keys on lower layers,
  which can be confusing.

The Hillside shield definition files should *not* need to be modified and are in ./config/boards/shields.

More information about each keymap is in their readme files.
