How to change conf. for your environment.
# Default conf. #
to find out default options, find "ARGUMETS.get(..)"s in SConstruct.

# Get supported board list #
Give arbitrary board name to ARDUINO\_BOARD.
```
$ scons ARDUINO_BOARD=help
```
arscons use Arduino's board.txt to select proper MCU, F\_CPU, UPLOAD\_PROTOCOL and UPLOAD\_SPEED.

# Example #
For Arduino NG(atmega8), using external reset trigger(reset.py), add my\_libs/ for arduino library directory.
```
$ scons upload ARDUINO_BOARD=atmega8 RST_TRIGGER=./reset.py EXTRA_LIB=./my_libs ARDUINO_VER=19
```