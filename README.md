# ESP32-JC3248W535-Micropython-LVGL
This repo is about running LVGL under MicroPython on the **JC3248W535** aka Cheap Black Display (CBD).

The firware was compiled from / includes:
- [Kdschlosser's Micropython Bindings](https://github.com/lvgl-micropython/lvgl_micropython) - LVGL9 bindings for Micropython.
- [Straga's MicroPython LCD Display Project](https://github.com/straga/micropython_lcd/) - LCD axs15231b QSPI and Touch axs15231b I2C driver.


The firmware was compiled from lvgl_micropython commit [af5263c](https://github.com/lvgl-micropython/lvgl_micropython/commit/af5263c7c0618ebd791e1fe2904fde9bb6234e7c). 
Newer versions include breaking changes regarding the USB connection.
Straga's new SPI driver (kdschlosser/lvgl_micropython#456) which allows 90° rotation and the touch fix (kdschlosser/lvgl_micropython#454) for correct touch calibration were included.
