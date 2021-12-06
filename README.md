# PenPoint-Virtualbox
Virtualbox image with PenPoint SDK 1.0 and PenPoint OS itself

## Image contents:

* FreeDOS 1.3-rc4 from [freedos.org](https://www.freedos.org/)
* PenPoint SDK from [Bitsavers](http://www.bitsavers.org/bits/Go/PENPOINT_SDK/)
* PenPoint OS 1.0
* Various PenPoint Goodies

## Installation

0. Download .ova file
1. Open Virtualbox
2. In Virtualbox, select File -> Import configuration
3. Select .ova file

## Run

To launch PenPoint OS, simply start virtual machine and type **go** after it boots

## Exit to DOS

To exit from PenPoint OS to DOS, press **PAUSE** and then **q**

## Fun things to do

GO.BAT and different .INI files in PENPOINT\BOOT are well-documented and full of comments, so by editing them you can do a lot of fun things, like:

### Boot debug version of PenPoint OS

To boot debug version of PenPoint OS, change file `\PENPOINT\SDK\UTIL\DOS\GO.BAT`. Comment line `\penpoint\boot\ppboot \penpoint\boot` and uncomment `\penpoint\boot\ppboot \penpoint\boot\_pp.os \penpoint\boot\mil.os \penpoint\boot\mil.ini`

### Change screen orientation

To change screen orientation, go to `PENPOINT\BOOT` and change `MIL.INI`. Replace `InitialScreenTop=fromBootProgram` with any of the following lines:

```
InitialScreenTop=North 
InitialScreenTop=South 
InitialScreenTop=East 
InitialScreenTop=West 
```

### Serial debugging

Sometimes PenPoint OS refuses to boot. You can redirect debug logs to serial. To do this, edit `\PENPOINT\BOOT\MIL.INI`, and uncomment `SerialDebugPort=l` and `#LowLevelDebug=com1`

### Further info

To find more about how to tweak your PenPoint OS installation, read [PenPoint Development Tools](http://ohlandl.ipv7.net/2524/PenPoint_Development_Tools_Jun92.pdf), chapter "Running PenPoint on a PC"

