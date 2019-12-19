# Deskmini-310-Hackintosh
macOS Catalina 10.15.2 on Deskmini 310 + i5 8500 + BCM94352Z
=======

## Working Devices

- [x] Ethernet (Intel I219V7)
- [x] Audio (Realtek ALC233)
- [x] WIFI/Bluetooth (Broadcom BCM93452Z)
- [x] Graphics (Intel UHD 630)
- [x] Dual Monitors (DELL U2715H x 2)
- [x] Shutdown/Restart

## Guide

### BIOS

* Load UEFI Defaults
* Advanced
  * Chipset Configuration
    * VT-d: Disabled
    * Onboard HD Audio: Enabled
  * USB Configuration
    * XHCI Hand-off: Enabled
  * Super IO Configuration
    * Serial Port: Disabled
* Security
  * Secure Boot: Disabled(by default)

### Post Installtion

1. Install Clover bootloader v2.5k r5100 (https://github.com/CloverHackyColor/CloverBootloader/releases/tag/5100)
2. Mount EFI (Clover Configurator etc.)
3. Clone this repo to EFI volume

#### USB

Ref: [List of Hackintosh USB Port Limit Patches (10.14 Updated)](https://hackintosher.com/forums/thread/list-of-hackintosh-usb-port-limit-patches-10-14-updated.467/)

#### Bluetooth/WIFI

[Broadcom WiFi/Bluetooth [Guide]](https://www.tonymacx86.com/threads/broadcom-wifi-bluetooth-guide.242423)

#### Fix shutdown

[[SUCCESS] Ongoing Status of Designare Z390 with i7-9700K](https://www.tonymacx86.com/threads/success-ongoing-status-of-designare-z390-with-i7-9700k.266065/)

#### Fix audio

https://github.com/YCF/Hackintosh-EFI-for-deskmini-310-i3-8100

#### Fix dual monitors

[Install hackintosh(Mojave 10.14.x) in Asrock deskmini 310](https://github.com/liminghuang/asrock_deskmini310_hackintosh)

[Mojave UHD 630 on i5 8400 issues, have tried everything](https://www.tonymacx86.com/threads/mojave-uhd-630-on-i5-8400-issues-have-tried-everything.269368/page-3#post-1889723)

[[Guide] Intel Framebuffer patching using WhateverGreen](https://www.tonymacx86.com/threads/guide-intel-framebuffer-patching-using-whatevergreen.256490/post-1856330)
