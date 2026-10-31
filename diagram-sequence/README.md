# Sequence Diagram

## Aplikasi Web E-Commerce Frozen Food & Snack

**File diagram:** [`sequence-diagram.drawio`](./sequence-diagram.drawio)
**PDF gabungan:** [`Sequence-Diagram-Kelompok-3.pdf`](./Sequence-Diagram-Kelompok-3.pdf) — 31 halaman (cover + daftar + 29 diagram)
**Pratinjau PNG:** folder [`png/`](./png) — 29 file, satu per use case (resolusi 2x)
**Sumber use case:** [`../diagram-usecase/use-case-diagram.drawio`](../diagram-usecase/use-case-diagram.drawio)
**Acuan kebutuhan:** SRS Aplikasi Web E-Commerce Frozen Food & Snack v1.0, Bagian 4

Satu file `.drawio` berisi **29 halaman** — satu sequence diagram untuk setiap
use case pada use case diagram Kelompok 3. Setiap halaman memakai penomoran
`SD-01` s.d. `SD-29` yang sama dengan nomor tab.

---

## 1. Partisipan

| Partisipan | Notasi | Keterangan |
|---|---|---|
| **Pelanggan / Admin** | stick figure | Aktor yang memicu use case. |
| **Halaman …** | «UI» | Halaman/komponen Next.js App Router yang dilihat pengguna. |
| **Server Action / RSC** | «Next.js» | Logika sisi server: Server Action, Route Handler, atau Server Component yang mengakses data. |
| **Prisma Client** | «ORM» | Lapisan akses data (query terparameterisasi, `$transaction`). |
| **MySQL** | «database» | Basis data relasional. |

Warna mengikuti use case diagram: biru = Pelanggan, oranye = Admin,
ungu = autentikasi bersama, kuning = server, merah = basis data.

---

## 2. Notasi

| Simbol | Makna |
|---|---|
| Panah solid + kepala penuh | Pemanggilan pesan (request/aksi). |
| Panah putus-putus + kepala terbuka | Pesan balasan (return/response). |
| Loop kecil pada lifeline | Proses internal (validasi, hashing, transaksi). |
| Kotak berlabel `alt` / `opt` | Fragment: `alt` = dua kemungkinan (dengan `else`), `opt` = perilaku opsional/kondisional. |
| Bar vertikal pada lifeline | Activation bar (masa aktif partisipan). |

---

## 3. Daftar Halaman

### 3.1 Autentikasi

| No | Halaman | Aktor | Relasi | Kebutuhan |
|---|---|---|---|---|
| SD-01 | Registrasi Akun | Pelanggan | — | AUTH-1 s.d. AUTH-4 |
| SD-02 | Login | Pelanggan / Admin | — | AUTH-5 s.d. AUTH-8 |
| SD-03 | Logout | Pelanggan / Admin | — | AUTH-9 |

### 3.2 Katalog Produk

| No | Halaman | Aktor | Relasi | Kebutuhan |
|---|---|---|---|---|
| SD-04 | Melihat Katalog Produk | Pelanggan | — | CAT-1, CAT-2, CAT-5 |
| SD-05 | Melihat Detail Produk | Pelanggan | `«extend»` Katalog | CAT-3 |
| SD-06 | Mencari / Memfilter Produk | Pelanggan | `«extend»` Katalog | CAT-4 |

### 3.3 Keranjang Belanja

| No | Halaman | Aktor | Relasi | Kebutuhan |
|---|---|---|---|---|
| SD-07 | Menambahkan Produk ke Keranjang | Pelanggan | — | CART-1, CART-2, CART-7 |
| SD-08 | Melihat Isi Keranjang | Pelanggan | — | CART-6, CART-7 |
| SD-09 | Mengubah Jumlah Produk | Pelanggan | `«extend»` Lihat Keranjang | CART-3, CART-5 |
| SD-10 | Menghapus Produk dari Keranjang | Pelanggan | `«extend»` Lihat Keranjang | CART-4 |

### 3.4 Checkout dan Pesanan

| No | Halaman | Aktor | Relasi | Kebutuhan |
|---|---|---|---|---|
| SD-11 | Checkout / Membuat Pesanan | Pelanggan | — | CHK-1 s.d. CHK-8, SAF-1 |
| SD-12 | Mengisi Alamat Pengiriman | Pelanggan | `«include»` Checkout | CHK-2 |
| SD-13 | Melihat Konfirmasi Pesanan | Pelanggan | `«include»` Checkout | CHK-8 |
| SD-14 | Melihat Riwayat Pesanan | Pelanggan | — | ORD-1, ORD-2 |
| SD-15 | Melihat Detail Pesanan Saya | Pelanggan | `«extend»` Riwayat | ORD-3, ORD-4 |

### 3.5 Dashboard Admin

| No | Halaman | Aktor | Relasi | Kebutuhan |
|---|---|---|---|---|
| SD-16 | Melihat Dashboard | Admin | — | DSH-1 s.d. DSH-5 |
| SD-17 | Melihat Total Pendapatan | Admin | `«include»` Dashboard | DSH-1 |
| SD-18 | Melihat Total Pesanan | Admin | `«include»` Dashboard | DSH-2 |
| SD-19 | Melihat Total Pelanggan | Admin | `«include»` Dashboard | DSH-3 |
| SD-20 | Melihat Pesanan Terbaru | Admin | `«include»` Dashboard | DSH-4 |

