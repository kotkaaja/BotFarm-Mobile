# BotFarm Mobile v1.0.2
**Auto Farm Job Routes System untuk SA-MP**

Script otomatisasi untuk SA-MP yang memungkinkan perekaman dan pemutaran rute pekerjaan dengan sistem profil yang dapat dikonfigurasi.

## 📋 Fitur Utama

### 🚶‍♂️ Sistem Rute Jalan Kaki
- Perekaman rute otomatis berdasarkan waktu
- Perekaman rute manual (titik per titik)
- Format penyimpanan JSON dengan dukungan sprint/walk
- Deteksi stuck otomatis dengan recovery

### 🚗 Sistem Rute Kendaraan
- Perekaman rute kendaraan real-time
- Autopilot dengan kontrol kecepatan
- Format penyimpanan TXT
- Deteksi keluar kendaraan otomatis

### 📊 Sistem Profil
- Multiple profil dengan nama custom
- Step-by-step execution
- Loop mode untuk pengulangan otomatis
- Action system (Key press & Chat commands)

### ⚡ Aksi Otomatis
- **Key Actions**: Y/N, F (Enter Car), H (Horn), Space, Alt
- **Chat Actions**: Pesan/command otomatis dengan pengulangan
- **Cooldown System**: Jeda waktu antar aksi dapat diatur
- **Count System**: Eksekusi berulang untuk setiap aksi

## 🛠️ Persyaratan Sistem

### Library yang Diperlukan
```
lib/moonloader.lua
lib/sampfuncs.lua
lib/samp/events.lua
mimgui.lua
encoding.lua
dkjson.lua
ffi.lua
socket/http.lua
```

### Direktori Installation
```
📁 client direktori temapt monet kalian/
├── 📁 monetloader/
│   └── 📄 BotFarm Mobile.luac
|   └── 📁 Botfarm/
│       ├── 📁 routes/
│       │   ├── 📄 *.json (Walking routes)
│       │   └── 📄 *.txt (Vehicle routes)
│       ├── 📄 profiles.json
|       └── 📄 license_token.txt
```

## 📦 Instalasi

1. **Persiapan Environment**
   - Pastikan MoonLoader sudah terinstall
   - Verifikasi semua library tersedia

2. **Download & Extract**
   - Download file `BotFarm Mobile.lua`
   - Letakkan di folder `moonloader/`

3. **Struktur Folder**
   - Script akan otomatis membuat folder `Botfarm/` dan `routes/`
   - Tidak perlu membuat manual

4. **Aktivasi**
   - Jalankan SA-MP dan masuk ke server
   - Ketik `/js` untuk membuka panel aktivasi
   - Masukkan token yang valid

## 🎮 Penggunaan

### Perintah Dasar
- `/js` - Buka/tutup panel utama
- `/jhelp` - Buka panel bantuan

### Perekaman Rute

#### 🚶‍♂️ Jalan Kaki
1. **Mode Otomatis**: 
   - Aktifkan "Mode Rekam Jalan Kaki Otomatis"
   - Atur interval waktu (default: 3 detik)
   - Mulai berjalan, titik akan terekam otomatis

2. **Mode Manual**:
   - Nonaktifkan mode otomatis
   - Gunakan tombol "Tambah Titik Manual" di setiap lokasi

#### 🚗 Kendaraan
1. Masuk ke kendaraan
2. Input nama rute
3. Klik "Rekam Kendaraan"
4. Berkendara mengikuti rute yang diinginkan
5. Klik "Stop Rekam Kendaraan"

### Pembuatan Profil
1. Buka "Editor" dari panel utama
2. Klik "Buat Profil Baru"
3. Tambahkan step dengan "Step Baru"
4. Konfigurasikan untuk setiap step:
   - **Nama Step**: Deskripsi step
   - **Route**: Pilih rute yang telah direkam
   - **Action**: Konfigurasikan aksi (Key/Chat/None)

### Menjalankan Bot
1. Pilih profil dari dropdown
2. Aktifkan "Ulangi Job (Loop)" jika diperlukan
3. Klik "Start Job"
4. Gunakan "Pause/Resume" untuk kontrol
5. "Stop" untuk menghentikan

## ⚙️ Konfigurasi

### Pengaturan Perekaman
- **Jalan Kaki**: Interval waktu rekam (500-10000ms)
- **Kendaraan**: Jarak minimal (5-50m), Waktu maksimal (500-5000ms)

### Pengaturan Playback
- **Kecepatan Kendaraan**: 5-100 (semakin tinggi semakin cepat)
- **Deteksi Stuck**: Otomatis dengan recovery

### Format File

#### Walking Route (.json)
```json
{
  "points": [
    [x, y, z, 11, -255, true],
    [x, y, z, 11, -255, false]
  ],
  "waitTime": 500
}
```

#### Vehicle Route (.txt)
```
1,2488.56,-1665.78,13.34
2,2495.23,-1670.45,13.34
3,2502.11,-1675.89,13.34
```

## 🔧 Troubleshooting

### Masalah Umum
1. **Script tidak load**: Periksa library dependencies
2. **Rute tidak berjalan**: Pastikan format file benar
3. **Stuck detection**: Sesuaikan threshold di kode jika perlu
4. **Token tidak valid**: Pastikan mendapat token dari sumber resmi

### Error Handling
- Script memiliki error handling untuk file I/O
- Recovery otomatis untuk stuck detection
- Validasi input untuk semua parameter

## 🔒 Keamanan & Etika

**Perhatian Penting:**
- Script ini untuk keperluan pembelajaran dan testing
- Gunakan dengan bijak dan tidak merugikan pemain lain
- Patuhi aturan server tempat Anda bermain
- Penulis tidak bertanggung jawab atas sanksi yang diterima

## 📝 Changelog v1.0.2

### Perbaikan
- Movement jalan kaki lebih mulus
- Rekam/Playback kendaraan lebih presisi
- Rekam otomatis berdasarkan waktu
- Bug input teks dan slider diperbaiki
- Stabilitas HTTP request dengan socket.http

### Fitur Baru
- Stuck detection dengan recovery
- Progress indicator untuk aksi
- Test route functionality
- Enhanced UI dengan theme custom

## Dukungan & Informasi

- **Author**: kotkaaja
- **Version**: 1.0.2 - Mobile Version  
- **Platform**: SA-MP Android + MonetLoader
- **Compatibility**: Android 6.0+ devices
- **Discord Community**: https://discord.gg/X2UW7VRqnB . join untuk mendapatkan token

### Catatan Penting Android
- Script dioptimalkan untuk perangkat mobile
- Touch controls tidak akan terganggu
- Background processing saat minimize
- Auto-save progress untuk stability

## Disclaimer & Keamanan

**Android Security Notice:**
- Script tidak mengakses data sensitif device
- Tidak memerlukan akses internet kecuali untuk validasi token
- File routes tersimpan lokal di storage aplikasi
- Tidak ada tracking atau logging aktivitas user
