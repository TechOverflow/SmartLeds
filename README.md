# SmartLeds

Simple & intuitive way to drive various smart LEDs on ESP32.

Requires ESP-IDF >=4.0 and C++17.

This fork (TechOverflow/SmartLeds) tracks [RoboticsBrno/SmartLeds](https://github.com/RoboticsBrno/SmartLeds)
and adds support for ESP32-C5, ESP32-C6 and ESP32-P4, and for ESP-IDF 6.x
(arduino-esp32 4.x), on top of the existing ESP32 / S2 / S3 / C3 support.

## PlatformIO configuration

PlatformIO projects must enable C++17 in `platformio.ini`:

```ini
build_unflags = -std=gnu++11
build_flags =
    -std=gnu++17
```

## Supported LEDs:

- WS2812 (RMT driver)
- WS2812B (RMT driver)
- SK6812 (RMT driver)
- WS2813 (RMT driver)
- APA102 (SPI driver)
- LPD8806 (SPI driver)

All the LEDs are driven by hardware peripherals in order to achieve high
performance.

## Drivers

## RMT driver

- can drive up to 8 strings
- occupies the RMT peripheral

## SPI driver

- can drive up to 2 strings
- occupies the SPI peripherals
- clock at 10 MHz

## Available

[PlatformIO - library 1740 - SmartLeds](https://platformio.org/lib/show/1740/SmartLeds)
