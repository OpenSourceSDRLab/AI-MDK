# Third-party notices

This repository and its release files contain work by OpenSourceSDRLab together with third-party software. The Apache License 2.0 in [LICENSE](LICENSE) applies **only** to the files created by OpenSourceSDRLab:

- `README.md`, `NOTICE.md`, `docs/`, `images/`

The firmware files on the [Releases](../../releases) page are built from the components below. Each keeps its original copyright notice and licence:

| Component | Where | Owner | Licence |
|---|---|---|---|
| xiaozhi-esp32 (voice-assistant application framework) | `xiaozhi.bin` | Shenzhen Xinzhi Future Technology Co., Ltd. and the project contributors, <https://github.com/78/xiaozhi-esp32> | MIT |
| ESP32-Portapack (PortaPack I2C module protocol and web pages) | `xiaozhi.bin`, `storage.bin` | HTotoo, <https://github.com/htotoo/ESP32-Portapack> | Custom licence (HTL), see the project's `LICENSE` |
| ESP-IDF (boot loader, drivers, Wi-Fi and Bluetooth stacks) | `bootloader.bin`, `xiaozhi.bin`, `partition-table.bin`, `ota_data_initial.bin` | Espressif Systems | Apache License 2.0; some components under their own licences as listed in ESP-IDF |
| ESP-SR (audio front end and WakeNet speech models) | `srmodels.bin`, `xiaozhi.bin` | Espressif Systems | Espressif ESP-SR licence (use with Espressif chips only) |

The MIT licence of xiaozhi-esp32 requires the following notice to be included with copies of that software:

```
MIT License

Copyright (c) 2025 Shenzhen Xinzhi Future Technology Co., Ltd.
Copyright (c) 2025 Project Contributors

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

The PortaPack-module part of the firmware is based on code from the ESP32-Portapack project: <https://github.com/htotoo/ESP32-Portapack>.

"Espressif", "ESP32", "HackRF" and "PortaPack" are trademarks of their respective owners. They are used here only to describe compatibility and do not imply endorsement.
