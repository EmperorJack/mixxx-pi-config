# mixxx-pi-config

This project documents the steps I took and configuration files I used to create a standalone Mixxx DJ setup using a Raspberry Pi. It is inspired by the standalone DDJ400 project completed by TimewasterNL, and the instructions provided by Fayaaz. The supplied configuration files customise the menu bar (i3bar) shown at the bottom of the screen, providing buttons to open Mixxx and turn off the system without needing a keyboard.

[images to go here]

## Hardware components

- Raspberry Pi 4 Model B (8GB RAM)
- Raspberry Pi 7" Touch Display
- SmartiPi Touch 2 case
- USB DJ controller with in-built sound card (e.g: DDJ400, XONE:K2)
- Micro SD card (32GB)
- USB stick with music
- USB-C power supply (or a USB-C power bank)

## Pi Image preparation

- Download mixxx-pi-gen image to SD card (MixxxPiBeta64v1 - mixxx-pi-v0.5.0.zip)
- Insert SD card into the pi

## Assembling the hardware components

- See https://smarticase.com/pages/smartipi-touch-2-setup-1

## Connecting to the pi

- Plug the pi into the power supply, Mixxx should start automatically
- Either plug in a USB keyboard, or connect the pi to the internet via ethernet and ssh to it (user: `pi`, password: `mixxx`)

## Package installation

- `sudo apt update`
- `sudo apt upgrade`
- vim
- i3blocks
- FontAwesome

## Locale configuration

- Set keyboard locale to English (US)
- Set timezone to Pacific/Auckland

## i3 configuration

- Copy i3 config file
- Copy i3blocks config and script files
- Run `i3-msg restart` to reload changes
- Once the custom menu bar is shown, the refresh button in the bottom right can be used to reload the bar

## Mixxx configuration

### Sound Hardware

- Configure Master and Cue output to soundcard of controller

### Library

- Enable rescan library on start-up
- Set library row height to 20px
- Ensure show Rekordbox library is enabled (if using rekordbox formatted USB stick)

### Controllers

- Make sure to copy controller mapping files to X
- Configure in controllers preferences

### Interface

- Change LateNight skin minimum resolution to X
- Open skin settings, uncheck mixer section, set deck size to compact
- Set locale to system in interface preferences
- Enable start in full-screen mode

### Waveforms

- Set waveform type to HSV, frame rate to 45, default zoom level to 14.3%

## Acknowledgements

- Fayaaz: https://github.com/fayaaz/mixxx-pi-gen for image
- TimewasterNL: https://djtechtools.com/2020/11/05/building-a-standalone-ddj-400-with-a-raspberry-pi-and-mixxx/ & https://www.youtube.com/watch?v=kyrJW7Vaf68
- i3blocks scripts: https://github.com/vivien/i3blocks-contrib

## License

Please refer to each individual configuration file to see the license.
