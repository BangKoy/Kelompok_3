# Use Case Diagram

## Aplikasi Web E-Commerce Frozen Food & Snack

## 1. Deskripsi Umum

Use Case Diagram ini menggambarkan interaksi antara dua aktor utama,
yaitu **Pelanggan (Customer)** dan **Admin**, dengan sistem Aplikasi Web
E-Commerce Frozen Food & Snack. Diagram menunjukkan fungsi-fungsi yang
dapat diakses oleh masing-masing aktor, mulai dari autentikasi, melihat
produk, melakukan transaksi, hingga pengelolaan produk dan pesanan.

Pelanggan menggunakan aplikasi untuk melihat katalog dan melakukan
pembelian produk frozen food dan snack. Admin bertanggung jawab
mengelola produk, memantau pesanan, memperbarui status pesanan, serta
melihat informasi pelanggan.

## 2. Aktor Sistem

  -----------------------------------------------------------------------
  Aktor                               Deskripsi
  ----------------------------------- -----------------------------------
  **Pelanggan (Customer)**            Pengguna yang mengakses aplikasi
                                      untuk melihat katalog produk,
                                      mencari produk, mengelola keranjang
                                      belanja, melakukan checkout, dan
                                      melihat riwayat pesanan.

  **Admin**                           Pengguna yang mengelola operasional
                                      toko melalui aplikasi, termasuk
                                      dashboard, produk, pesanan, dan
                                      informasi pelanggan.
  -----------------------------------------------------------------------

## 3. Use Case Pelanggan

### 3.1 Autentikasi

Bagian autentikasi menggambarkan proses pelanggan menggunakan akun untuk
mengakses aplikasi.

-   **Registrasi Akun:** Pelanggan membuat akun baru untuk menggunakan
    aplikasi.
-   **Login:** Pelanggan masuk ke aplikasi menggunakan akun yang telah
    terdaftar.
-   **Logout:** Pelanggan mengakhiri sesi penggunaan aplikasi.

### 3.2 Katalog Produk

Bagian katalog produk menyediakan fitur bagi pelanggan untuk mencari dan
melihat informasi produk yang tersedia.

-   **Melihat Katalog Produk:** Pelanggan melihat daftar produk yang
    ditawarkan toko.
-   **Melihat Detail Produk:** Pelanggan melihat informasi lebih lengkap
    mengenai produk yang dipilih.
-   **Mencari / Memfilter Produk:** Pelanggan mencari atau menyaring
    produk berdasarkan kriteria tertentu.

### 3.3 Keranjang Belanja

Bagian keranjang belanja memungkinkan pelanggan mengelola produk yang
akan dibeli sebelum checkout.

-   **Mengelola Keranjang Belanja:** Pelanggan mengelola produk yang
    telah dimasukkan ke keranjang.
-   **Menambahkan Produk ke Keranjang:** Pelanggan memasukkan produk
    yang ingin dibeli.
-   **Mengubah Jumlah Produk:** Pelanggan menyesuaikan jumlah produk
    yang akan dibeli.
-   **Menghapus Produk dari Keranjang:** Pelanggan menghapus produk yang
    tidak ingin dibeli.
-   **Melihat Keranjang Belanja:** Pelanggan melihat daftar produk yang
    dipilih beserta jumlah dan total belanja.

### 3.4 Checkout dan Pesanan

Bagian checkout dan pesanan menggambarkan proses pelanggan menyelesaikan
pembelian melalui aplikasi.

-   **Checkout / Membuat Pesanan:** Pelanggan melanjutkan pembelian
    produk dari keranjang.
-   **Mengisi Alamat Pengiriman:** Pelanggan memasukkan alamat tujuan
    pengiriman.
-   **Memilih Metode Pembayaran:** Pelanggan menentukan metode
    pembayaran yang akan digunakan.
-   **Membuat Pesanan:** Sistem memproses data pembelian menjadi
    pesanan.
-   **Melihat Konfirmasi Pesanan:** Pelanggan melihat informasi bahwa
    pesanan berhasil dibuat.
