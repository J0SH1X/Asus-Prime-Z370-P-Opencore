# ASUS-Prime-Z370-P-OpenCore
 
### Before you give this EFI a try, make sure you read [this](#generating-your-own-serial-and-editing-rom) and [this](#enabling-uefi-secure-boot-windows-11)!

This repo includes an OpenCore EFI for the ASUS Prime Z370-P motherboard.

Testing on:

Model | ASUS Prime Z370-P
------------- | ---------------
CPU | Intel Core i5-9500
iGPU | UHD 630
RAM | 8 GB DDR4
macOS | Monterey

## What works?

- Audio
- Boot
- USB
- Ethernet
- GPU acceleration
- Sleep
- Power Management

## What doesn't work?

- to be determined

## BIOS settings

[Dortania BIOS Guide](https://dortania.github.io/OpenCore-Install-Guide/AMD/zen.html#amd-bios-settings)

Note: TPM can be left enabled if dual booting Windows 11.

## How to install

Download this repo and place the EFI folder into your internal drive's EFI partition... That's it.

## How to Install macOS:

There are two ways you can make a USB installer:

1. Have a working install of macOS, download the Installer from the App Store, then make a bootable Installer with the `createinstallmedia` command
2. If you are using Windows, use [macrecovery.py](https://dortania.github.io/OpenCore-Install-Guide/installer-guide/winblows-install.html) from the offical OpenCore release package.

After you have created a bootable Installer, copy the EFI folder to the EFI partition of the installer drive and install as usual (GUID Partiton Map; APFS). After the installation, mount the EFI partition of the installed OS and copy the EFI folder to its partition.

## Generating your own serial and Editing ROM

Use GenSMBIOS (https://github.com/corpnewt/GenSMBIOS) to generate a serial for iMac19,1

use PlistEdit Pro or any decent plist editor to manually enter the details in the following sections of the config (as shown in the video): (SystemSerialNumber, MLB, and UUID)

https://user-images.githubusercontent.com/59102649/116117179-3ea51200-a6bc-11eb-8a18-a03f7bb5bf1d.mp4

You should also put in your ethernet adapter's MAC address into the ROM section.

## Enabling UEFI Secure Boot (Windows 11):

If you want to dual boot Windows 11 on your machine and therefore need to enable secure boot, follow the german guide [here](https://www.hackintosh-forum.de/forum/thread/54966-uefi-secure-boot-windows-11-und-monterey-dualboot-mit-opencore-teil-1/).

## Credits

* [TECHNIKVERBOT](https://github.com/TECHNIKVERBOT) (for rebuilding my EFI)
* [USBToolBox](https://github.com/USBToolBox) (for their awesome USB mapping tool)
* [acidanthera](https://github.com/acidanthera) (for OpenCore and the kexts)
* [dortania](https://dortania.github.io/OpenCore-Install-Guide/) (for their awesome guide)
