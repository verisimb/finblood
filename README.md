# Finblood

<p align="center">
  <img src="assets/logofinblood/logomaroon.png" alt="Finblood Logo" width="250">
</p>

**Project Pemrograman Mobile Kelompok Finblood**

- **Very Irawan Simbolon (2315091092)**
- **I Gede Surya Dharma Putra (2315091076)**
- **I Putu Tonyco Satria Pradipta (2315091058)**

Finblood adalah aplikasi mobile untuk memudahkan pencarian dan pendaftaran pendonor darah. Aplikasi ini membantu menghubungkan orang yang membutuhkan darah dengan sukarelawan pendonor darah dari berbagai kampus.

## Fitur Utama

- **Autentikasi Pengguna**: Pendaftaran, login, verifikasi email, dan reset kata sandi
- **Daftar Pendonor**: Lihat daftar pendonor darah berdasarkan kampus dan golongan darah
- **Daftar Menjadi Pendonor**: Tambahkan diri Anda ke database pendonor darah
- **Peringkat Kampus**: Lihat statistik jumlah pendonor dari setiap kampus
- **Kontak Langsung**: Hubungi pendonor langsung melalui nomor telepon
- **Carousel Slide**: Menampilkan carousel slide yang dapat diatur secara dinamis melalui backend atau pengaturan admin. Setiap slide memiliki konten visual (gambar atau teks) dan aksi yang dapat disesuaikan
- **Notifikasi Pendonor Baru**: Mengirimkan push notifikasi ke pengguna setiap ada pendonor baru

## Screenshot

<p align="center">
  <img src="assets/images/ss1.png" alt="Login Screen" width="150">
  &nbsp;&nbsp;&nbsp;
  <img src="assets/images/ss2.png" alt="Home Screen" width="150">
  &nbsp;&nbsp;&nbsp;
  <img src="assets/images/ss3.png" alt="Donor Register Screen" width="150">
  &nbsp;&nbsp;&nbsp;
  <img src="assets/images/ss4.png" alt="Donor List Screen" width="150">
</p>

## Teknologi

- **Frontend**: Flutter
- **Backend**: Firebase (Authentication, Firestore, Cloud Functions, Cloud Messaging)
- **Penyimpanan Data**: Cloud Firestore
- **Autentikasi**: Firebase Authentication
- **Notifikasi**: Firebase Cloud Messaging (FCM)
- **Pengelolaan Status**: Shared Preferences

## Prasyarat

- Flutter SDK (versi terbaru)
- Dart (versi terbaru)
- Firebase Project
- Android Studio / VS Code

## Instalasi

1. Clone repositori ini
   ```bash
   git clone https://github.com/verisimb/finblood.git
   cd finblood
   ```

2. Install dependencies
   ```bash
   flutter pub get
   ```

3. Jalankan aplikasi
   ```bash
   flutter run
   ```

## Struktur Database

### Collection: users
- **uid**: String (Primary Key)
- **nama**: String
- **email**: String
- **emailVerified**: Boolean
- **createdAt**: Timestamp
- **updatedAt**: Timestamp
- **displayName**: String

### Collection: pendonor
- **nama**: String
- **nomor_hp**: String
- **kampus**: String
- **golongan_darah**: String (A, B, AB, O)
- **timestamp**: Timestamp

### Collection: carousel_images
- **url**: String
- **order**: Number
- **actionType**: String
- **actionValue**: String

### Collection: carousel_metadata
- **lastUpdated**: Timestamp

## Cloud Functions

Aplikasi ini menggunakan Cloud Functions untuk:
- Verifikasi email pengguna
- Menghapus akun pengguna saat terjadi kegagalan pendaftaran
- Mengirim push notification ke semua pengguna setiap ada pendonor baru (otomatis via FCM & Cloud Functions)

## Pengembangan Lebih Lanjut

- Integrasi dengan rumah sakit dan PMI
