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
- [Bab 4: Kontrol Proses](#bab-4-kontrol-proses)
  - [Komponen dari sebuah proses](#komponen-dari-sebuah-proses)
  - [PID: Angka Process ID](#pid-angka-process-id)
  - [PPID: Angka parent process ID](#ppid-angka-parent-process-id)
  - [UID dan EUID: user ID and effective user ID](#uid-dan-euid-user-id-and-effective-user-id)
- [Siklus Hidup dari Proses](#siklus-hidup-dari-proses)
- [Signals](#signals)
  - [kill: send signals](#kill-send-signals)

## Bab 4: Kontrol Proses
### Komponen dari sebuah proses
Sebuah proses terdiri dari ruang alamat dan kumpulan struktur data dalam kernel. Ruang alamat adalah kumpulan halaman memori yang telah ditandai oleh kernel untuk penggunaan proses. Halaman-halaman memori ini adalah sebuah unit pengolaan memori yang digunakan untuk menyimpan kode, data, dan tumpukan proses. Struktur data dalam kernel mencatat status proses, prioritasnya, parameter penjadwalan, dan lain-lain.

Dalam kumpulan struktur data kernel merekam berbagai informasi untuk masing-masing proses, seperti:
- Proses pemetaan ruang alamat
- Status proses saat ini, seperti Running, Sleeping, dan seterusnya
- Prioritas untuk proses
- Informasi tentang sumber daya yang telah digunakan oleh proses, seperti CPU, memori, dan lain-lain
- Informasi tentang proses files dan port jaringan yang telah terbuka
- Masker sinyal, kumpulan sinyal yang saat ini diblokir
- Pemilik proses

Sebuah "Thread" adalah eksekusi konteks dalam proses. Sebuah proses memiliki beberapa thread, yang dimana semua berbagi ruang alamat dan sumber daya yang sama. Thread digunakan untuk mencapai paralelisme dalam proses yang berarti agar thread dapat bekerja secara bersama. Thread terkenal sebagai proses yang ringan dikarenakan mereka mudah dibuat dan dihancurkan dibandingkan dengan proses.

### PID: Angka Process ID
Setiap proses diidentifikasikan oleh angka proses ID yang unik. PID merupakan integer yang ditugaskan oleh kernel untuk setiap proses saat proses tersebut dibuat. PID digunakan untuk mereferensikan proses pada berbagai pemanggilan sistem.

### PPID: Angka parent process ID
Setiap proses juga diasosiakan dengan parent process, yang berarti proses yang membuat proses tersebut. PPID merupakan PID dari orang tua dari proses tersebut. PPID digunakan untuk mereferensikan orang tua dari proses pada berbagai pemanggilan sistem.

### UID dan EUID: user ID and effective user ID
User ID merupakan ID pengguna dari pengguna yang menjalankan proses. Effective User ID merupakan UID yang proses gunakan untuk menentukan sumber daya yang proses dapat gunakan. EUID digunakan untuk mengontrol akses ke file, port jaringan, dan sumber daya lainnya. 

## Siklus Hidup dari Proses
Untuk membuat proses baru, proses menyalin dirinya sendiri dengan fork system call. Fork membuat salinan proses yang asli, dan salinan tersebut sebagian besar identik dengan parent-nya. Proses yang baru memiliki PID berbeda dan memiliki informasi perhitungan sendiri.

Saat sistem boot, kernel secara otomatis membuat dan menginstall beberapa proses. Proses yang paling terlihat adalah `init` atau `systemd`, yang selalu memiliki angka proses 1. Proses ini mengeksekusi skrip sistem startup.

## Signals
Signal merupakan cara untuk mengirim notifikasi kepada proses. Sebanyak 30 jenis yang didefinisikan, Mereka digunakan dalam berbagai cara:
- Sebagai komunikasi antar proses
- Dikirim oleh driver terminal untuk menghentikan, menginterupsi, atau menangguhkan proses saat tombol tertentu ditekan
- Dikirim oleh administrator (dengan `kill`) untuk berbagai tujuan
- Dikirim oleh kernel saat proses melakukan kesalahan fatal
- Dikirim oleh kernel untuk memberi notifikasi untuk sebuah proses tentang kondisi khusus

### kill: send signals
Perintah `kill`<br>
Perintah ini digunakan untuk menghentikan proses dengan cara mengirim signal. Standarnya, perintah tersebut mengirim sinyal `TERM` yang dimana meminta proses untuk menghentikan sendiri.  Namun, sinyal `TERM` bisa ditangkap, diblokir, atau diabaikan oleh proses. Menggunakan kill -9 (atau kill -KILL), sinyal KILL tidak bisa ditangkap, diblokir, atau diabaikan.<br>
syntax perintah `kill`:

```kill [-signal] pid```

Contoh percobaan:<br>
