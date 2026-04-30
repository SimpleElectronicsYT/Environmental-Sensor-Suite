Design considerations for the project

Temperature gathering
The broad idea is to be able to gather air and/or water temperatures but have a waterproof housing

DHT-11 / DHT-22 don't seem like a good fit - they are generally precise but will not be able to gather temperature from fluid touching the housing - a sensor that can be pressed onto the exterior wall of the sensor housing seems like a better fit

Dallas 18B20
https://www.analog.com/media/en/technical-documentation/data-sheets/ds18b20.pdf

This sensor will be in the prototype 1 version of this hardware.
- -55C to +125C total range - way beyond 'typical' conditions
- +- 0.5C from -10C to +85C water temperature ranges fit very well into this range
- Up to 12 bit resolution
- No external components required
- Only requires 2 pins - not important in this case, but if a unified sensor version is made in the future, this is a useful feature
- Supported out of the box by MicroPython using onewire and ds18x20 libraries

Microcontroller selection:
ESP-32-S3 is my initial choice for this project:
- Newer chip and has nice modern features like deep sleep and built-in wireless
- High speed enough to be able to run well with micropython
- Reasonable built-in memory and storage which can be used instead of or in conjunction with SD-Card storage if needed (4MB of flash)

Specific board selection
ESP32-S3-Super Mini
https://www.espboards.dev/esp32/esp32-s3-super-mini/
- At this stage, it is not economically viable to design a board to replace the ESP32-S3-Super Mini since the footprint it has is nearly impossible to shrink and design resources need to go towards a working prototype. No chip-level design will take place until:
  - The prototype is proven to be working
  - The PCB has been designed to carry the ESP32-S3-Super Mini
  - A new hardware revision needs to be designed
- The Super Mini board can be made to have all the features needed for this project (and room for future improvement)