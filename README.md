# 🧺 CleanGo Laundry Management System

Aplikasi manajemen laundry berbasis client-server, terdiri dari dashboard admin web (Laravel) dan aplikasi mobile (Flutter) yang terhubung melalui REST API.

Proyek Akhir Semester — Pemrograman Web Berbasis Framework (PWEB) × Pemrograman Perangkat Bergerak Client Server (PPBCS)
Universitas Muhammadiyah Bandung — 2025/2026

## 📋 Fitur Utama

### Web Admin (Laravel)
- Autentikasi Login & Register (Laravel Breeze)
- Role Management (Admin & Customer) menggunakan Spatie Permission
- Dashboard statistik: Total Customer, Total Service, Total Order, Pendapatan
- Manajemen Service: CRUD, search, pagination
- Manajemen Order: lihat data order, detail order, update status laundry, search, filter status, filter pickup, pagination
- Manajemen Pembayaran: detail pembayaran, status pembayaran, search, filter metode & status pembayaran, pagination
- Laporan: filter tanggal, filter status order, filter status pembayaran, export PDF

### Mobile App (Flutter)
- Login & Register
- Dashboard Customer (ringkasan order baru, proses, selesai, total pengeluaran)
- Melihat daftar layanan
- Membuat order laundry
- Riwayat order & detail order
- Checkout pembayaran (Cash & QRIS)
- Melihat status laundry
- Update profil

## 🛠️ Tech Stack

| Bagian | Teknologi |
|---|---|
| Backend | Laravel 13, PHP 8.3 |
| Frontend Web | Blade, Tailwind CSS |
| Database | MySQL |
| Auth & Permission | Laravel Breeze, Spatie Laravel Permission |
| REST API | Laravel Sanctum |
| Mobile | Flutter, Dart |
| State Management | Provider |
| HTTP Client | package http |
| Local Storage | Shared Preferences |
| PDF | DomPDF |
| Version Control | Git & GitHub |

## 📁 Struktur Project

```
├── laravel/
├── Flutter
├── README.md

```

## ⚙️ Instalasi & Menjalankan Project

### Prasyarat
- PHP >= 8.2
- Composer
- Node.js & NPM
- MySQL
- Flutter SDK
- Git

### Laravel (Web Admin)

```bash
# 1. Clone repository
git clone https://github.com/aldihrmn/cleango-laundry.git
cd cleango-laundry

# 2. Install dependencies
composer install

# 3. Salin file environment
cp .env.example .env

# 4. Generate application key
php artisan key:generate
```

Edit file `.env` sesuaikan bagian berikut:

```
APP_NAME="CleanGo Laundry"
APP_URL=http://127.0.0.1:8000

DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=cleango_laundry
DB_USERNAME=root
DB_PASSWORD=
```

```bash
# 5. Buat database 'cleango_laundry' di MySQL, lalu jalankan migration & seeder
php artisan migrate --seed

# 6. Buat symbolic link untuk storage
php artisan storage:link

# 7. Install & build assets
npm install
npm run build

# 8. Jalankan server
php artisan serve
# → http://127.0.0.1:8000
```

### Flutter (Mobile App)

```bash
# 1. Masuk ke folder Flutter
cd flutter

# 2. Install dependencies
flutter pub get
```

Sesuaikan base URL:

```dart
// Android Emulator
const String baseUrl = "http://10.0.2.2:8000/api";

// Device fisik (sesuaikan dengan IP lokal komputer)
// const String baseUrl = "http://192.168.x.x:8000/api";
```

```bash
# 3. Pastikan Laravel sudah berjalan, lalu jalankan Flutter
flutter run
```

## 👥 Akun Default

| Email | Password | Role |
|---|---|---|
| admin@cleango.com | password | Admin |
| customer@cleango.com | password | Customer |

## 📸 Screenshot

