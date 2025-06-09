<div align="center">
  <h1 style="text-align: center;font-weight: bold">LAPORAN RESMI<br>WORKSHOP ADMINISTRASI JARINGAN</h1>
  <h4 style="text-align: center;">Dosen Pengampu : Dr. Ferry Astika Saputra, S.T., M.Sc.</h4>
</div>
<br />
<div align="center">
  <img src="https://upload.wikimedia.org/wikipedia/id/4/44/Logo_PENS.png" alt="Logo PENS">
  <h3 style="text-align: center;">Disusun Oleh : </h3>
  <p style="text-align: center;">
    <strong>Ale Perdana Putra Darmawan (3123500027) </strong><br>
  </p>
<h3 style="text-align: center;line-height: 1.5">Politeknik Elektronika Negeri Surabaya<br>Departemen Teknik Informatika Dan Komputer<br>Program Studi Teknik Informatika<br>2024/2025</h3>
  <hr><hr>
</div>

## Daftar Isi
- [Daftar Isi](#daftar-isi)
- [Teknologi yang digunakan](#teknologi-yang-digunakan)
- [Struktur Frontend](#struktur-frontend)
  - [Components](#components)
    - [Services](#services)
    - [App Configuration](#app-configuration)
- [Struktur Backend](#struktur-backend)
- [Hasil Akhir](#hasil-akhir)

## Teknologi yang digunakan
- Frontend menggunakan ReactJS untuk menciptakan antarmuka pengguna yang interaktif dan dinamis di browser pengguna. Sisi frontend ini akan berkomunikasi dengan backend melalui API untuk mengambil atau mengirim data.

- Backend menggunakan ExpressJS untuk membangun API yang menangani logika komunikasi dengan database. Layanan ini berjalan di dalam kontainer Docker pada port 3000 yang diekspos ke port 3001 di IP address lokal.

- Database menggunakan MySQL untuk menyimpan classicmodels database. Database ini juga berjalan di dalam kontainer Docker sendiri dan dapat diakses melalui port 3306.

- Docker digunakan untuk mengemas backend dan database ke dalam kontainer yang terisolasi, memastikan keduanya berjalan secara konsisten di lingkungan mana pun. Teknologi ini mengatur pemetaan port agar layanan dapat saling berkomunikasi dan dapat diakses dari luar.

## Struktur Frontend
Source Code: https://github.com/AlePerdana/frontend-adjar.git

### Components
- Dashboard.jsx: Komponen utama yang menampilkan halaman dashboard dengan visualisasi data penjualan dan informasi overview bisnis. Dilengkapi dengan styling melalui `Dashboard.css` untuk mengatur tampilan layout, card, dan elemen-elemen dashboard.

- SalesAnalysis.jsx: Komponen yang menangani analisis data penjualan dengan fitur filtering, sorting, dan visualisasi grafik. Memiliki styling khusus melalui `SalesAnalysis.css` untuk mengatur tampilan tabel, chart, dan control elements.

#### Services
- api.js: File konfigurasi dan fungsi-fungsi API yang menangani komunikasi dengan backend ExpressJS di port 3001. Berisi berbagai endpoint API:
  - getCustomers(): API untuk mengambil data pelanggan dengan dukungan filtering berdasarkan parameter tertentu
  - getOrders(): API untuk mengambil data pesanan dengan kemampuan filtering berdasarkan tanggal, status, atau customer
  - getEmployees(): API untuk mengambil data karyawan dengan opsi filtering departemen atau jabatan
  - getPayments(): API untuk mengambil data pembayaran dengan filtering berdasarkan periode atau jumlah
  - getOffices(): API untuk mengambil data kantor cabang dengan filtering lokasi atau negara
  - getSalesSummary(): API untuk menghitung ringkasan penjualan total termasuk revenue, profit, dan jumlah order
  - getSalesByCountry(): API untuk menganalisis penjualan berdasarkan negara dengan pengelompokan customer dan total sales
  - getSalesByProductLine(): API untuk menganalisis penjualan berdasarkan kategori produk dengan distribusi realistis
  - getSalesByYear(): API untuk menganalisis trend penjualan tahunan berdasarkan data order dan payment
  - testConnection(): API untuk menguji konektivitas dengan backend server

#### App Configuration
- App.js: File utama aplikasi React yang mengatur routing dan struktur komponen utama serta menangani integrasi dengan API service untuk komunikasi dengan backend ExpressJS.

- main.jsx: Entry point aplikasi yang merender komponen App ke DOM.

## Struktur Backend
Source Code: https://github.com/ARVAZAKI/backend-adjar2.git

## Hasil Akhir
- Dashboard.jsx
<br><div style=width:500;>![ss](assets/fe1.png)</div>

- SalesAnalysis.jsx
<br><div style=width:500;>![ss](assets/fe2.png)</div>
<br><div style=width:500;>![ss](assets/fe3.png)</div>
<br><div style=width:500;>![ss](assets/fe4.png)</div>