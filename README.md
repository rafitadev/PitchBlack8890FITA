# PitchBlack Recovery Project - Samsung Exynos 8890 (FITA Edition)

## Introduction
This repository contains the PitchBlack Recovery Project (PBRP) source code and device trees for Samsung Exynos 8890 devices (herolte, hero2lte, gracerlte), based on Android 9.0 (SDK 28).

## Project Status
- **Base**: PBRP 3.x
- **Android Version**: 9.0
- **Developer**: [@RafitaDev](https://github.com/rafitadev)
- **Edition**: FitaDev Special Build

## Credits & Origins
This project is a specialized fork and compilation based on the work of:
* **Original Device Trees**: [ananjaser1211](https://github.com/ananjaser1211/android_device_samsung_hero)
* **Recovery Source**: [PitchBlack Recovery Project](https://github.com/PitchBlackRecoveryProject)

## Supported Devices
* **Samsung Galaxy S7** (herolte)
* **Samsung Galaxy S7 Edge** (hero2lte)
* **Samsung Galaxy Note 7/FE** (gracerlte)

## Custom Modifications (Fita Edition)
- Adjusted `BOARD_RECOVERYIMAGE_PARTITION_SIZE` to 48234496.
- Custom build versioning set to `Fita`.
- Fixed Soong build duplications and Python 2.7 environment issues for modern build hosts.
- Patched Omni/AOSP manifests for legacy compatibility.

## How to Build
```bash
# Initialize the PBRP tree
repo init -u https://github.com/PitchBlackRecoveryProject/manifest_pb.git -b android-9.0

# Sync sources
repo sync -c -j$(nproc --all) --force-sync --no-clone-bundle --no-tags

# Build the recovery
. build/envsetup.sh
lunch omni_<device>-eng
mka p recoveryimage
```

## Disclaimer
While this recovery is tested, use it at your own risk. The developers are not responsible for bricked devices, dead SD cards, or thermonuclear war.
