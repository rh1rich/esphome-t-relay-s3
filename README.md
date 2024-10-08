# esphome-t-relay-s3
LilyGo T-RelayS3 with ESPHome

This ESPHome configuration file can be used as starting template for your own project.
All onboard components are preconfigured to work with Home Assistant.
## SoC
The board uses a ESP32-S3-WROOM-1U-N16R8 which has 16MB flash and 8MB PSRAM.
Because this board is not listed on [PlatformIO](https://registry.platformio.org/platforms/platformio/espressif32/boards), `esp32s3box` is used as `board`. The ESP32-S3-Box uses the same SoC.
## OnBoard components
### Relays
The 6 relays, which are controlled through a SN74HC595 shift-register, are configured as switches.
If you connect one ore more T-Relay-Chain boards, you have to increase the `sr_count` of the `sn74hc595` component and add additional switch components for each relay.
### LEDs
The red and green LEDs, which are also controlled through a SN74HC595 shift-register, are configured as status LEDs.
The red LED works as a ESPHome status_led.
The green LED works as a status led for the network connection and is implemented via the `interval` component.
- LED off ... no wifi connection
- LED blinking ... wifi connection
- LED on ... api connection
### Real-time-clock (PCF8563)
The onboard real-time-clock PCF8563 (I2C) is used to update the time on boot.
### Temperatur sensor (DS18B20)
The board is prepared to connect/solder a DS18B20 temperture (1-wire) sensor.
The configuration for this sensor is also integrated but commented out.
