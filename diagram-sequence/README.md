# Diagram Sequence — Alur Sistem Pemesanan

## Maksud Diagram

Diagram ini menggambarkan **garis besar alur kerja aplikasi** pemesanan frozen food dan snack dari tiga sudut pandang: pelanggan, aplikasi, dan admin.

Tujuan diagram:

- Menunjukkan urutan kejadian dari pelanggan mulai masuk aplikasi sampai pesanan selesai diproses admin.
- Memperlihatkan pembagian tugas: pelanggan berbelanja, aplikasi mencatat dan menampilkan data, admin mengelola toko.
- Menjadi acuan bersama (tim, dosen, atau penguji) tanpa harus membaca kode program.

Diagram sengaja dibuat **tanpa istilah teknis** agar mudah dipahami.

## Pihak yang Terlibat

| Pihak | Peran |
|---|---|
| **Pelanggan** | Mendaftar, berbelanja, checkout, dan melihat status pesanan. |
| **Aplikasi** | Menyimpan data, menampilkan halaman, dan memberi respons atas setiap tindakan. |
| **Admin** | Mengelola produk, memantau pesanan, mengubah status, dan melihat data pelanggan. |

## Arti Garis dan Bentuk

| Simbol | Arti |
|---|---|
| **Garis putus-putus vertikal** | Garis hidup (*lifeline*). Menandakan pihak tersebut tetap terlibat selama alur berjalan. |
| **Kotak putus-putus besar** | Satu tahap/alur. Berisi langkah-langkah yang saling berkaitan. |
| **Anak panah garis penuh (→)** | Tindakan atau permintaan yang dikirim oleh pihak pengirim. Contoh: pelanggan membuka katalog. |
| **Anak panah garis putus-putus (⇢)** | Jawaban atau hasil yang diberikan aplikasi. Contoh: aplikasi menampilkan daftar produk. |
| **Urutan dari atas ke bawah** | Urutan waktu kejadian. Makin ke bawah, makin akhir kejadiannya. |

## Tahapan Alur

| No | Tahap | Yang Terjadi |
|---|---|---|
| 1 | **Daftar dan Masuk** | Pelanggan membuat akun atau masuk, lalu aplikasi mengonfirmasi keberhasilan. |
| 2 | **Melihat Produk** | Pelanggan membuka katalog; aplikasi menampilkan produk, harga, dan stok. |
| 3 | **Keranjang Belanja** | Pelanggan menambah, mengubah, atau menghapus produk; total belanja ikut diperbarui. |
| 4 | **Checkout** | Pelanggan mengisi alamat pengiriman dan menyelesaikan pesanan; pesanan tercatat dengan status **Menunggu**. |
| 5 | **Pesanan Saya** | Pelanggan melihat riwayat transaksi beserta status pesanannya. |
| 6 | **Admin Mengelola Toko** | Admin masuk, melihat ringkasan toko, mengelola produk, memantau pesanan masuk, mengubah status pesanan, dan melihat daftar pelanggan. |
| 7 | **Pelanggan Melihat Status Terbaru** | Pelanggan membuka pesanan saya dan melihat status terbaru setelah diproses admin. |

## Alur Status Pesanan

```
Menunggu  →  Diproses  →  Dikirim  →  Selesai
```

- Pesanan baru selalu berstatus **Menunggu** setelah checkout.
- Hanya admin yang dapat mengubah status.
- Perubahan status langsung terlihat oleh pelanggan pada halaman **Pesanan Saya**.

## Ringkasan Satu Kalimat

Pelanggan berbelanja dan membuat pesanan → aplikasi mencatat pesanan → admin memproses dan mengubah status → pelanggan melihat status terbaru.

## Isi Folder

| File | Keterangan |
|---|---|
| `sequence-diagram.drawio` | File diagram asli (XML draw.io), bisa diedit di draw.io atau app.diagrams.net. |
| `sequence-diagram.png` | Gambar diagram siap pakai untuk laporan atau presentasi. |
| `README.md` | Penjelasan ini. |
