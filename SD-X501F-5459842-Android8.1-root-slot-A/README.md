# SD-X501F Android Things 8.1 rooted firmware for slot A

This experimental package targets the Lenovo Smart Display M10 ZA4T0001JP / SD-X501F. It is based on Android Things 8.1.0 (API 27), build 5459842. The rooted system and vendor images were modified for the [LANovo](https://github.com/ygelfand/LANovo/) installer. Image names end in `_a` to identify the target slot.

## Contents and limitations

The 14 slot A images are listed with sizes and SHA-256 hashes in `manifest.json` and `SHA256SUMS.txt`. This package includes boot, system, vendor, vbmeta, modem, Bluetooth, DSP, OEM and boot-chain images. It excludes slot B, GPT, userdata, factory, persist, DRM and keymaster; it is not a complete eMMC backup. The system image was cleaned of old LANovo traces, embedded ADB keys and the property enabling ADB TCP port 5555. Camera and audio components remain in the images.

The included `vbmeta_a.img` was not re-signed for the modified system. Use only on a compatible, appropriately unlocked SD-X501F; do not relock with custom firmware installed. Keep a device-specific recovery backup.

## Verify and flash on Windows

1. Extract the archive and verify all 14 images without connecting a device:

   ```powershell
   .\flash-all.bat --verify-only
   ```

2. Install Python 3.11 or later, the Qualcomm HS-USB QDLoader 9008 driver, and pyserial:

   ```powershell
   python -m pip install pyserial
   ```

3. Confirm the physical model, enter EDL 9008 mode, and identify the COM port in Device Manager. Use a new or empty backup directory with sufficient free space. The script checks image hashes, GPT and partition sizes, backs up target partitions before writing, and verifies readback.

   ```powershell
   .\flash-all.bat --port COM12 --backup-dir "D:\X501F-backup-before-flash"
   ```

4. After flashing, enter fastboot and select slot A:

   ```powershell
   fastboot devices
   fastboot -s SERIAL set_active a
   fastboot -s SERIAL reboot
   ```

The latest package is version 1.1. Its refreshed checksums match all 14 images; run `--verify-only` after extraction before flashing.
