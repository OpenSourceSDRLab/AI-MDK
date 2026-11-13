---
title: AI MDK Quick Start Guide
product: AI MDK
doc_id: OSSDRLAB-AI-MDK-QSG
version: 1.0
date: 2026-11-12
repo: https://github.com/OpenSourceSDRLab/AI-MDK
---

<!-- ossl:header -->
<p><a href="https://www.opensourcesdrlab.com"><img src="../images/OpenSourceSDRLab-banner.jpg" alt="OpenSourceSDRLab" width="100%"></a></p>

# AI MDK Quick Start Guide

| Product | Document | Version | Date |
|---|---|---|---|
| AI MDK | OSSDRLAB-AI-MDK-QSG | 1.0 | 2026-11-12 |
<!-- /ossl:header -->

## 1. Overview

The AI MDK is an ESP32-S3 extension board for the OpenSourceSDRLab PortaRF. It sits in the PortaRF expansion slot, talks to the PortaRF firmware over I2C, and adds voice-assistant control: after the wake word "Hi Mayhem" you can start applications, switch between them or reboot the PortaRF by voice. Speech recognition runs on the OpenSourceSDRLab AI server, so the AI MDK needs a Wi-Fi connection.

This guide shows how to update the AI MDK firmware and how to connect it to Wi-Fi.

## 2. What you need

| Item | Notes |
|---|---|
| PortaRF with the AI MDK extension board | the "with extension board" bundle |
| USB-C cable | data cable, not a charge-only cable |
| Computer | Windows, macOS or Linux |
| Firmware files | the six `.bin` files of the latest release from the [Releases](../../../releases) page |
| ESP32 flashing tool | a browser-based ESP32 web flasher (Google Chrome or Microsoft Edge, which support Web Serial), or Espressif's `esptool` |
| 2.4 GHz Wi-Fi network | for the AI server connection |

## 3. Flash memory map

| File | Offset |
|---|---|
| `bootloader.bin` | `0x0` |
| `partition-table.bin` | `0x8000` |
| `ota_data_initial.bin` | `0xd000` |
| `srmodels.bin` | `0x10000` |
| `storage.bin` | `0x100000` |
| `xiaozhi.bin` | `0x200000` |

Some web flashers expect the offset without the `0x` prefix (for example `200000` instead of `0x200000`).

## 4. Update the firmware

1. Open the PortaRF and take the AI MDK out of the expansion slot.

2. Hold the **BOOT** (DFU) button on the AI MDK and connect it to the computer with the USB-C cable. Release the button after it is connected.

3. Open an ESP32 web flasher in Chrome or Edge, click **Connect** and select the USB JTAG/serial debug unit.

4. Remove any preset entries in the flasher's address table, then add the six files at the offsets in section 3.

5. Click **Program** and wait until the log reports that the flashing has finished.

6. Press the **RESET** button on the AI MDK or unplug the USB-C cable.

7. Put the AI MDK back into the PortaRF expansion slot.

> **Tip:** with `esptool` the same step is one command (replace the port name):
>
> `esptool --chip esp32s3 --port <PORT> write_flash 0x0 bootloader.bin 0x8000 partition-table.bin 0xd000 ota_data_initial.bin 0x10000 srmodels.bin 0x100000 storage.bin 0x200000 xiaozhi.bin`

## 5. Connect to Wi-Fi

1. Switch on the PortaRF. On first start, or after the Wi-Fi settings have been cleared, the AI MDK starts a Wi-Fi access point for configuration and announces it by voice.

2. Connect a phone or computer to that access point and open the address `192.168.4.1` in a browser.

3. Select your 2.4 GHz network, enter the password and save. The AI MDK restarts and announces when it is connected.

4. Say "Hi Mayhem", then give a command, for example to open an application.

> **Tip:** to change the network later, open the AI MDK web page and use **Reconfigure WiFi**; the AI MDK clears the saved network and restarts in configuration mode.

## 6. Support

- Email: support@opensourcesdrlab.com
- Forum: <https://forum.opensourcesdrlab.com>
- Discord: <https://discord.gg/nnxY6DkmvT>
- Blog and user manuals: <https://blog.opensourcesdrlab.com>

<!-- ossl:footer -->
---
<sub>© 2026 OpenSourceSDRLab. All rights reserved. · <a href="https://www.opensourcesdrlab.com">www.opensourcesdrlab.com</a></sub>
<!-- /ossl:footer -->
