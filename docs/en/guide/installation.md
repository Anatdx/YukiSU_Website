# Installation Guide

::: details What you will learn about YukiSU installation
[[toc]]
:::

::: danger Warning
**Rooting your device can void your warranty and may cause permanent damage if done incorrectly.**
Always create a full backup before proceeding, read the documentation to ensure compatibility with your device, follow the documentation, and have a recovery plan ready.
:::

Please refer **entirely** to the [KernelSU Installation Guide](https://kernelsu.org/guide/installation.html)

## Getting Started

### Universal GKI Installation

::: tip
For GKI 2.0 devices like Xiaomi, Redmi, Samsung, etc. (excluding manufacturers with kernel modifications like Meizu, OnePlus, Realme, and OPPO)
:::

#### Steps

1. Download GKI build files

   Not provided yet, sorry, use LKM instead, or build GKI yourself

2. Flash via Recovery

   Boot into `TWRP recovery`, select **Install**, navigate to the downloaded `AnyKernel3 zip` file, swipe to flash and reboot

3. [Verify Installation](#verification)

::: details File Format Guide
The `.zip` archive without a suffix is uncompressed. The `.gz` suffix is a compressed format used for specific models.
:::

### OnePlus Device Installation

1. Gather device information

- Kernel version (first two parts, e.g., `5.10`, `5.15`, `6.1`, `6.6`)
- Processor codename (usually English without numbers)
- Branch and configuration files from OnePlus open-source kernel repository

2. Create custom build

   Find any repository that can build SukiSU kernel for your device, and replace the repository link with mine

3. Flash the build

   Download the generated zip file with AnyKernel3 suffix, boot into `TWRP recovery`, select **Install**, navigate to the downloaded `AnyKernel3 zip` file, swipe to flash and reboot. For phones without TWRP or if you don't want to use recovery, first flash an LKM, or Magisk, APatch, whatever, then grant root permission to the manager, click direct install and use `Flash AnyKernel3`

::: tip
You only need the first two parts of the kernel version. Search for your processor codename yourself.
:::

::: warning Required Kernel Configuration
For KPM support, add `CONFIG_KPM=y`

For non-GKI devices, also add `CONFIG_KALLSYMS=y` and `CONFIG_KALLSYMS_ALL=y`
:::

## Post-Installation Setup

### Maintaining Root After System Updates

> [!IMPORTANT]
> How to maintain root access after OTA updates:

#### Steps

1. Before rebooting after system update

   - Don't reboot immediately after OTA installation, install YukiSU to the second slot
   - Open YukiSU Manager, in the **Flash/Patch Kernel** interface select **GKI/non_GKI install**, select your `AnyKernel3` kernel `zip` file, select the slot opposite to the currently running slot and flash then reboot. Who taught you to update this way? Use LKM as a transition, otherwise who are you going to complain to when it crashes?

2. Alternative: LKM Mode

   Use [LKM mode](#universal-gki-installation) to install to the unused slot after OTA.

::: warning Warning
**Note for non-GKI devices:** This method doesn't support all non-GKI devices. For non-GKI devices, using TWRP is the safest method.
:::

## Verification

After installation, verify everything is working properly:

- Open YukiSU Manager to check root working status
- Use apps that require root to verify root access is working
- Check kernel version in Settings -> About Phone

## Need Help?

If you encounter issues during installation:

1. Check our [Compatibility Guide](./compatibility) for device requirements
2. Visit our [GitHub repository](https://github.com/Anatdx/YukiSU) for support
3. Join our [Telegram community](https://t.me/hymo_chat) for help

::: danger Safety Reminder
**Always have a backup plan!** Keep your original `boot.img/init_boot.img` and know how to recover your device if something goes wrong.
:::
:::
