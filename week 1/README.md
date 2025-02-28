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
- [Tugas Review](#tugas-review)
  - [Soal Pertama](#soal-pertama)
  - [Soal Kedua](#soal-kedua)
  - [Soal Ketiga](#soal-ketiga)
- [Kesimpulan](#kesimpulan)

## Tugas Review
### Soal Pertama
Analisa file http.cap dengan wireshark : Versi HTTP yang digunakan, IP address dari client maupun server, waktu dari client mengirimkan HTTP request., Waktu dari server mengirinmkan server dan berapa durasinya.<br>
Jawab:<br>
![img](Assets/img1.png)<br>
Versi HTTP yang digunakan adalah versi 1.1

![img](Assets/img2.png)<br>
IP address yang digunakan client adalah 145.254.160.237.<br>
IP address yang digunakan server adalah 65.208.228.223.<br>

![img](Assets/img3.png)<br>
Waktu dari client mengirimkan HTTP request adalah 0.911310.

![img](Assets/img4.png)<br>
Waktu dari server mengirimkan server adalah 3.955688.

![img](Assets/img5.png)<br>
Durasi untuk menyelesaikan sesi HTTP request adalah 4,846969 - 3.955688 = 0,891281.<br>

### Soal Kedua
Deskripsi gambar pada slide.<br>
![img](Assets/img6.png)<br>
Penjelasan: Dari gambar diatas dijelaskan tipe jenis pengiriman data yang dari node to node atau router ke router, host to host atau antar komputer, dan proses ke proses. <br>
Node to node mengggunakan data link layer yang membungkus data dalam bentuk frame yang berisi dengan alamat fisik (MAC address), error detection, dan flow control.<br>
Host to host menggunakan network layer yang membungkus data dalam bentuk packet yang berisi dengan alamat IP (IP address) dengan fungsi untuk mencari jalur terbaik untuk mencapai tujuannya.<br>
Process to process menggunakan transport layer yang membungkus data dalam bentuk segment yang berisi dengan port number agar membedakan antar proses atau aplikasi. Dalam segment juga terdapat protocol TCP dan UDP untuk sistem pengiriman dan penerimaan data.

### Soal Ketiga
rangkuman tahapan komunikasi menggunakan TCP<br>
Jawab: Tahapan komunikasi utama dalam penggunaaan TCP terdapat Establish Connection menggunakan Three-Way Handshake, Data Transmission, dan Connection Termination. 

Tahap komunikasi pertama adalah Establish Connection dengan Three-Way Handshake yaitu dengan client mengirim segmen SYN ke server untuk memulai koneksi, lalu server  merespons dengan SYN-ACK, setelah itu, client membalas dengan ACK terakhir. Setelah proses ini selesai, koneksi TCP antar client dan server telah terbentuk.

Tahap komunikasi kedua adalah Data Transmission yaitu proses pengiriman data. Saat data dikirim, data tersebut akan di pecah menjadi segmen-segmen yang berukuran sama atau kurang. Setiap segmen yang terpecah memiliki sequence number masing masing yang dimana saat diterima oleh server akan mengirimkan ACK kepada client. Jika server tidak menerima pecahan segmen, maka TCP akan mengirimkan ulang segmen yang belum diterima.

Tahap komunikasi ketiga adalah Connection Termination yaitu proses terminasi koneksi antar client dan server. Proses ini dimulai saat salah satu pihak (client atau server) mengirim segmen FIN untuk mengakhiri transmisi. Pihak lain merespons dengan ACK dan juga mengirim FIN untuk memutuskan koneksi. Setelah itu pengirim akan menutup koneksi setelah menerima ACK terakhir.

## Kesimpulan
Dapat disimpulkan bahwa TCP (Transmission Control Protocol) merupakan protokol yang ada pada layer transport yang berfungsi untuk pengiriman dan penerimaan data secara reliabel. TCP memastikan bahwa data yang dikirim dari pengirim sampai ke penerima dengan urutan yang benar dan tanpa kehilangan data.