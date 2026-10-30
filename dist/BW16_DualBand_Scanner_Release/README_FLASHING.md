# Panduan Flashing Firmware BW16 Dual-Band Wi-Fi Analyzer

Dokumen ini adalah panduan lengkap bagi pembeli / pengguna untuk mengunggah (*flashing*) file biner `.bin` ke modul **Ai-Thinker BW16 (RTL8720DN)**.

---

## 1. Persiapan Hardware
1. Modul **Ai-Thinker BW16** (development board atau breakout board).
2. Kabel Micro-USB / USB-C (pastikan kabel data, bukan hanya kabel charger daya).
3. Komputer/Laptop (Windows, Linux, atau macOS).

---

## 2. File Biner Firmware
Paket firmware resmi terdiri dari file:
* **`km0_km4_image2.bin`** *(Wajib)*: Program aplikasi utama BW16 Dual-Band Analyzer (offset alamat: `0x08006000` / `0x08004000` / standard image 2).
* **`km0_boot_all.bin`** *(Opsional / Factory)*: Bootloader Cortex-M0.
* **`km4_boot_all.bin`** *(Opsional / Factory)*: Bootloader Cortex-M33.

---

## 3. Langkah Flashing Menggunakan Image Tool (Windows / Linux)

### Cara Memasukkan BW16 ke Mode Download / Burn:
1. Hubungkan board BW16 ke USB komputer.
2. Tahan tombol **Burn / Boot / Download** (tombol B).
3. Sambil tetap menahan tombol Burn, tekan tombol **RST (Reset)** sekali.
4. Lepaskan tombol Burn.
5. Board sekarang berada di mode **UART Bootloader / Download Mode** (indikator LED hijau padam atau berkedip singkat).

### Flashing via Ameba Image Tool:
1. Unduh dan buka aplikasi **Ameba Image Tool** (disediakan oleh Realtek).
2. Pilih nomor **COM Port** modul BW16 kamu.
3. Atur Baudrate ke **115200** atau **1500000** (1.5M).
4. Klik tab **Download**:
   - Centang **Flash / Image 2**, pilih file `km0_km4_image2.bin`.
   - Jika board dalam kondisi baru/kosong, masukkan juga bootloader `km0_boot_all.bin` dan `km4_boot_all.bin`.
5. Klik tombol **Download** dan tunggu hingga proses mencapai 100%.
6. Setelah selesai, tekan tombol **RST (Reset)** pada BW16.

---

## 4. Cara Menghubungkan & Mengakses Portal
1. Setelah reboot, BW16 akan memancarkan hotspot Wi-Fi:
   - **SSID:** `BW16-Scanner-XXXX` (XXXX adalah 4 digit terakhir MAC)
   - **Password:** Tidak ada (Open Wi-Fi)
2. Sambungkan HP atau Laptop kamu ke hotspot tersebut.
3. Buka browser web (Chrome, Safari, Firefox), lalu buka alamat:
   ```
   http://192.168.1.1
   ```
4. Jika perangkat baru pertama kali dinyalakan, layar **Aktivasi Lisensi** akan muncul:
   - Salin **Device MAC** yang tertera di layar.
   - Kirimkan Device MAC tersebut ke penjual untuk mendapatkan kode aktivasi.
   - Masukkan kode aktivasi dan klik **Aktivasi Sekarang**.
5. Setelah teraktivasi, dashboard **BW16 Dual-Band Wi-Fi Analyzer** akan langsung terbuka dan siap digunakan!
