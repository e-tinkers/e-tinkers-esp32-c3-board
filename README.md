# E-Tinkers ESP32-C3 Board

E-Tinkers ESP32-C3 Board is a ESP32-C3 dev board base on ESP32-C3-WROOM-02 module from  Expressif, unlike the official ESP-C3-DevKitM-1 or ESP32-C3-DevKitC-02, E-Tinkers ESP32-C3 Board does not has the USB Type-C port and the ESPLink on-board programmer, but it does include an on-board 600mA LDO and break out all the GPIO pins. It is designed for using as a WiFi/BLE shield or to integrated with another MCU and/or sensors, and before creating your own customizing design, you need an ESP32-C3 evaluation board for rapid prototype, in both cases USB port is probably not needed in the end product.

## Specification and Key features

Component|Detail |
----|----|
MCU         | 32-bit single-core RISC-V |
ROM         | 384KB |
SRAM        | 400KB(16KB for cache) |
Flash       | 4MB |
WiFi        | IEEE 802.11bgn |
Bluetooth   | BLE 5.0 & mesh |
GPIO        | 22 |
SPI         | 3 |
UART        | 2 |
I2C         | 1 |
RMT         | 2 Transmit + 2 Receive |
DMA         | 3 Transmit + 3 Receive |
LED-PWMC    | 6 channels |
TWAI        | 1 |
ADC         | 2 x 12bit, 6 channels |
Temp sensor | 1 |
Timer       | 6 |
Security    | OTP/AES/SHA/RSA/RNG/HMAC |

## Pin Assignements
All available GPIO pins of the ESP32-C3-WROOM-02 are broken out to the pin headers on the board.
![E-Tinkers ESP32-C3 Board pinout](https://github.com/e-tinkers/e-tinkers-esp32-c3-board/blob/master/e-tinkers_esp32_c3_pinout.png)

## Firmware
Programming can be done using a USB-TTL Adaptor. The *Firmware* folder contains the firmware binary code , bootloader, and partition table for testing and demo purpose. Use [esptool](https://github.com/espressif/esptool) to upload the code to the board.

```
esptool.py --chip esp32c3 \
	--port /dev/cu.SLAB_USBtoUART \
	write_flash \
	--flash_mode dio \
	--flash_size 4MB \
	--flash_freq 80m \
	0x0 bootloader.bin \
	0x8000 partitions.bin \
	0x10000 firmware.bin
```

## Reference
### esp-idf
https://github.com/espressif/esp-idf
### esp32-c3 get-started
https://docs.espressif.com/projects/esp-idf/en/latest/esp32c3/get-started/
### esp32-c3
https://www.espressif.com/en/products/socs/esp32-c3
