## Raspberry Pi LFS GCC CPU Default Patches
**Changes the default dynamic linker in GCC config from soft float (ld-linux.so.3) to hard float (ld-linux-armhf.so.3)<br />
Author: Mogwai (https://intestinate.com/pilfs)<br />
Project Manager: Jon Wilder<br />
Created under GNU General Public License v3**<br /><br />

## Release Notes
**gcc-9.1.0-rpi-cpu-default.patch** - Patch version for GCC-9

**gcc-10.1.0-rpi-cpu-default.patch** - Patch version for GCC-10

## Changelog
**gcc-9.1.0-rpi-cpu-default.patch** - Patches gcc/config.gcc at line 1189

**gcc-10.1.0-rpi-cpu-default.patch** - Patches gcc/config.gcc at line 1279

## Description
These patch files are mandatory for selecting the hardfloat dynamic linker as the default dynamic linker. For each Pi version 1-4, it adds the correct configure options for --with-cpu=, --with-fpu=, and --with-float=hard for the correct processor type in file <PKG_ROOT>/gcc/config.gcc. This ensures that GCC gets compiled with the hard float dynamic linker ld-linux-armhf.so.3.

Without these patch files, the ARM dynamic linker will default to the soft float dynamic linker, ld-linux.so.3.

After untarring and changing into the gcc sources directory, run -

patch -Np1 -i ../gcc-10.1.0-rpi1-cpu-default.patch

Changing the number after "rpi" to match your Pi version.

## Contact Information
Any questions, comments, and concerns? Please contact me at RPiLFS@comcast.net
