# Sonyapilib
[![Build Status](https://travis-ci.org/alexmohr/sonyapilib.svg?branch=v4)](https://travis-ci.org/alexmohr/sonyapilib)
[![Coverage Status](https://coveralls.io/repos/github/alexmohr/sonyapilib/badge.svg?branch=v4)](https://coveralls.io/github/alexmohr/sonyapilib?branch=v4)

This library controls sony devices of all generations which are supported by the TVSideView app. In contrast to other libraries like https://github.com/aparraga/braviarc this supports older generations aswell.

Code has been taken from the following repositories.
* https://github.com/KHerron/SonyAPILib
* https://github.com/aparraga/braviarc

This library is used as communication interface in a home assistant component to control media players, which can be found here: https://github.com/alexmohr/media_player.sony

At the moment not all functions offered by the api are implemented. If you miss a function feel free to create a pull request or open a feature request.

# Installation
To install simply run
```
pip install sonyapilib
```

This library has been tested with python 3.5 and above, functionality for older python version cannot be guaranteed.

# Example
This example connections with device (of which the ip address is hard coded) start the registration process and starts the first available. More detailed examples can be found in the examples folder.
```
from sonyapilib.device import SonyDevice

if __name__ == "__main__":
    # device must be on for registration
    host = "10.0.0.102"
    device = SonyDevice(host, "SonyApiLib Python Test")
    device.register()
    pin = input("Enter the PIN displayed at your device: ")
    if not device.send_authentication(pin):
        print("Failed to register device")
        exit(1)

    apps = device.get_apps()
    device.start_app(apps[0])
    device.play()

```

# URL list

https://github.com/chr15m/media-remote/blob/master/SNIFF.md

https://gist.github.com/kalleth/e10e8f3b8b7cb1bac21463b0073a65fb

# Compatibility List

### 2016 model or later
KDL-W/WD, KLV-W Series (2016 model) are not compatible with Video & TV SideView. (Except for KDL-W800D/W950D)
 
You can not install Video & TV SideView app into your Sony's Android TV™.

### 2015 model
XBR-X94xC series, XBR-X93xC series, XBR-X91xC series, XBR-X90xC series, XBR-X85xC series, XBR-X83xC series, XBR-X80xC series, KD-X94xxC series, KD-X93xxC series, KD-X91xxC series, KD-X90xxC series, KD-X85xxC series, KD-X83xxC series, KD-X80xxC series, KDL-W95xC series, KDL-W85xC series, KDL-W80xC series, KDL-W75xC series, KDL-W70xC series, KDL-W600A series

Please update your TV software to the latest version.

### 2014 model
XBR-X95xB series, XBR-X90xB series, XBR-X85xB series, KD-X95xxB series, KD-X90xxB series, KD-X85xxB series, KD-X83xxC series, KD-X80xxB series, KDL-W95xB series, KDL-W92xA series, KDL-W90xB series, KDL-W85xB series, KDL-W83xB series, KDL-W8xxB series, KDL-W7xxB series, KDL-W6xxB series, KDL-W5xxA series

### 2013 model
XBR-X90xA series, XBR-X85xA series, KD-X900xA series, KD-X850xA series, KDL-W95xA series, KDL-W90xA series, KDL-W85xA series, KDL-W80xA series, KDL-W70xA series, KDL-W67xA series, KDL-W65xA series, KDL-W60xA series, KDL-S99xA series

### 2012 model
XBR-X90x series, KD-X900x series, XBR-HX95 series, KDL-HX95 series, KDL-HX85 series, KDL-HX75 series, KDL-NX65 series, KDL-EX75 series, KDL-EX65 series, KDL-EX55 series, KDL-EX54 series

### 2011 model
XBR-HX92 series, KDL-HX92 series, KDL-HX82 series, KDL-HX72 series, KDL-NX72 series, KDL-EX72 series, KDL-EX62 series, KDL-EX52 series, KDL-EX42 series, KDL-EX32 series, KDL-CX52 series, KDL-CX40 series

### Blu-ray Disc™/DVD Player
UHP-H1, BDP-S6700, BDP-S3700, BDP-S6500, BDP-S5500, BDP-S4500, BDP-S3500, BDP-S7200, BDP-S6200, BDP-S5200, BDP-S4200, BDP-S3200, BDP-BX620, BDP-BX520, BDP-BX320, BDP-S5100, BDP-S4100, BDP-S3100, BDP-BX510, BDP-BX310, BDP-A6000, BDP-S790, BDP-S590, BDP-S490, BDP-S390, BDP-BX59, BDP-BX39, BDP-S780, BDP-S580, BDP-S480, BDP-S380, BDP-BX58, BDP-BX38, BDP-S1700ES, BDP-S770, BDP-S570, BDP-S470, BDP-S370, BDP-BX57, BDP-BX37

### Blu-ray Disc™/DVD Home Theatre System
BDV-N9200WL, BDV-N9200W, BDV-NF7220, BDV-N7200WL, BDV-N7200W, BDV-N5200W, BDV-E3200, BDV-N9900SH, BDV-N9150WL, BDV-N9150W, BDV-N9100WL, BDV-N9100W , BDV-N8100WL, BDV-N8100W , BDV-N7100WL, BDV-N7100W, BDV-E6100 , BDV-E5100, BDV-E4100, BDV-E3100, BDV-E2100, BDV-EF1100, BDV-N995W, BDV-N990W, BDV-N890W, BDV-N790W, BDV-N590, BDV-E690, BDV-E490, BDV-E390, BDV-E385, BDV-E290, BDV-E190, BDV-NF720, BDV-NF620, BDV-EF420, BDV-EF220, BDV-T79, BDV-T39, BDV-E985W, BDV-E980W, BDV-E980, BDV-E880, BDV-E780W, BDV-E580, BDV-E380, BDV-L800M, BDV-L800, BDV-L600, BDV-T58, BDV-IZ1000W, BDV-HZ970W, BDV-E970W, BDV-E870, BDV-E770W, BDV-E670W, BDV-E570, BDV-E470, BDV-E370, BDV-F700, BDV-F500, BDV-F7, BDV-T57

### Streaming Player / Network Media Player
NSZ-GS8, NSZ-GU1, NSZ-GX70, NSZ-GS7, SMP-N200, SMP-N100

### Sony Internet TV
NSX-46GT1, NSX-40GT1, NSX-32GT1, NSX-24GT1, NSZ-GT1

### AV Receiver
STR-DN1070, STR-DN1060, STR-DN860, STR-DN1050, STR-DN850, STR-DN1040, STR-DN840,　STR-DA1800ES, STR-DN1030, STR-DN1020
