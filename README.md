# EFI OpenCore Dell Precision 7560 + NullMoth

Ini EFI dari Dell Precision 7560 punyaku, jalan di macOS 26.7.3 dengan driver NullMoth 3.1. Layar laptopnya nyambung ke NVIDIA.

## Spek asli laptopku

| Komponen | Spek asli |
| --- | --- |
| Laptop | Dell Precision 7560 |
| Prosesor | Intel Core i7-11850H, generasi ke-11, 8 core / 16 thread, base 2,50 GHz |
| RAM | 32 GB |
| GPU | NVIDIA RTX A3000 Laptop GPU, VRAM 6 GB; iGPU Intel Tiger Lake (PCI ID `8086:9A60`) |
| Layar internal | 3840 × 2160 (4K UHD), 60 Hz |
| Audio | Realtek ALC289 |
| Penyimpanan macOS | SSD internal 256 GB |

Kalau di **About This Mac** prosesornya kebaca **Intel Xeon W**, jangan bingung, bah. Itu nama yang ditampilkan macOS gara-gara identitas Mac/SMBIOS di OpenCore. CPU fisiknya tetap **Intel Core i7-11850H**; bisa dicek lewat `sysctl -n machdep.cpu.brand_string`.

**Jangan main salin terus langsung boot, bang.** Ini template buat dicocokkan sama laptopmu, bukan EFI yang tinggal pakai. Walaupun sama-sama Precision 7560, isi hardware dan pengaturan BIOS bisa beda.

## Sebelum dicoba

1. Bikin identitas SMBIOS punyamu sendiri, lalu ganti `SystemSerialNumber`, `MLB`, `SystemUUID`, dan `ROM` di `EFI/OC/config.plist`. Yang di repo ini cuma placeholder.
2. Cek lagi ACPI, USB mapping, jalur layar, kext, dan boot arguments. Jangan asal samakan kalau GPU atau komponen laptopmu beda.
3. Simpan EFI yang sudah pasti bisa boot di flashdisk. Kalau konfigurasi baru bikin layar gelap, masih ada jalan baliknya.
4. Install driver NVIDIA [NullMoth](https://github.com/nullmoth/nvidia-macos-driver) **terpisah di macOS**. `NVRM`, `NVRMFB`, `NVAccel`, `NVRMAGDC`, dan `NMXAudio` tidak ikut di repo ini.
5. Kalau pakai Wi-Fi Intel dari `itlwm.kext`, install [HeliPort](https://github.com/OpenIntelWireless/heliport) juga. Nama dan password Wi-Fi sengaja kukosongkan dari EFI ini; sambungkan jaringanmu sendiri lewat HeliPort.

Serial/UUID asli, data Wi-Fi, dan backup `config.plist` dari laptopku sudah dibuang. Jadi jangan cari password Wi-Fi di sini, bah.

## Sumber driver

- [OpenCore](https://github.com/acidanthera/OpenCorePkg)
- [NullMoth NVIDIA driver](https://github.com/nullmoth/nvidia-macos-driver)
- [VoodooPS2](https://github.com/acidanthera/VoodooPS2)
- [OpenIntelWireless itlwm](https://github.com/OpenIntelWireless/itlwm)
- [WhateverXe](https://github.com/b00t0x/WhateverXe)

File bawaan proyek lain tetap ikut lisensi dari pembuatnya. Cek lisensinya kalau mau sebar ulang atau ubah-ubah.
