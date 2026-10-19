# Aplikasi Android "Tempe Monitor"

Aplikasi Android (APK) untuk memantau dan mengontrol fermentasi tempe. Server: Firebase Realtime Database (gratis).
Pasangannya adalah firmware ESP32 di `tempe_fermentasi_proyek.zip` (struktur data sama: `/tempe/status`, `/tempe/histori`, `/tempe/kontrol`).

## Cara mendapatkan APK (gratis, tanpa install Android Studio)
1. Buat akun GitHub, lalu buat repository baru (boleh private).
2. Upload SEMUA isi folder ini ke repository, termasuk folder tersembunyi `.github` (di web GitHub: Add file → Upload files, seret semua file dan folder).
3. Buka tab **Actions** → workflow **Build APK** (jalan otomatis setelah upload; atau klik *Run workflow*). Tunggu ±5–8 menit.
4. Buka run yang sukses → bagian **Artifacts** → unduh **TempeMonitor-APK** (zip berisi `app-debug.apk`).
5. Salin APK ke HP, buka, izinkan "install dari sumber tidak dikenal", lalu install.

## Pertama kali dipakai
Ketuk ikon ⚙︎, isi host database Firebase (sama dengan `FIREBASE_HOST` di `config.h` ESP32), lalu Simpan. Tidak perlu build ulang untuk mengganti server.

## Fitur
- Suhu, kelembapan, fase tempe (decision tree), warna sensor, lama fermentasi
- Status heater / humidifier / kipas, indikator ESP32 online/offline
- Mode Otomatis (Fuzzy Mamdani) atau Manual, dengan tombol per aktuator
- Grafik 200 data terakhir

## Batasan
- Aplikasi memperbarui data tiap 3 detik hanya saat terbuka. Belum ada notifikasi saat aplikasi ditutup (butuh Firebase Cloud Messaging; bisa ditambahkan).
- Aturan database di panduan firmware terbuka untuk uji coba. Untuk pemakaian sungguhan, amankan dulu.
- APK yang dihasilkan adalah versi debug, cukup untuk dipakai pribadi tetapi tidak untuk Play Store.
