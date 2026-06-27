---

title: Installing BloomOS on OPPO A31
description: Official installation instructions for the OPPO A31 (OP4C7D).
author: Stanly Silas
updated: 2026-06-27
-------------------

# Installing BloomOS on OPPO A31 (OP4C7D)

> [!WARNING]
> Installing custom software modifies your device's operating system. Proceed only if you understand the installation process and have backed up all important data. BloomOS developers and maintainers are not responsible for data loss, boot loops, unbootable devices or any other damage resulting from incorrect installation.

## Overview

This guide explains how to install BloomOS on the **OPPO A31 (OP4C7D)**.

Please read the entire guide before beginning. Skipping steps or flashing incorrect files may prevent your device from booting.

---

## Prerequisites

Before continuing, ensure that all of the following requirements have been completed.

* ✅ Bootloader unlocked
* ✅ Platform Tools (ADB & Fastboot) installed
* ✅ Latest BloomOS package downloaded
* ✅ Permissive boot image downloaded
* ✅ Disabled vbmeta image downloaded
* ✅ USB cable available
* ✅ Battery charged to at least 50%
* ✅ Backup of all important personal data

If your bootloader is still locked, complete the Bootloader Unlock Guide before continuing.

---

## Downloads

Download the latest release for **OP4C7D** from the official BloomOS Downloads page.

Required files:

* BloomOS ROM
* Permissive boot image
* Disabled vbmeta image

---

## Boot into Fastboot Mode

1. Power off the device.
2. Boot into Fastboot Mode.
3. Connect the device to your computer.
4. Verify the connection.

```bash
fastboot devices
```

Your device serial number should be displayed.

---

## Flash Disabled vbmeta

Flash the supplied disabled vbmeta image.

```bash
fastboot --disable-verity --disable-verification flash vbmeta vbmeta.img
```

This disables Android Verified Boot so the custom operating system can boot correctly.

---

## Flash the Permissive Boot Image

Flash the boot image included with the release.

```bash
fastboot flash boot boot.img
```

This boot image enables permissive SELinux, which is currently required for BloomOS on this device.

---

## Reboot into Recovery

Boot directly into the recovery image.

```bash
fastboot reboot recovery
```

Do not boot into Android before completing the installation.

---

## Factory Reset

Inside recovery:

1. Select **Factory Reset**
2. Format Data / Factory Reset
3. Return to the main menu

This removes encryption and prepares the device for installation.

---

## Sideload BloomOS

Choose:

**Apply Update → Apply from ADB**

Then execute:

```bash
adb sideload BloomOS.zip
```

Wait until installation completes successfully.

---

## First Boot

Once installation finishes:

1. Return to the main menu.
2. Reboot the device.

The first boot may take between **5 and 10 minutes**.

Do not interrupt the boot process.

---

## Updating BloomOS

Future releases can be installed using the built-in OTA Updater when available.

Manual installation packages may also be flashed using the same procedure described above unless otherwise noted in the release notes.

---

## Troubleshooting

### Device not detected

Verify Fastboot connectivity.

```bash
fastboot devices
```

or

```bash
adb devices
```

depending on the current boot mode.

---

### Boot loop

Ensure that:

* the correct ROM package was used
* the supplied permissive boot image was flashed
* the supplied disabled vbmeta image was flashed
* a factory reset was performed before installation

---

### Installation failed

Verify that:

* the downloaded files are not corrupted
* the device codename is **OP4C7D**
* the installation steps were followed exactly

---

## Frequently Asked Questions

### Will this erase my data?

Yes.

Unlocking the bootloader and performing a factory reset erases all user data.

---

### Will my warranty be affected?

Unlocking the bootloader may void your warranty depending on your region and manufacturer policies.

---

### Can I return to stock firmware?

Yes.

You can return to the original firmware by flashing the official stock images using the manufacturer's flashing tools.

---

## Need Help?

If you encounter issues not covered in this guide:

* Open an issue on GitHub.
* Contact the device maintainer.
* Join the BloomOS Telegram community for support.
