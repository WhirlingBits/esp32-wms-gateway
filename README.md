# esp32-wms-gateway

> **Short description:** ESP32 gateway for controlling Warema WMS radio devices
> via the Warema WMS stick using Warema's proprietary WMS protocol.

An ESP32-based gateway for controlling Warema radio-frequency (RF) devices through
the **Warema WMS USB stick**, using Warema's proprietary WMS protocol.

## Description

`esp32-wms-gateway` bridges a network-based control interface (e.g. a smart-home
system) and Warema's **WMS (Warema Mobile System)** ecosystem. Warema shades,
blinds, awnings, and related actuators communicate wirelessly over Warema's own
RF protocol. By connecting a **Warema WMS stick** to the ESP32 and speaking that
proprietary protocol, the gateway lets you send commands to and read status from
WMS devices without relying on Warema's cloud or mobile app.

The firmware runs on an ESP32 and exposes WMS devices to the rest of your network,
so shades and blinds can be integrated into home-automation setups and controlled
programmatically.

### How it works

1. A **Warema WMS stick** is attached to the ESP32 (over USB/serial), acting as the
   RF transceiver for the WMS network.
2. The gateway firmware drives the stick and implements Warema's proprietary WMS
   protocol to pair with, command, and query WMS devices.
3. The ESP32's network interfaces (Wi-Fi, and on PoE/Ethernet-capable boards,
   wired Ethernet) expose these devices to the local network for integration with
   smart-home platforms.

## Features

- Control Warema WMS RF devices (shades, blinds, awnings, and similar actuators)
- Communicates through the official Warema WMS stick
- Implements Warema's proprietary WMS protocol
- Local-network gateway — no dependency on Warema's cloud service
- Targets ESP32 hardware with Wi-Fi and, on supported boards, PoE/Ethernet

## Hardware

- An ESP32 development board (board support for the **ESP32-P4-WIFI6-POE-ETH**
  board is provided via the companion `wb-bsp` project)
- A **Warema WMS stick** connected to the ESP32

## Building

This project is built with the **ESP-IDF** toolchain. Set up ESP-IDF, then from the
project root:

```
idf.py set-target esp32p4
idf.py build
idf.py -p <PORT> flash monitor
```

> Note: adjust the target to match your specific ESP32 board.

## Status

Early development. The repository currently contains project scaffolding and CI
configuration; firmware functionality is being built out.

## License

See the repository for license information.
