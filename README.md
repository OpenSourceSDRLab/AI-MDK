<p><a href="https://www.opensourcesdrlab.com"><img src="images/OpenSourceSDRLab-banner.jpg" alt="OpenSourceSDRLab" width="100%"></a></p>

# AI-MDK

Firmware and flashing instructions for the **OpenSourceSDRLab AI MDK**, the ESP32-S3 extension board that adds voice-assistant control to the **PortaRF** (HackRF One + PortaPack H4M in one unit).

## Product link

The AI MDK is sold as part of the PortaRF "with extension board" bundle:
<https://opensourcesdrlab.com/products/portarf>

## About the board

- Microcontroller: Espressif **ESP32-S3** with 16 MB flash, Wi-Fi and Bluetooth LE
- Fits the PortaRF expansion slot (board-to-board connector) and talks to the PortaRF firmware over I2C
- Uses the PortaRF microphone hole and speaker for voice input and spoken replies
- Wake word "Hi Mayhem"; voice commands start applications, switch between them or reboot the PortaRF
- Speech recognition runs on the OpenSourceSDRLab AI server; the AI MDK needs a Wi-Fi connection to reach it
- Also supports the functions of the plain ESP32 MDK (PortaPack external-module features)

## Quick start

1. Download the firmware files of the latest release from the [Releases](../../releases) page.
2. Hold the BOOT (DFU) button on the AI MDK, connect it to your computer with a USB-C cable, and write the six files at the offsets listed below with any ESP32 flasher.
3. Reset the AI MDK, put it back into the PortaRF and set up Wi-Fi.

The full steps are in the **[Quick Start Guide](docs/Quick-Start-Guide.md)** ([PDF](docs/Quick-Start-Guide.pdf)).

## Repository layout

| Path | Contents |
|---|---|
| `docs/` | Quick Start Guide (Markdown and PDF) |
| `images/` | OpenSourceSDRLab banner |

## Downloads (Releases)

The firmware is attached to the [Releases](../../releases) page. Write each file at its flash offset:

| File | Offset | Contents |
|---|---|---|
| `bootloader.bin` | `0x0` | ESP-IDF second-stage boot loader |
| `partition-table.bin` | `0x8000` | partition table |
| `ota_data_initial.bin` | `0xd000` | OTA data (selects the factory application) |
| `srmodels.bin` | `0x10000` | Espressif ESP-SR speech models (wake word) |
| `storage.bin` | `0x100000` | web pages and settings (SPIFFS) |
| `xiaozhi.bin` | `0x200000` | AI MDK application |
| `SHA256SUMS.txt` | | SHA-256 checksums of the files above |

Check a download with `shasum -a 256 -c SHA256SUMS.txt` (macOS / Linux) or `certutil -hashfile <file> SHA256` (Windows).

## Licence

Files created by OpenSourceSDRLab are released under the [Apache License 2.0](LICENSE). The firmware is built on open-source projects from Espressif, the xiaozhi-esp32 project and the ESP32-Portapack project, which remain under their own licences; see [NOTICE.md](NOTICE.md).

## Support

- Email: support@opensourcesdrlab.com
- Forum: <https://forum.opensourcesdrlab.com>
- Discord: <https://discord.gg/nnxY6DkmvT>
- Blog and user manuals: <https://blog.opensourcesdrlab.com>

---
<sub>© 2026 OpenSourceSDRLab. All rights reserved. · <a href="https://www.opensourcesdrlab.com">www.opensourcesdrlab.com</a></sub>
