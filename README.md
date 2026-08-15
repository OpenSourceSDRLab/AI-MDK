# AI-MDK
Custom firmware and hardware for the AI MDK used in PortaRF.


## Flashing the firmware manually with any ESP Web Tool / Flasher
1. Go to an ESP Web flasher with a browser that supports connecting to USB/serial port.
   
   For example use Google Chrome and https://esptool.spacehuhn.com/
   
3. Connect the USB-C cable between the AI-MDK (ESP32) and your computer while holding the DFU/Boot button.
4. Select the USB JTAG/serial debug unit.
5. Delete all the current addresses (Flash memory offset) by clicking on the red X.
6. Rebuild the addresses table as shown on the releases page. In this example only need to add the data after the 0x and select the file for that address. This may differ per ESP Flasher!

   For example:

                  bootloader.bin : 0x0000 -> 0000
                  xiaozhi.bin : 0x200000 -> 200000   
                  partition-table.bin : 0x8000 -> 8000
                  ota_data_initial.bin : 0xd000 -> d000
                  srmodels.bin : 0x10000 -> 10000
                  storage.bin : 0x100000 -> 100000
   
8. Press the green Program button.
9. The ESP Web Tool is now flashing the new firmware to the AI-MDK.
10. You will see when it is finished when the Output is saying "To Run the new firmware please reset the device".
11. You can now either unplug the USB-C cable or press the reset button on the AI-MDK.
12. Done. You can now place the AI-MDK back on the PortaRF board and use the new AI features.
