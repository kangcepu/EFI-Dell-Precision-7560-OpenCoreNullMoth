# EFI OpenCore Dell Precision 7560 + NullMoth

Ini EFI dari Dell Precision 7560 punyaku: Intel Core i7-11850H, NVIDIA RTX A3000 Laptop GPU 6 GB, macOS 26.7.3, dan driver NullMoth 3.1. Layar laptopnya nyambung ke NVIDIA.

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
