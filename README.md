# Kodi Raspberry-Pi3
## Background
Enable compile-time optimizations that are specific for the Cortex-A53 processor in the Raspberry Pi 3 Model B and B+.

## Instructions
In addition to patching the upstream source, one should build with modified CFLAGS and with a few extra lines in the cmake step:

```
 export CFLAGS+=" -march=armv8-a+crc"
 export CXXFLAGS="${CFLAGS}"

 cmake ... -DCORE_SYSTEM_NAME=rbpi -DWITH_CPU=cortex-a53 ...
```

## Requirements
* Kodi Krypton 17.x or Leia 18.0a1. Do not attempt to patch Leia 18.0a2 as the patch has been merged upstream [PR#13638](https://github.com/xbmc/xbmc/pull/13638) slated for inclusion into that release.
* GCC >=7.2.1
