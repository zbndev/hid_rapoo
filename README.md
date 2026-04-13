# hid_rapoo

Battery reporting for Rapoo Gaming Mouses

Tested on Arch Linux and Fedora Linux 43.

## Supported Devices

| Device        | USB ID (VID:PID) |
| ------------- | ---------------- |
| VT3 Pro       | 24ae:1215        |
| VT3 Pro Max   | 24ae:1244        |
| VT3 Max Gen-2 | 24ae:3102        |
| VT9 Pro       | 24ae:1417        |
| VT9 Pro Mini  | 24ae:3103        |

## Prerequisites

Install kernel headers and DKMS:

**Fedora/RHEL:**

```bash
sudo dnf install kernel-devel kernel-headers dkms
```

**Ubuntu/Debian:**

```bash
sudo apt install linux-headers-$(uname -r) dkms
```

**Arch:**

```bash
sudo pacman -S linux-headers dkms
```

## Installation (Recommended - DKMS)

DKMS will automatically rebuild and load the module after kernel updates and on boot.

```bash
sudo ./install-dkms.sh
```

To verify installation:

```bash
lsmod | grep hid_rapoo
modinfo hid_rapoo
```

## Uninstalling (DKMS)

```bash
sudo ./uninstall-dkms.sh
```

## Manual Installation (Temporary)

If you want to build and test without DKMS:

```bash
make
sudo insmod hid_rapoo.ko
```

To remove:

```bash
sudo rmmod hid_rapoo
```
