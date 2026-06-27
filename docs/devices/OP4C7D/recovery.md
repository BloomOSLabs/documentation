# Recovery

BloomOS uses a custom recovery for installation and maintenance.

## Booting Recovery

Use the following command from Fastboot mode.

```bash
fastboot reboot recovery
```

Alternatively, use the hardware key combination for your device.

---

## Available Functions

Recovery supports:

* Factory Reset
* Apply Update from ADB
* Reboot System
* Advanced Recovery Options

---

## Updating Recovery

Recovery updates are distributed alongside official BloomOS releases when required.

Unless specifically instructed, flashing recovery separately is not necessary.

---

## Troubleshooting

If recovery fails to boot:

* Verify the correct boot image is installed.
* Verify the correct vbmeta image has been flashed.
* Reflash the latest recovery supplied with the current release.
