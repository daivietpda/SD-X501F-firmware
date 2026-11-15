# Lenovo SD-X501F firmware archive

Firmware for the Lenovo Smart Display M10 (ZA4T0001JP / SD-X501F), prepared for [LANovo](https://github.com/ygelfand/LANovo/) and [libcountertop PR #12](https://github.com/ygelfand/libcountertop/pull/12).

## Packages

- **Original backup:** EDL 9008 partition backup from an unrooted device with a locked bootloader. Slot A is Android 7 `userdebug`; slot B is Android 8.1 `user`. The release excludes userdata, persist, DRM and keymaster. This is not a full eMMC image.
- **Rooted slot A package:** Modified Android Things 8.1.0 (API 27), build 5459842, prepared for `lanovo install`. See the package README for verification and flashing instructions.

Download the archives and SHA-256 checksums from the [latest release](https://github.com/daivietpda/SD-X501F-firmware/releases/latest). Firmware binaries are distributed as release assets.

The current test build has working touch and microphone input. The screen orientation and microphone mute/camera shutter button indicators are correct; speaker output is silent and the camera preview is rotated incorrectly. Results are specific to the tested device and build.
