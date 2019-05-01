# Deskmini-310-Hackintosh
macOS Mojave 10.14.4 on Deskmini 310 + i5 8500 + BCM94352Z
=======

## Working Devices

- [x] Ethernet (Intel I219V7)
- [x] Audio (Realtek ALC233)
- [x] WIFI/Bluetooth (Broadcom BCM93452Z)
- [x] Graphics (Intel UHD 630)
- [x] Dual Monitors (DELL U2715H x 2) \*
- [x] Shutdown/Restart

\* *Known issue: always have to unplug/plug HDMI on boot...*

## Guide

### 1. BIOS

* Load UEFI Defaults
* Advanced
  * CPU Configuration
    * Intel Virtualization Technology: Disabled
  * Chipset Configuration
    * VT-d: Disabled
    * Onboard HD Audio: Enabled
  * USB Configuration
    * XHCI Hand-off: Enabled
  * Super IO Configuration
    * Serial Port: Disabled
* Security
  * Secure Boot: Disabled(by default)

## Post Installtion

### MultiBeast 11.0.1

* Drivers:
  * Audio: AppleALC
  * Network: IntelMausiEthernet v2.4.0
  * USB: Remove XHCI USB Port Limit + USBInjectAll
* System Definitions: Macmini6,2

### Clover Configurator

* ACPI:
  * Patches:
    * HDAS -> HDEF
    * EHC1 -> EC01
    * EHC2 -> EH02
* Boot
  * Arguments
    * slide=0(*Fix shutdown)
* Devices
  * Audio
    * Inject: 3
  * Properties
    * PciRoot(0x0)/Pci(0x1f,0x3) (*Fix audio)
      * layout-id: 1C000000
      * device-id: 48a30000
    * PciRoot(0x0)/Pci(0x2,0x0) (*Fix dual monitors)
      * AAPL,ig-platform-id: 07009B3E
      * device-id: 9B3E0000
      * enable-hdmi20: 01000000
      * framebuffer-con1-busid: 02000000
      * framebuffer-con1-enable: 01000000
      * framebuffer-con1-type: 00080000
      * framebuffer-con2-enable: 01000000
      * framebuffer-con2-index: FFFFFFFF
      * framebuffer-patch-enable: 01000000
      * framebuffer-portcount: 02000000
* SMBIOS:
  * Product Name: Macmini8,1

Install Drivers: EmuVariableUefi-64 (*Fix shutdown)

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
