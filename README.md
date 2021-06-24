# mixxx-pi-config

## System preparation

- `sudo apt update`
- `sudo apt upgrade`

## Packages to install

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

## Mixxx configuration

### Library

- Enable rescan library on start-up
- Set library row height to 20px
- Ensure show Rekordbox library is enabled

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
