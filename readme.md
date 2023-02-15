# AHT20 library for RP2040

This is a library I created for my [personal project](https://github.com/skylordants/Pico_receiver). I'm sharing it, in case it is helpful to somebody and to make my code public, but I don't intend on regularily maintaining it, because it works for me, unless something big happens.

## Usage
The simplest way to use the library is to include it in a platformio project using [wizio-pico baremetal](https://github.com/Wiz-IO/wizio-pico) platform, but other projects using the RP2040 SDK should work as well. It depends on my [I2C](https://github.com/skylordants/rp2040_i2c) library, but can be made to work without it quite easily, if necessary.

An AHT20 object can be created by calling it's constructor and giving it a pointer to the I2C object. After that, the only thing to do is to call *measure*, which returns *true*, if it's successful. After that, the measurements are saved in the variables *temperature* and *humidity*. Functions *calculate_current_temperature* and *calculate_current_humidity* can be used to get the last measurements in normal units and *calculate_temperature* and *calculate_humidity* can be used to get correct units for any measurements provided.

## Sources
Most of the stuff is based on the [datasheet](https://files.seeedstudio.com/wiki/Grove-AHT20_I2C_Industrial_Grade_Temperature_and_Humidity_Sensor/AHT20-datasheet-2020-4-16.pdf). Some initial understanding in how the sensor work was from [DFRobot_AHT20](https://github.com/DFRobot/DFRobot_AHT20), which has an MIT license, but I didn't copy any code, so I shouldn't be committing any license infringement.
