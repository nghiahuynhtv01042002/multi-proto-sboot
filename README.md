# SECURE BOOTLOADER WITH FIRMWARE UPDATE 

**Everything is still in conceptable and design stage the current idea is preliminary and may be adjusted in the future**

## 1. Firmware verification before transferring control:
The bootloader verifies the firmware integrity (using checksum or digital signature) before jumping to the application.
This ensures the device only runs valid and trusted firmware.
## 2. Firmware update via Multiple protocols (USB FS, SPI, UART):
Supports remote firmware updates via:
    + USB Full-Speed (USB FS)
    + SPI
    + UART

The bootloader validates the received firmware before flashing it.

## 3. Backup and recovery via SD card:
In case of a failed firmware update (e.g., power loss, CRC failure...), the bootloader can:
+ Restore from a backup firmware stored on the SD card.
+ Prevents the device from becoming unbootable (“bricked”).

## 4. Offline update via SD card:
Firmware can be updated from a local SD card, without the need for OTA or communication links.
Integrity is verified before applying the update.