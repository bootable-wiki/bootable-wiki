---
permalink: /iOS-UEFI-Ventoy
title: "iOS Ventoy Guide"
layout: single
---
# Requirements
- UEFI motherboard.
    - UEFI was a requirement to get OEM volume discount for Windows 8. So all computers that had Windows were produced after 2012 it should be assumed that the motherboard firmware should support UEFI, even if the machine was shipped with Windows 7.
- 256 megabyte (not gigabyte) or larger USB flash drive formatted as FAT32.
- USB-C iOS device such as iPhone 15 or newer ***OR*** a lightning iOS device and an adapter such as [USB 3 Camera Adapter](https://www.apple.com/shop/product/MK0W2AM/A/lightning-to-usb-3-camera-adapter).

## 1. Check if the USB format is FAT32 with Files app.
For UEFI booting the file system needs to be supported by the motherboard. The most commonly supported file system is [FAT32](https://en.wikipedia.org/wiki/File_Allocation_Table#FAT32). On Apple platforms FAT32 is labled as "MS-DOS (FAT)"
Steps
- Open the Files app
- Tap on Browse
- Press and hold on your USB flash drive
- Tap on "Get Info"
- Read the "Format" line and see that it is "MS-DOS (FAT)"

If the format is not "MS-DOS (FAT)" then you cannot use the iOS device to erase & set the format to FAT32. I would suggest trying another flash drive as the default filesystem of flash drives is most often FAT32. If you have no flash drives that are formatted as FAT32, I would suggest buying a new flash drive from a reputable brand such as SanDisk or Samsung. I would not recommend drives with lightning connector built in as they will usually require that you use their specific app.

## 2. Download Ventoy Bootable zip file
The iPhone cannot extract ISO files without 3rd party apps. The Ventoy Live CD ISO has been repacked into a zip file with secure boot support. [ Download `Ventoy_Bootable.zip`](https://pixeldrain.com/api/file/rZHHGJgQ)

- Open the Files app
- Open the downloads folder
- Tap & hold on the zip file
- Tap on uncompress
- Open the folder
- Tap the 3 dots in upper right corner
- Tap Select
- Tap the EFI folder & the ENROLL.cer file
- Tap the share icon in the bottom left folder
- Choose the copy option
- Navigate to the USB flash drive
- Tap & hold in the blank area
- Choose paste
- Unplug drive 

## 3. Convert to Ventoy disk

- Plug the flash drive into a PC
- Get into the boot menu or "bios" setup & choose the flash drive to start the computer with
- If prompted with `Verification Failed Security Violation` enroll the Ventoy key into secure boot. [Tutorial](https://www.ventoy.net/en/doc_secure.html) then reboot the computer & select flash drive again.
- Choose the "Ventoy Installer" option
- Select the flash drive, the program will show brand & size information to make sure you choose the right drive, as it erases the all contents & formats as [exFAT](https://en.wikipedia.org/wiki/ExFAT)
    - You can install Ventoy to the flash drive you booted the computer with or any other flash drive you plug in.
- When you see `Ventoy has been successfully installed to the device.` you can unplug the flash drive and plug back into the iPhone
- You can now download a Linux distro or [Windows ISO](https://duckduckgo.com/?q=Download+Windows+ISO) & copy to the newly made Ventoy disk.

--- 
Last updated on 2024-Mar-06