### Dashboard Admin (Web)
Menampilkan ringkasan Total Customer, Total Service, Total Order, dan Pendapatan, lengkap dengan menu cepat ke Service, Order, Payment, dan Report.
<img width="1600" height="900" alt="WhatsApp Image 2026-07-22 at 9 03 52 PM" src="https://github.com/user-attachments/assets/0559a229-46f0-43ef-b3ee-decb9c83eb0e" />


### Login Mobile
Tampilan login aplikasi mobile customer.
<img width="627" height="1015" alt="WhatsApp Image 2026-07-22 at 9 04 39 PM" src="https://github.com/user-attachments/assets/589e7a79-01ca-49dc-810e-d82544e2ec3c" />


### Dashboard Customer (Mobile)
Menampilkan ringkasan Order Baru, Proses, Selesai, dan Total Pengeluaran, serta menu cepat Buat Order, Riwayat, Status Order, dan Profil.
<img width="627" height="1015" alt="WhatsApp Image 2026-07-22 at 9 04 21 PM" src="https://github.com/user-attachments/assets/889b9216-a62e-4336-98fb-b1431b864116" />


## 🎥 Video Demo

| Tautan | Keterangan |
|---|---|
| ▶️ [Video Demo (YouTube)](https://youtu.be/EQ6IumlfTU8) | Demo seluruh fitur web & mobile |

## 🗄️ REST API

### Authentication

| Method | Endpoint |
|---|---|
| POST | /api/auth/login |
| POST | /api/auth/register |
| POST | /api/auth/logout |
| PATCH | /api/auth/profile |

### Dashboard

| Method | Endpoint |
|---|---|
| GET | /api/dashboard |

### Service

| Method | Endpoint |
|---|---|
| GET | /api/services |

### Order

| Method | Endpoint |
|---|---|
| GET | /api/orders |
| POST | /api/orders |
| GET | /api/orders/{id} |
| PATCH | /api/orders/{id}/status |
| POST | /api/orders/{id}/payment |
| GET | /api/orders/{id}/payment |
| PATCH | /api/orders/{id}/payment/confirm |

### Contoh Login

```json
{
    "email": "admin@cleango.com",
    "password": "password"
}
```

## 👨‍💻 Tim Pengembang — Kelompok 7

| No | Nama | NIM | Kontribusi |
|---|---|---|---|
| 1 | Fauzan Aditia Putra | 220102034 | API dan Flutter |
| 2 | Ardi Muhamad | 230102001 | Order dan Payment |
| 3 | Aldi Hermawan | 230102015 | Customer dan Service |
| 4 | Muhammad Rizki Febrian | 230102094 | Auth dan Dashboard |

## 🔗 Repository & Dokumen

| Tautan | Keterangan |
|---|---|
| [Laravel (Web Admin)](https://github.com/aldihrmn/cleango-laundry) | Repository backend & web admin |
| [Flutter (Mobile App)](https://github.com/fauzanaditia/cleango-laundry-mobile) | Repository aplikasi mobile |
| [Laporan Tugas Besar PPBCS(PDF)](https://github.com/user-attachments/files/30007009/Laporan_Tugas.Besar_Pemograman.perangkat.bergerak.client.server_Kelompok.7.pdf) | Laporan Tugas Besar PPBCS Kelompok 7 |
| [Laporan Tugas Besar PWEB(PDF)](https://github.com/user-attachments/files/30273124/Laporan.Kendala.Tugas.Besar.Pemrograman.Web.Berbasi.FrameWork.pdf) | Laporan Pweb Kelompok 7 |
| [Presentasi_Kelompok_7_CleanGo_Laundry.pptx](https://github.com/user-attachments/files/30273204/PPT_Kelompok_7_CleanGo_Laundry.pptx) | Presentasi     Kelompok 7 |


## 📝 Lisensi

Proyek ini dibuat untuk memenuhi tugas akhir mata kuliah:
- Pemrograman Web Berbasis Framework (PWEB)
- Pemrograman Perangkat Bergerak Client Server (PPBCS)

Program Studi Teknik Informatika
Universitas Muhammadiyah Bandung
Tahun Akademik 2025/2026
