---
permalink: /Chromebook-ISO-Linux
title: "Chromebook Recovery Utility Linux ISO Guide"
layout: single
---

# Requirements
- [Chromebook Recovery Utility Extension](https://chromewebstore.google.com/detail/chromebook-recovery-utili/pocpnlppkickgojjlmhdmidojbmbodfm)
- Flash drive (refer to distrobution for size requirement)
- Linux ISO with isohybrid support

# What is isohybrid
Most Linux distributions are released in `.ISO` format these files were originally made for burning to optical discs. As flash drives grew in popularity in comparison to discs, distros needed to adapt to this so they adopted “isohybrid”. isohybrid modified ISO files that were created for discs to also support flash drives. If the distro says that you can just use the `dd` command then it will certainly be a isohybrid file. If this method doesn’t work for a partiucular distro I would suggest trying another.

Microsoft Windows ISOs are not set up in isohybrid mode. For Windows I would recommend using Ventoy. You can download the Ventoy LiveCD iso which is isohybrid. Once you install Ventoy to flash drive then you can add your Windows ISO to the Ventoy.

## 1. Renaming ISO
For the Chromebook Recovery Utility to be able to select this file we will need to change the file extension.
- Right click the file and choose the rename option.
- Go to the end of the file and add to the end `.bin`

Example `ubuntu-22.04.4-desktop-amd64.iso` becomes `ubuntu-22.04.4-desktop-amd64.iso.bin`

## 2. Use Chromebook Recovery Utility
- Choose the puzzle piece icon at the top of Chrome then choose Chromebook Recovery Utility (CRU) from the list
- Click the gear icon
- Click `Use local image`
- Choose the flash drive you want to **ERASE** and put Linux on.
- Click Continue
- Click Create now