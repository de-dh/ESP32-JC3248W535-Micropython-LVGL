# ESP32-JC3248W535-Micropython-LVGL

## Description
This repo is about running LVGL under MicroPython on the **JC3248W535** aka Cheap Black Display (CBD).

The firware was compiled from / includes:
- [Kdschlosser's Micropython Bindings](https://github.com/lvgl-micropython/lvgl_micropython) - LVGL9 bindings for Micropython.
- [Straga's MicroPython LCD Display Project](https://github.com/straga/micropython_lcd/) - LCD axs15231b QSPI and Touch axs15231b I2C driver.


The firmware was compiled from lvgl_micropython commit [af5263c](https://github.com/lvgl-micropython/lvgl_micropython/commit/af5263c7c0618ebd791e1fe2904fde9bb6234e7c). 
Newer versions include breaking changes regarding the USB connection.
Straga's new SPI driver (kdschlosser/lvgl_micropython#456) which allows 90° rotation and the touch fix (kdschlosser/lvgl_micropython#454) for correct touch calibration were included.

Them following build and flash commands were used (see [here](https://github.com/straga/micropython_lcd/tree/master/device/JC3248W535)):

```shell
# build
python make.py esp32 BOARD=ESP32_GENERIC_S3 BOARD_VARIANT=SPIRAM_OCT --flash-size=16

# flash
python -m esptool --chip esp32s3 --port COM7 -b 460800 --before default_reset --after hard_reset write_flash --flash_mode dio --flash_size 16MB --flash_freq 80m --erase-all 0x0 lvgl_micropy_ESP32_GENERIC_S3-SPIRAM_OCT-16_NEW_SPI.bin
```

## Instructions

1. Flash the firmware.
2. Upload the `/lib` folder and the test programs `test_landscape_mode.py` and `test_portrait_mode.py` to the device.
3. Run the test programs.


## Using The Onboard LiPo Charger

WIP
