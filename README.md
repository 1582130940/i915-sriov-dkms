# Linux i915 driver with SR-IOV support (dkms module)

Originally from [linux-intel-lts](https://github.com/intel/linux-intel-lts/tree/lts-v5.15.71-adl-linux-221121T044440Z/drivers/gpu/drm/i915)

## Notice

This package is **highly experimental**, you should only use it when you know what you are doing.

You need to install this dkms module in **both host and VM!**

For Arch Linux users, it is available in AUR. [i915-sriov-dkms-git](https://aur.archlinux.org/packages/i915-sriov-dkms-git)

Latest tested kernel version on Arch Linux: `6.0.9-arch1-1`

Tested usages:

- VA-API video acceleration in VM (need to remove any other display device such as virtio-gpu)

## My testing cmdline

```
intel_iommu=on i915.enable_guc=7
```

## Creating virtual functions

```
echo 2 > /sys/devices/pci0000:00/0000:00:02.0/sriov_numvfs
```

You can create up to 7 VFs on UHD Graphics 770
