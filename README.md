# kodi-raspberrypi3
## Background
This patch enables Kodi optimizations specific for the Cortex-A53 processor in the Raspberry Pi 3. Tested and verified on a Raspberry Pi 3 running Arch ARMv7 (armv7h).

## Instructions
In addition to patching the upstream source with this patch, you will need to build with modified CFLAGS and with a few extra lines in the cmake step.

Append the following two lines to augment your distro defaults:
```
 CFLAGS+=" -march=armv8-a+crc -mcpu=cortex-a53 -mfpu=neon-fp-armv8"
 CXXFLAGS="${CFLAGS}"
```

In the cmake step, ensure you add the following:
```
-DCORE_SYSTEM_NAME=rbpi -DWITH_CPU=cortex-a53
```

## Requirements
* Kodi Kryption 17.6
* GCC 7.2.1 and 7.3.0

Note that other versions may work but are unsupported.

