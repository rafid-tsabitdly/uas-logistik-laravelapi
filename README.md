Sistem Logistik IT - Back-End (Laravel API)

Repositori ini berisi sistem *Back-End* dan pangkalan data berbasis Laravel REST API untuk mendukung kebutuhan data *real-time* pada aplikasi mobile/web manajemen Logistik IT.

## Panduan Instalasi & Konfigurasi Server Lokal

### 1. Prasyarat Sistem
* Laragon atau XAMPP aktif
* PHP versi 8.x ke atas
* Composer terinstal di komputer

### 2. Langkah Instalasi Proyek
1. Clone atau unduh repositori ini dan letakkan folder proyek ke dalam direktori server lokal Anda (misalnya di `C:\laragon\www\rest-api`).
2. Buka terminal di dalam folder proyek tersebut, lalu jalankan perintah instalasi dependensi vendor:
   ```bash
   composer install
3. Salin file konfigurasi lingkungan .env.example menjadi file .env baru:
   cp .env.example .env
4. Buat kunci enkripsi aplikasi baru dengan menjalankan perintah:
   php artisan key:generate
   
### 3. Konfigurasi & Impor Pangkalan Data (Database)
1. Aktifkan Laragon/XAMPP Anda, lalu buka alat manajemen database seperti HeidiSQL atau phpMyAdmin.
2. Lakukan impor (Import) berkas database db_logistik_it.sql yang telah disediakan langsung di dalam repositori utama ini. Berkas ini secara otomatis akan membangun struktur tabel beserta data dummy inventaris bawaan.
3. Buka file .env yang baru Anda buat, lalu pastikan baris konfigurasi pangkalan data telah diarahkan ke database lokal Anda seperti berikut:
    DB_CONNECTION=mysql
    DB_HOST=127.0.0.1
    DB_PORT=3306
    DB_DATABASE=db_logistik
    DB_USERNAME=root
    DB_PASSWORD=

### 4. Menjalankan Server Lokal API
1. Untuk mengaktifkan layanan API agar dapat diakses oleh aplikasi Flutter, jalankan perintah berikut pada terminal Anda:
    php artisan serve
    Server lokal akan aktif dan berjalan pada alamat http://127.0.0.1:8000.

