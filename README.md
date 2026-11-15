# Lenovo SD-X501F firmware archive

Firmware collected from a Lenovo Smart Display M10 (ZA4T0001JP / SD-X501F), prepared for the [LANovo project](https://github.com/ygelfand/LANovo/) and the discussion in [libcountertop PR #12](https://github.com/ygelfand/libcountertop/pull/12).

## Packages

- **SD-X501F-original-backup**: EDL 9008 partition backup from an unrooted device whose bootloader had not been unlocked. Slot A contains Android 7 `userdebug`; slot B contains Android 8.1 `user`. The release package excludes userdata, persist, DRM and keymaster. This is a selection of partition images, not a complete eMMC image. The remaining images have not been independently audited for device-specific information.
- **SD-X501F-5459842-Android8.1-root-slot-A**: Modified, rooted Android Things 8.1.0 (API 27), build 5459842, prepared for `lanovo install`. See the package README for its contents and flashing instructions.

Download the ZIP archives and SHA-256 checksums from the [latest release](https://github.com/daivietpda/SD-X501F-firmware/releases/latest). The archives are release assets and are not stored in Git.

## Current LANovo test

The owner installed a recent LANovo development build using `lanovo install`. Microphone input and touch work; screen orientation and the displayed microphone mute and camera shutter states are correct. Speaker output is silent and the camera image is rotated incorrectly. These observations are specific to the tested setup.
