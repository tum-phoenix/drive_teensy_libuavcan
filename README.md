UAVCAN stack in C++
===================

Portable reference implementation of the [UAVCAN protocol stack](http://uavcan.org) in C++ for embedded systems
and Linux.

UAVCAN is a lightweight protocol designed for reliable communication in aerospace and robotic applications via CAN bus.

## Documentation

* [UAVCAN website](http://uavcan.org)
* [UAVCAN discussion group](https://groups.google.com/forum/#!forum/uavcan)
* [Libuavcan overview](http://uavcan.org/Implementations/Libuavcan/)
* [List of platforms officially supported by libuavcan](http://uavcan.org/Implementations/Libuavcan/Platforms/)
* [Libuavcan tutorials](http://uavcan.org/Implementations/Libuavcan/Tutorials/)

## Library usage

### Dependencies

* Python 2.7 or 3.3 or newer
* [Arduino IDE](https://www.arduino.cc/en/main/software)
* [Teensyduino](https://www.pjrc.com/teensy/td_download.html)
* [GCC ARM Embedded](https://launchpad.net/gcc-arm-embedded)

Note that this reporitory includes [Pyuavcan](http://uavcan.org/Implementations/Pyuavcan) as a submodule.
Such inclusion enables the library to be built even if pyuavcan is not installed in the system.

Install Arduino and Teensyduino (for example in /opt).

### Cloning the repository

```bash
git clone https://github.com/tum-phoenix/drive_teensy_libuavcan
cd drive_teensy_libuavcan
git checkout <correct branch>
git submodule update --init
```

Change paths and device settings in `cmake/teensy-arm.toolchain.cmake`.


### Building and installing

Cross-compile with CMake:

```bash
mkdir build
cd build
cmake .. -DCMAKE_TOOLCHAIN_FILE=../cmake/teensy-arm.toolchain.cmake -DUAVCAN_PLATFORM=teensy32
make
```
