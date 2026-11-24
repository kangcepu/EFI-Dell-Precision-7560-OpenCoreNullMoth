# Dell Precision 7560 OpenCore EFI

OpenCore configuration from a Dell Precision 7560 with an Intel Core i7-11850H, NVIDIA RTX A3000 Laptop GPU (6 GB), and macOS 26.7.3. The source machine uses NullMoth 3.1 and has its internal panel connected to the NVIDIA GPU. This is a **public template**, not a ready-to-boot personal EFI.

**Do not copy this EFI and boot it unchanged.** The included SMBIOS values are placeholders. ACPI, USB mapping, display routing, Wi-Fi, and boot arguments may differ even between Precision 7560 units.

## Before using it

1. Generate your own SMBIOS `SystemSerialNumber`, `MLB`, `SystemUUID`, and `ROM`, then replace the placeholders in `EFI/OC/config.plist`.
2. Add your own Wi-Fi networks through HeliPort. The `itlwm.kext` `WiFiConfig` in this repository is empty to keep network names and passwords private.
3. Review the ACPI files, device properties, kexts, and boot arguments for your exact hardware. Keep a known-working USB recovery EFI before testing changes.
4. Install the NullMoth NVIDIA driver separately inside macOS. Its `NVRM`, `NVRMFB`, `NVAccel`, `NVRMAGDC`, and `NMXAudio` components are **not** in this EFI repository.
5. Install HeliPort separately if using the included Intel `itlwm.kext` for Wi-Fi.

The working machine's private identifiers and saved Wi-Fi credentials are not included. Historical `config.plist` backups are also excluded.

## Upstream projects

- [OpenCore](https://github.com/acidanthera/OpenCorePkg)
- [NullMoth NVIDIA driver and 1401](https://github.com/nullmoth/nvidia-macos-driver)
- [VoodooPS2](https://github.com/acidanthera/VoodooPS2)
- [OpenIntelWireless itlwm and HeliPort](https://github.com/OpenIntelWireless/itlwm)
- [WhateverXe](https://github.com/b00t0x/WhateverXe)

Each included binary remains under its upstream license. Check upstream license terms before redistributing or adapting these files.
