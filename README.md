# OpenCore untuk Dell Precision 7560

Konfigurasi EFI ini digunakan pada Dell Precision 7560 dengan macOS Tahoe 26.7.3 (build `25G342`). Akselerasi grafis NVIDIA menggunakan NullMoth 3.1. Layar internal terhubung ke GPU NVIDIA.

## Spesifikasi perangkat

| Komponen | Spesifikasi |
| --- | --- |
| Model | Dell Precision 7560 |
| Prosesor | Intel Core i7-11850H, generasi ke-11, 8 core / 16 thread, frekuensi dasar 2,50 GHz |
| Memori | 32 GB |
| GPU diskret | NVIDIA RTX A3000 Laptop GPU, VRAM 6 GB |
| GPU terintegrasi | Intel Tiger Lake, PCI ID `8086:9A60` |
| Layar internal | 3840 × 2160, 60 Hz |
| Wi-Fi dan Bluetooth | Intel AX210 (`8086:2725`), Bluetooth `8087:0032` |
| Audio | Realtek ALC289 |
| Penyimpanan macOS | SSD internal 256 GB |

macOS menampilkan nama prosesor Intel Xeon W karena identitas Mac (SMBIOS) yang digunakan oleh OpenCore. Prosesor fisik perangkat ini adalah Intel Core i7-11850H. Identitas prosesor dapat diperiksa dengan `sysctl -n machdep.cpu.brand_string`.

## Status konfigurasi

- Wi-Fi menggunakan [ForbiddenItlwm 0.7.0-alpha.2](https://github.com/retropineaple/ForbiddenItlwm), sehingga terhubung melalui menu Wi-Fi bawaan macOS. HeliPort tidak diperlukan untuk konfigurasi ini.
- AirDrop telah diuji dengan iPhone, termasuk penerimaan berkas dari iPhone ke laptop.
- Bluetooth menggunakan IntelBluetoothFirmware, BlueToolFixup, dan BTLEAdvFixup 0.9.6. `IntelBTPatcher.kext` dinonaktifkan sesuai persyaratan BTLEAdvFixup.
- `itlwm.kext` lama tetap tersedia di EFI sebagai cadangan, tetapi dinonaktifkan. Jangan mengaktifkannya bersamaan dengan ForbiddenItlwm.
- Driver NVIDIA NullMoth dan komponen audionya dipasang secara terpisah di macOS; komponen tersebut tidak disertakan dalam repositori ini.

ForbiddenItlwm masih dalam tahap pengembangan. Dukungan AirDrop bergantung pada versi macOS, versi driver, dan perangkat Wi-Fi. Konfigurasi di repositori ini telah digunakan pada perangkat yang spesifikasinya tercantum di atas; hasil pada perangkat lain dapat berbeda.

## Persiapan sebelum digunakan

1. Buat identitas SMBIOS sendiri, lalu isi `SystemSerialNumber`, `MLB`, `SystemUUID`, dan `ROM` pada `EFI/OC/config.plist`. Nilai dalam repositori ini adalah placeholder.
2. Cocokkan pengaturan BIOS, ACPI, pemetaan USB, jalur layar, dan perangkat keras dengan laptop yang akan digunakan.
3. Simpan EFI yang sudah dapat digunakan pada USB bootable sebelum mengganti EFI internal.
4. Pasang [driver NVIDIA NullMoth](https://github.com/nullmoth/nvidia-macos-driver) secara terpisah jika menggunakan GPU NVIDIA. `NVRM`, `NVRMFB`, `NVAccel`, `NVRMAGDC`, dan `NMXAudio` tidak disertakan di sini.
5. Periksa [persyaratan ForbiddenItlwm](https://github.com/retropineaple/ForbiddenItlwm/blob/main/docs/INSTALL.md) sebelum memperbarui macOS atau mengganti driver Wi-Fi. Build driver dalam repositori ini ditujukan untuk macOS Tahoe 26.7.3.

Nomor seri, UUID, alamat ROM, dan kredensial Wi-Fi milik perangkat asli telah dihapus dari versi publik.

## Proyek terkait

- [OpenCore](https://github.com/acidanthera/OpenCorePkg)
- [NullMoth NVIDIA driver](https://github.com/nullmoth/nvidia-macos-driver)
- [ForbiddenItlwm](https://github.com/retropineaple/ForbiddenItlwm)
- [OpenIntelWireless](https://github.com/OpenIntelWireless)
- [WhateverXe](https://github.com/b00t0x/WhateverXe)

Berkas dari proyek lain tetap mengikuti lisensi masing-masing pemiliknya.
