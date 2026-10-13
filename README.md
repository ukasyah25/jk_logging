# JK Trip Logger

Catat **Ah terpakai**, **jarak (km)**, **Ah/km** dan **Wh/km** dari JK-BMS (Bluetooth) dan GPS HP. Berjalan di browser, tanpa server dan tanpa hardware tambahan.

## Deploy ke GitHub Pages
1. Buat repo baru di GitHub, unggah semua file ini (termasuk folder `.github`).
2. Buka **Settings → Pages → Source: GitHub Actions**.
3. Push ke branch `main`. Alamat aplikasi: `https://USERNAME.github.io/NAMA-REPO/`.

## Cara pakai
1. Buka alamat di **Chrome Android** (Web Bluetooth tidak ada di iOS/Firefox).
2. Nyalakan Bluetooth dan GPS. Tutup app JK-BMS agar slot BLE bebas.
3. Tekan **Sambung ke BMS**, pilih perangkat JK.
4. Tekan **Mulai perjalanan** sebelum jalan, **Selesai** saat berhenti.
5. Riwayat tersimpan di HP; log detail bisa diunduh sebagai CSV.

## Catatan
- Layar harus tetap menyala dan Chrome di depan; browser menghentikan GPS dan BLE di latar belakang. Aplikasi meminta *wake lock* otomatis.
- **Ah terpakai** dihitung dari integrasi arus (net, regen mengurangi). Nilai dari selisih kapasitas BMS ditampilkan sebagai pembanding.
- Posisi data di frame BMS bisa berbeda antar firmware. Jika Volt/Amp/SOC tampak salah, ganti **Format frame BMS** ke 24S atau 32S secara manual.
- Tegangan, arus, dan SOC di BMS dibaca dari protokol JK02 (service `FFE0`, karakteristik `FFE1`).
