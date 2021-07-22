# mixxx-pi-config

This project documents the steps I took and configuration files I used to create a standalone Mixxx DJ setup using a Raspberry Pi. It is inspired by the standalone DDJ400 project completed by [TimewasterNL](https://djtechtools.com/2020/11/05/building-a-standalone-ddj-400-with-a-raspberry-pi-and-mixxx/), and the instructions & files provided by [Fayaaz](https://github.com/fayaaz/mixxx-pi-gen). The supplied configuration files extend Fayaaz's configuration to customise the menu bar (i3bar) shown at the bottom of the screen, providing buttons to open Mixxx and turn off the system without needing a keyboard. It also makes use of unclutter to hide the mouse pointer after a small time delay.

## Hardware components

- Raspberry Pi 4 Model B (8GB RAM)
- Raspberry Pi 7" Touch Display
- SmartiPi Touch 2 case
- USB DJ controller with in-built sound card (e.g: DDJ400, XONE:K2)
- Micro SD card (32GB)
- USB stick with music
- USB-C power supply (or a USB-C power bank)

## Pi Image preparation

- Download mixxx-pi-gen image to SD card (I used [MixxxPiBeta64v1](https://github.com/fayaaz/mixxx-pi-gen/releases/tag/v0.5.0) aka v0.5.0)
- Insert SD card into the pi

## Assembling the hardware components

- See https://smarticase.com/pages/smartipi-touch-2-setup-1

## Connecting to the pi

- Plug the pi into the power supply, Mixxx should start automatically
- To interact with the pi, either plug in a USB keyboard (use `meta+enter` key to open a terminal), or connect it to the internet and use ssh to control it from another computer (user: `pi`, password: `mixxx`)
- To connect the pi to the internet either use an ethernet connection or use `raspi-config` to configure a wifi connection

## Package installation

*First, update & upgrade the pi*

- `sudo apt update`
- `sudo apt upgrade`

*Next, you'll want to `apt-get` the following packages:*

- `vim` (or your preferred editor)
- `i3blocks`
- `FontAwesome`
- `unclutter`

## Locale configuration

*These steps are easiest using `raspi-config` with a keyboard on the pi*

- Set keyboard locale to English (US) (or your preferred language)
- Set timezone to Pacific/Auckland (or your preferred timezone)

## i3 configuration

- Update the installed i3 config file from the image to match the one in this repo
- Copy the i3blocks config and script files from this repo
- Run `i3-msg restart` to reload changes to i3
- Once the custom menu bar is shown, the refresh button in the bottom right can be used to reload the bar

## Mixxx configuration

*The following configuration takes places in the Mixxx preferences window, and in some mixxx config files*

### Sound Hardware

- Configure Master and Cue output to soundcard of controller

### Library

- Enable rescan library on start-up
- Set library row height to 20px
- Ensure show Rekordbox library is enabled (if using rekordbox formatted USB stick)

### Controllers

- Make sure to copy any custom controller mapping files to the mixxx controllers folder. You must restart mixxx for the mappings to appear
- Configure MIDI device in controllers preferences

### Interface

- Modify LateNight skin `MinimumSize` to match your display (e.g: `800,450` for the Raspberry Pi 7" Touch Display). You can find the config file in the mixxx skins folder e.g: `mixxx/skins/LateNight/skin.xml`. You must restart mixxx for these changes to take effect
- Open skin settings, uncheck mixer section, set deck size to compact
- Set locale to system in interface preferences
- Enable start in full-screen mode

### Waveforms

- Set waveform type to HSV, frame rate to 45, default zoom level to 14.3%

## Acknowledgements

- Fayaaz: https://github.com/fayaaz/mixxx-pi-gen for image and base i3 config
- TimewasterNL: https://djtechtools.com/2020/11/05/building-a-standalone-ddj-400-with-a-raspberry-pi-and-mixxx/ & https://www.youtube.com/watch?v=kyrJW7Vaf68
- i3blocks scripts: https://github.com/vivien/i3blocks-contrib

## License

Please refer to each individual configuration file to see the license.

## TODO

Expand this README with:

- More detailed install commands & paths
- Add some images or video recordings to showcase the pi
