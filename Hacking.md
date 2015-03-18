for how to mod. the SConstruct for your -custom- arduino.

## Find out how genuin arduino IDE's work ##
add following configs to ~/.arduino/preferences.txt
```
build.verbose=true
upload.verbose=true
```
and build&upload in arduino IDE. you'll get verbose output of building and uploading process.

## Practice ##
for genuin arduino with atmega328. I can find...

```
avr-g++ -c -g -Os -w -fno-exceptions -ffunction-sections -fdata-sections \
-mmcu=atmega328p -DF_CPU=16000000L -DARDUINO=18 \
-I/usr/share/arduino/hardware/arduino/cores/arduino \
/tmp/.../BlinkWithoutDelay.cpp \
-o/tmp/.../BlinkWithoutDelay.cpp.o

avrdude -v -v -v -v -patmega328p -carduino -P/dev/ttyUSB0 -b57600 -D \
-Uflash:w:/tmp/.../BlinkWithoutDelay.cpp.hex:i
```