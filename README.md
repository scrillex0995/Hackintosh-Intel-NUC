# Hackintosh-Intel-NUC
Install macOS Catalina, Big Sur, Montery on your Intel NUC5i5MYBE with dualboot using this guide.
This guide is based on dortania's opencore guide. The EFI will updating recently like this guide, so you can check it some times for updates.


* Installation USB[]
* Setting up UEFI
* Kexts
* BIOS settings
* Installation

## Installation USB
Creating USB may help you dortania's guide

I am recommending you to make USB from macOS. If you don't have broadcom wifi or ethernet, the installation process will take very long time(4-7 hours).

## Setting up UEFI
You don't have to create an EFI from scratch, because I did. Just download latest version ```EFI``` Folder from repository.
After Download, just move it to your USB like in dortania's guide.

## Kexts
It's one of the most important stuff that you have to read in this guide.
Intel NUC by default doesn't have wifi or bluetooth, you'll want to use only [IntelMausi.Kext](https://github.com/acidanthera/IntelMausi/releases) to get Intel ethernet working
If you have bought wifi or bluetooth card: ->

Intel
* [Intel Wifi Kexts](https://github.com/OpenIntelWireless/itlwm/releases)
* [Intel Bluetooth Kexts](https://github.com/OpenIntelWireless/IntelBluetoothFirmware)

Broadcom
* [Broadcom Wifi patch](https://github.com/acidanthera/AirportBrcmFixup/releases)
* [Broadcom Bluetooth patch](https://github.com/acidanthera/BrcmPatchRAM/releases)

This kexts should be installed for working bluetooth and wifi.

## BIOS settings
### To start press f9 to return default settings
BIOS setting should be set:
* Devices->USB, "xHCI Mode" set to "Smart Auto"
* Devices->Video, "IGD Minimum Memory" set to 64mb
* Devices->Video, "IGD Aperture Size" set to 256mb
* Boot->Secure Boot, "Secure Boot" is disabled
* Security->Security Features, "Execute Disable Bit" is
* Boot->Boot Priority->Legacy Boot Priority, disable "Legacy Boot"

## Installation
Insert your USB drive, ```press f10 to get to boot menu```.
Hold alt to see boot picker and choose your dmg file

Now you are in macOS recovery:
* select langauge
* format your disk using disk utility (APFS or MacOS extended and GUID Partition)
* choose install macOS

Disk utility erase options:


![image](https://github.com/Irox-cpu/Hackintosh-Intel-NUC/assets/61883651/d975e143-6306-42b1-80d2-ab57dcafd1bf)

## Info and Troubleshoot
During the installation you'll want to hold ```alt``` to show boot picker.

Troubleshoot section will be added later, when some question will apear.

## FAQ

Q: Is it safe to reset NVRAM?

A: I've not tested resetting NVRAM jet, but there is an ```cleannvram.efi``` file which works fine. I have also one comment from NUC user that resseted NVRAM, he couldn't to boot any EFI drives and ability to EFI boot. But ```cleannvram.efi``` works fine.


Q: How to delete Hackintosh from my NUC?

A: Check "How to delete Hackintosh" section in this guide

Q: Is perfomance good at games?

A: NO, perfomance in games is much MUCH worse than on Linux and Windows. You will get 50% less perfomance in games.

## How to delete Hackintosh
You have tried macOS, but you didn't like and want to remove it from your NUC.
All what you will have to do is Update your bios, clean or reset NVRAM, delte bootentries using bootice.exe
Ok, let's start from the stuff

* BIOS update on USB drive
* Windows installation USB drive
* bootice.exe on USB drive

That's what you have to do in order:

* 1 Reboot macOS(don't forget hold alt) picker, press spacebar and select cleanNVRAM or resetNVRAM.
* 2 Boot to your BIOS and update it!
* 3 Boot to Windows USB drive and clean UEFI Entries by bootice.exe
* 4 Install OS

