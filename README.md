# Attunement
Replacement for Harmony - Extensive connectivity options and compatibility with existing harmony remote

## Project Aims:
- Node red style coding, Auto generated through wizard with ability to modify limitlessly
- Tight integration with home assistant
- Extensive connectivity and controllability (MQTT, HTTP, terminal, IR, RS232 etc)
- Bluetooth passthrough for 1 keyboard/mouse shared between multiple devices
- Expansible hardware built on raspberry pi (lots of IR outputs/inputs, Ethernet)
- Customise everything on the remote
- hosted completely locally
- Extraction of all IR commands from harmony
- Reuse of existing Harmony Remote (Remote uses unique IR commands to trigger Attunment Functions)

## Hub
- IR blaster built in + at least 4 IR expansion ports
- Multiple control methods Zigbee, Wifi, BLE, IR

## Remote
- Micro controller with wifi and bluetooth connection to base (esp32 or similar)
- Lipo Battery
- USB C connector (obvs)
- Touchscreen added (~2.4" 240 x 320)
- Dockable like Harmony
- LVGL graphical interface with menus not just a long list e.g. games, streaming.

## Remote Dock
- Pogo pin style connection to remote
- USB C power connection
- 3D printed with heavy metal insert for stability
- Optional IR blaster (maybe)

## Additional Blasters
- option to add more remote blasters synced to hub
