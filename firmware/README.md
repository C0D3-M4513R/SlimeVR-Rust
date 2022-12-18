# Firmware
An implementation of SlimeVR firmware, built in Rust. Uses `embedded-hal` instead of
Arduino.

## Target Hardware
For now, we are only focused on the ESP32 platform, specifically the ESP32-C3, and the NRF52840.
We think these chips are the best platforms to develop the firmware on.

### ESP32-C3
* Super cheap chip ($1.80 for a module).
* Supports *both* WiFi and Bluetooth.
* USB serial without a uart converter. Keeps PCB costs low.
* Supports JTAG debugging *without* needing a hardware probe!
  This enables crazy stuff like logging over RTT which is much more efficient than serial.
* RISC-V architecture means it's well supported by LLVM, unlike the ESP32/8266.
* Hardware I2C instead of bit banging like on the esp8266.
* Unfortunately it's not as power efficient as the nrf52840.

### NRF52840
* NOT a cheap chip, like $6 for a module.
* Seems like it's 6-10x more power efficient than esp32c3.
  This is the main selling point, we can make *tiny* trackers.
* Bluetooth only, although we can do some proprietary protocols.
* Has amazing async rust support.
* Has built in USB support, not just as serial but full USB.
* Supports a debugger but only with a hardware probe.


## How to flash the firmware
This section is out of date, so is the CONTRIBUTING.md.
We will improve the documentation shortly.