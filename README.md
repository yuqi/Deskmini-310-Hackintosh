# Deskmini-310-Hackintosh 
macOS Mojave 10.14.2 on Deskmini 310 + i5 8500 + BCM94352Z

## Working Devices

- [x] Ethernet (Intel I219V7)
- [x] Audio (Realtek ALC233)
- [x] WIFI/Bluetooth (Broadcom BCM93452Z)
- [x] Graphics (Intel UHD 630)
- [x] Dual Monitors (DELL U2715H x 2)
- [x] Shutdown/Restart

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
      * device-id: 70a10000
    * PciRoot(0x0)/Pci(0x2,0x0) (*Fix dual monitors)
      * AAPL,ig-platform-id: 0000923e
      * AAPL02,override-no-connect: 00ffffff ffffff00 10ac67d0 53515430 2f1a0103 803c2278 ee4455a9 554d9d26 0f5054a5 4b00b300 d100714f a9408180 77800101 0101565e 00a0a0a0 29503020 35005550 2100001a 000000ff 00433635 52443642 4c305451 530a0000 00fc0044 454c4c20 55323731 35480a20 000000fd 0038561e 711e000a 20202020 20200166 020322f1 4f100504 03020716 01141f12 13202122 23090707 83010000 65030c00 1000023a 80187138 2d40582c 25005550 2100001e 011d8018 711c1620 582c2500 55502100 009e011d 007251d0 1e206e28 55005550 2100001e 8c0ad08a 20e02d10 103e9600 55502100 0018483f 00ca8080 30401a50 13005550 2100001e 00000094
      * framebuffer-con2-enable: 01000000
      * framebuffer-con2-flags: c7030000
      * framebuffer-con2-type: 00080000
      * framebuffer-patch-enable: 01000000
* SMBIOS:
  * Product Name: Macmini8,1
  
Install Drivers: EmuVariableUefi-64 (*Fix shutdown)

#### Bluetooth/WIFI

Ref: [Broadcom WiFi/Bluetooth [Guide]](https://www.tonymacx86.com/threads/broadcom-wifi-bluetooth-guide.242423)

#### Fix shutdown

Ref: [[SUCCESS] Ongoing Status of Designare Z390 with i7-9700K](https://www.tonymacx86.com/threads/success-ongoing-status-of-designare-z390-with-i7-9700k.266065/)

#### Fix audio

Ref: https://github.com/YCF/Hackintosh-EFI-for-deskmini-310-i3-8100

#### Fix dual monitors

Ref: [[Guide] Intel Framebuffer patching using WhateverGreen](https://www.tonymacx86.com/threads/guide-intel-framebuffer-patching-using-whatevergreen.256490/post-1856330)

