# Dell Precision 7560 OpenCore EFI

OpenCore configuration for a Dell Precision 7560 running macOS 26 with an NVIDIA RTX A3000 and NullMoth 3.1. This is a **public template**, not a ready-to-boot personal EFI.

## Before using it

1. Generate your own SMBIOS `SystemSerialNumber`, `MLB`, `SystemUUID`, and `ROM`, then replace the placeholders in `EFI/OC/config.plist`.
2. Add your own Wi-Fi networks through HeliPort. The `itlwm.kext` `WiFiConfig` in this repository is empty to keep network names and passwords private.
3. Review the ACPI files, device properties, kexts, and boot arguments for your exact hardware. Keep a known-working USB recovery EFI before testing changes.

The working machine's private identifiers and saved Wi-Fi credentials are not included. Historical `config.plist` backups are also excluded.

## Upstream projects

- [OpenCore](https://github.com/acidanthera/OpenCorePkg)
- [NullMoth NVIDIA driver and 1401](https://github.com/nullmoth/nvidia-macos-driver)
- [VoodooPS2](https://github.com/acidanthera/VoodooPS2)
- [OpenIntelWireless itlwm and HeliPort](https://github.com/OpenIntelWireless/itlwm)
- [WhateverXe](https://github.com/b00t0x/WhateverXe)

Each included binary remains under its upstream license. Check upstream license terms before redistributing or adapting these files.