### 3.6 Manajemen Produk

| No | Halaman | Aktor | Relasi | Kebutuhan |
|---|---|---|---|---|
| SD-21 | Melihat Daftar Produk | Admin | — | PRD-2, PRD-6 |
| SD-22 | Menambah Produk | Admin | `«extend»` Daftar Produk | PRD-1, PRD-5 |
| SD-23 | Mengubah Produk | Admin | `«extend»` Daftar Produk | PRD-3 |
| SD-24 | Menghapus Produk | Admin | `«extend»` Daftar Produk | PRD-4, SAF-2 |

### 3.7 Manajemen Transaksi

| No | Halaman | Aktor | Relasi | Kebutuhan |
|---|---|---|---|---|
| SD-25 | Melihat Semua Pesanan | Admin | — | TRX-1, TRX-6 |
| SD-26 | Melihat Detail Pesanan Pelanggan | Admin | `«extend»` Semua Pesanan | TRX-2 |
| SD-27 | Mengubah Status Pesanan | Admin | `«extend»` Semua Pesanan | TRX-3 s.d. TRX-5 |

### 3.8 Manajemen Pelanggan

| No | Halaman | Aktor | Relasi | Kebutuhan |
|---|---|---|---|---|
| SD-28 | Melihat Daftar Pelanggan | Admin | — | CUS-1, CUS-3, CUS-4 |
| SD-29 | Melihat Jumlah Pesanan Pelanggan | Admin | `«extend»` Daftar Pelanggan | CUS-2 |

---

## 4. Catatan Perancangan

- **Alur mengikuti SRS.** Urutan pesan, validasi, dan pengecekan peran pada
  setiap halaman mengacu pada urutan stimulus/respons dan kebutuhan
  fungsional Bagian 4 SRS.
- **Checkout bersifat transaksional.** SD-11 memakai `prisma.$transaction`
  (`BEGIN` → cek stok → `INSERT Order` + `OrderItem` dengan snapshot harga →
  kurangi stok → kosongkan keranjang → `COMMIT`). Jika stok tidak cukup,
  seluruh transaksi di-`ROLLBACK` sehingga tidak ada pesanan parsial
  (CHK-6, SAF-1).
- **Otorisasi di sisi server.** Pengecekan sesi/peran muncul sebagai pesan ke
  diri sendiri pada Server Action/RSC, bukan hanya penyembunyian di UI
  (AUTH-7, AUTH-8, SEC-5, SEC-7).
- **Sesi berbasis cookie.** Logout (SD-03) menghapus sesi dan cookie, sehingga
  tidak melibatkan basis data — halaman ini hanya memakai tiga lifeline.
- **Soft-delete produk.** SD-24 memakai `alt`: produk yang sudah dirujuk
  `OrderItem` di-soft-delete, produk yang belum dirujuk dihapus permanen
  (PRD-4, TBD pada SRS).
- **Status pesanan satu arah.** SD-27 memvalidasi transisi
  `Pending → Diproses → Dikirim → Selesai` dan menolak transisi lain
  (TRX-3, TRX-4).
- **Login/Logout dipakai bersama.** Keduanya memakai aktor
  *Pelanggan / Admin* dan diwarnai ungu, sama seperti pada use case diagram.

---

## 5. Cara Membuka, Mengedit, dan Ekspor

1. Buka [draw.io](https://app.diagrams.net) atau draw.io Desktop.
2. Pilih **File → Open From → Device**, lalu pilih `sequence-diagram.drawio`.
3. Setiap use case berada pada tab/halaman terpisah (SD-01 s.d. SD-29).
4. Untuk laporan: **File → Export as → PNG/SVG/PDF**, pilih halaman yang
   diinginkan (atau *All Pages* untuk PDF).
5. Semua elemen (lifeline, pesan, fragment, activation bar) adalah objek
   native draw.io yang dapat dipindah dan diedit.

### Ekspor PNG

Semua halaman sudah diekspor ke folder [`png/`](./png) dengan nama
`SD-<nomor> <nama use case>.png`, resolusi 2x (misalnya
`SD-11 Checkout dan Membuat Pesanan.png` berukuran 3000 × 3816 px). File PNG
memakai latar putih dan margin 40 px, siap ditempel ke dokumen laporan.

Untuk mengekspor ulang setelah diagram diubah: di draw.io pilih
**File → Export as → PNG**, centang **All Pages**, atur *Zoom* 200% dan
*Border Width* 20, lalu simpan.

### PDF gabungan

[`Sequence-Diagram-Kelompok-3.pdf`](./Sequence-Diagram-Kelompok-3.pdf) berisi
seluruh PNG dalam satu dokumen:

| Halaman | Isi |
|---|---|
| 1 | Cover (judul, kelompok, anggota) |
| 2 | Daftar diagram + nomor halaman |
| 3–31 | SD-01 s.d. SD-29, satu diagram per halaman |

Halaman diagram memakai A4 dengan orientasi otomatis (landscape untuk diagram
lebar, portrait untuk diagram tinggi) dan dilengkapi bookmark per use case
sehingga mudah dinavigasi di pembaca PDF.