-   **Melihat Riwayat Pesanan:** Pelanggan melihat daftar transaksi yang
    pernah dilakukan.
-   **Melihat Detail Pesanan:** Pelanggan melihat informasi lengkap
    pesanan tertentu dari riwayat.

## 4. Use Case Admin

### 4.1 Dashboard

Dashboard menyediakan ringkasan informasi operasional toko kepada Admin.

-   **Melihat Dashboard:** Admin melihat ringkasan aktivitas dan
    performa toko.
-   **Melihat Total Pendapatan:** Admin melihat jumlah pendapatan toko.
-   **Melihat Total Pesanan:** Admin melihat jumlah pesanan yang
    tercatat.
-   **Melihat Total Pelanggan:** Admin melihat jumlah pelanggan yang
    terdaftar.
-   **Melihat Pesanan Terbaru:** Admin melihat pesanan yang baru masuk
    ke sistem.

### 4.2 Manajemen Produk

Bagian manajemen produk digunakan Admin untuk mengelola informasi produk
yang ditampilkan kepada pelanggan.

-   **Mengelola Produk:** Admin melakukan pengelolaan data produk.
-   **Melihat Daftar Produk:** Admin melihat seluruh produk yang
    tersedia di sistem.
-   **Menambahkan Produk:** Admin memasukkan produk baru ke katalog.
-   **Mengubah Produk:** Admin memperbarui informasi produk yang sudah
    ada.
-   **Menghapus Produk:** Admin menghapus produk yang tidak lagi
    ditawarkan.

### 4.3 Manajemen Pesanan

Bagian manajemen pesanan memungkinkan Admin memantau dan menangani
transaksi pelanggan.

-   **Mengelola Pesanan:** Admin melakukan pengelolaan pesanan yang
    masuk.
-   **Melihat Semua Pesanan:** Admin melihat seluruh pesanan pelanggan.
-   **Melihat Detail Pesanan:** Admin melihat informasi lengkap pesanan
    tertentu.
-   **Mengubah Status Pesanan:** Admin memperbarui status pesanan sesuai
    proses penanganannya.

Status pesanan yang ditampilkan pada diagram adalah:

`Pending → Diproses → Dikirim → Selesai`

### 4.4 Manajemen Pelanggan

Bagian manajemen pelanggan menyediakan informasi mengenai pelanggan yang
menggunakan aplikasi.

-   **Melihat Daftar Pelanggan:** Admin melihat daftar pelanggan yang
    terdaftar.
-   **Melihat Jumlah Pesanan Setiap Pelanggan:** Admin melihat jumlah
    pesanan yang dilakukan pelanggan tertentu.

## 5. Relasi pada Diagram

Diagram menggunakan beberapa jenis relasi:

-   **Association:** Garis yang menghubungkan aktor dengan use case
    untuk menunjukkan fitur yang dapat diakses aktor.
-   **`<<include>>`:** Menunjukkan bahwa suatu use case menyertakan
    perilaku use case lain sebagai bagian dari prosesnya.
-   **`<<extend>>`:** Menunjukkan bahwa suatu use case menambahkan
    perilaku pada use case lain dalam kondisi tertentu.

Catatan: Penjelasan ini mengikuti fitur dan relasi yang terlihat pada
diagram. Ketepatan beberapa relasi `include` dan `extend`, khususnya
pada autentikasi dan pengelolaan keranjang, perlu diperiksa kembali agar
sesuai dengan makna UML.

## 6. Kesimpulan

Use Case Diagram Aplikasi Web E-Commerce Frozen Food & Snack memberikan
gambaran ruang lingkup fungsional sistem serta pembagian akses antara
Pelanggan dan Admin. Pelanggan menggunakan aplikasi untuk mencari produk
dan melakukan pembelian, sedangkan Admin mengelola produk, memantau
transaksi, memperbarui status pesanan, dan melihat informasi pelanggan.

Diagram ini dapat menjadi dasar untuk memahami kebutuhan fungsional
aplikasi sebelum perancangan lebih lanjut, seperti Activity Diagram,
Sequence Diagram, dan implementasi sistem.
