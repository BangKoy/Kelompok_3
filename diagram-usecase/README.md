# Use Case Diagram

## Aplikasi Web E-Commerce Frozen Food & Snack

**File diagram:** [`use-case-diagram.drawio`](./use-case-diagram.drawio)  
**Pratinjau:** [`New v2 Usecase diagram.png`](<./New v2 Usecase diagram.png>)

![Use Case Diagram](<./New v2 Usecase diagram.png>)

Diagram ini disusun berdasarkan **SRS Aplikasi Web E-Commerce Frozen Food & Snack v1.0**, khususnya Bagian 4 (Fitur Sistem), dan dapat langsung dibuka serta diedit di draw.io. Diagram memuat **29 use case**, **14 association**, **6 `«include»`**, dan **11 `«extend»`**.

---

## 1. Aktor

| Aktor | Deskripsi |
|---|---|
| **Pelanggan (Customer)** | Pengguna yang menelusuri katalog, melihat dan mengubah isi keranjang, melakukan checkout, serta melihat riwayat pesanan. |
| **Admin** | Pengguna yang mengelola produk, memproses pesanan, melihat dashboard, dan melihat daftar pelanggan. |

`Login` dan `Logout` digunakan bersama oleh kedua aktor dan ditempatkan pada
kelompok **Autentikasi** di bagian tengah atas diagram.

---

## 2. Use Case Pelanggan

### 2.1 Autentikasi
- Registrasi Akun
- Login *(shared dengan Admin)*
- Logout *(shared dengan Admin)*

### 2.2 Katalog Produk
- **Melihat Katalog Produk** — use case utama
- **Menambahkan Produk ke Keranjang** — use case utama
- Melihat Detail Produk — `«extend»` ke *Melihat Katalog Produk*
- Mencari / Memfilter Produk — `«extend»` ke *Melihat Katalog Produk*

### 2.3 Keranjang Belanja
- **Melihat Isi Keranjang** — use case utama
  - `«extend»` dari Mengubah Jumlah Produk
  - `«extend»` dari Menghapus Produk dari Keranjang

### 2.4 Checkout dan Pesanan
- **Checkout / Membuat Pesanan** — use case utama
  - `«include»` Mengisi Alamat Pengiriman
  - `«include»` Melihat Konfirmasi Pesanan

### 2.5 Pesanan Saya
- **Melihat Riwayat Pesanan** — use case utama
  - `«extend»` dari Melihat Detail Pesanan Saya

---

## 3. Use Case Admin

### 3.1 Dashboard
- **Melihat Dashboard** — use case utama
  - `«include»` Melihat Total Pendapatan
  - `«include»` Melihat Total Pesanan
  - `«include»` Melihat Total Pelanggan
  - `«include»` Melihat Pesanan Terbaru

### 3.2 Manajemen Produk
- **Melihat Daftar Produk** — use case utama
  - `«extend»` dari Menambah Produk
  - `«extend»` dari Mengubah Produk
  - `«extend»` dari Menghapus Produk

### 3.3 Manajemen Pesanan
- **Melihat Semua Pesanan** — use case utama
  - `«extend»` dari Melihat Detail Pesanan Pelanggan
  - `«extend»` dari Mengubah Status Pesanan

### 3.4 Manajemen Pelanggan
- **Melihat Daftar Pelanggan** — use case utama
  - `«extend»` dari Melihat Jumlah Pesanan Pelanggan

---

## 4. Jenis Relasi

| Relasi | Notasi | Makna pada diagram |
|---|---|---|
| **Association** | Garis solid tanpa panah | Menghubungkan aktor dengan use case yang dapat diaksesnya. |
| **`«include»`** | Garis putus-putus dengan panah terbuka, dari use case dasar ke use case yang disertakan | Use case dasar **wajib** menjalankan use case yang disertakan. Contoh: *Checkout* `«include»` *Mengisi Alamat Pengiriman*. |
| **`«extend»`** | Garis putus-putus dengan panah terbuka, dari use case tambahan ke use case dasar | Use case tambahan bersifat **opsional/kondisional** terhadap use case dasar. Contoh: *Mencari / Memfilter Produk* `«extend»` *Melihat Katalog Produk*. |

---

## 5. Catatan Perancangan

- **Login/Logout tidak diduplikasi.** Keduanya dimodelkan satu kali dan
  dihubungkan ke Pelanggan maupun Admin agar sesuai dengan satu sistem
  autentikasi pada SRS (AUTH-5 s.d. AUTH-9).
- **Dashboard memakai `«include»`.** Empat ringkasan (pendapatan, pesanan,
  pelanggan, pesanan terbaru) adalah bagian wajib dari dashboard sesuai
  DSH-1 s.d. DSH-4.
- **Pembayaran tidak dimodelkan sebagai use case.** SRS menyatakan pembayaran
  ditangani di luar sistem (AS-2 dan BR-6), sehingga tidak ada use case
  payment gateway.
- **Alamat pengiriman dan konfirmasi memakai `«include»`.** Checkout tidak dapat
  diselesaikan tanpa alamat pengiriman (CHK-2), dan SRS mewajibkan sistem
  menampilkan konfirmasi pesanan setelah checkout (CHK-8). Keduanya perilaku
  wajib, sehingga arah panahnya dari *Checkout* ke use case yang disertakan.
- **CRUD admin memakai `«extend»` dari use case daftar.** *Melihat Daftar
  Produk* dan *Melihat Semua Pesanan* menjadi use case dasar yang dihubungkan
  ke Admin. Menambah/mengubah/menghapus produk serta melihat detail/mengubah
  status pesanan adalah aksi opsional yang memperluas use case dasar tersebut.
- **Keranjang memakai `«extend»`.** *Melihat Isi Keranjang* adalah use case
  dasar; mengubah jumlah dan menghapus produk adalah perilaku opsional.
  Dengan demikian tidak ada lagi use case umbrella "Mengelola ..." yang
  ambigu.
- **Detail produk dan detail pesanan memakai `«extend»`.** Keduanya adalah
  tampilan lanjutan yang dibuka secara opsional dari katalog/riwayat.
- **Warna diagram:** biru = fitur Pelanggan, oranye = fitur Admin, hijau =
  fitur Autentikasi yang digunakan bersama.

---

## 6. Cara Membuka dan Mengedit

1. Buka [draw.io](https://app.diagrams.net) atau aplikasi draw.io Desktop.
2. Pilih **File → Open From → Device**, lalu pilih `use-case-diagram.drawio`.
3. Seluruh elemen (aktor, ellipse use case, kotak kelompok, dan garis relasi)
   merupakan objek native draw.io yang dapat dipindah, diubah teksnya, dan
   diedit propertinya.
