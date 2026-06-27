---

title: Installation
description: General installation workflow for BloomOS.
-------------------------------------------------------

# Installation

This guide describes the general installation workflow used by all officially supported BloomOS devices.

> [!IMPORTANT]
> Device-specific installation instructions always take precedence over this guide.

## Typical Installation Process

Although every device differs, the installation process usually follows these steps:

1. Unlock the bootloader.
2. Download the required files.
3. Boot into Fastboot or Recovery.
4. Flash any required boot or vbmeta images.
5. Factory reset the device.
6. Install BloomOS.
7. Reboot and complete the Android setup.

## Device Documentation

Every supported device has its own installation guide.

See:

```
docs/devices/<codename>/installation.md
```

## Troubleshooting

If installation fails:

* Verify that the correct files were downloaded.
* Ensure the device codename matches the documentation.
* Follow every installation step exactly as documented.
