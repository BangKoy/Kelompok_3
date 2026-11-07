# REKAP PROJECT RPL — N1

## Aplikasi Web E-Commerce Frozen Food & Snack

**Kelompok 3**

| Item | Keterangan |
|---|---|
| Mata kuliah | Rekayasa Perangkat Lunak (RPL) |
| Proyek | Aplikasi Web E-Commerce Frozen Food & Snack |
| Kelompok | 3 |
| Anggota | Achmad Zaky Mulyana (202343501777) · Regi Rianto Suyono (202343501754) · Ganang Ardi Pratama (202343501804) |
| Tech stack | Next.js (App Router), Tailwind CSS, Prisma ORM, MySQL |
| Lingkup N1 | Object Diagram |
| Status | **100% N1** |
| Tanggal rekap | 7 November 2026 |

---

## 1. Ringkasan Eksekutif

Proyek ini membangun aplikasi web e-commerce **mobile-first** untuk toko makanan
frozen food dan snack. Sistem melayani dua aktor:

- **Pelanggan (CUSTOMER):** registrasi, login, katalog, keranjang, checkout,
  dan riwayat pesanan.
- **Admin (ADMIN):** dashboard, CRUD produk, pemrosesan status pesanan, dan
  daftar pelanggan.

Hasil rekayasa perangkat lunak yang sudah tersedia:

| Ringkasan | Jumlah |
|---|---|
| Fitur sistem (SRS Bagian 4) | 9 fitur |
| Aktor | 2 aktor |
| Use case | 29 use case |
| Sequence diagram | 29 halaman (SD-01 s.d. SD-29) |
| Class domain | 6 class + 2 enumeration |
| Relasi class diagram | 8 relasi |
| Object diagram | 2 snapshot, 9 objek unik, 10 link |

Seluruh artefak inti konsisten: use case menjadi dasar sequence diagram,
sequence diagram memakai class domain yang sama, dan object diagram
menampilkan instance nyata dari class tersebut.

---

## 2. Capaian Artefak

| No | Artefak | Berkas | Ringkasan | Status |
|---|---|---|---|---|
| 1 | SRS | [`srs/SRS Aplikasi Web E-Commerce Frozen Food & Snack.docx`](./srs/SRS%20Aplikasi%20Web%20E-Commerce%20Frozen%20Food%20%26%20Snack.docx) | 9 fitur, kebutuhan fungsional AUTH/CAT/CART/CHK/ORD/DSH/PRD/TRX/CUS | ✅ 100% |
| 2 | Use Case Diagram | [`diagram-usecase/use-case-diagram.drawio`](./diagram-usecase/use-case-diagram.drawio) | 29 use case, 14 association, 6 `«include»`, 11 `«extend»` | ✅ 100% |
| 3 | Activity Diagram | [`Activity_Diagram_Frozen_Food_Snack_Ecommerce.pdf`](./Activity_Diagram_Frozen_Food_Snack_Ecommerce.pdf) | Alur proses bisnis utama | ✅ 100% |
| 4 | Sequence Diagram | [`diagram-sequence/sequence-diagram.drawio`](./diagram-sequence/sequence-diagram.drawio) | 29 halaman, satu diagram per use case | ✅ 100% |
| 5 | Class Diagram | [`diagram-class/class-diagram.drawio`](./diagram-class/class-diagram.drawio) | 6 class, 2 enum, 8 relasi | ✅ 100% |
| 6 | Object Diagram | [`diagram-object/object-diagram.drawio`](./diagram-object/object-diagram.drawio) | 2 snapshot, 9 objek unik, 10 link | ✅ 100% |

**Kelengkapan artefak inti: 6/6 (100%).**

> Catatan: State Machine Diagram dan ERD tercatat sebagai TBD pada Lampiran B
> SRS dan tidak termasuk paket N1 ini. Keduanya dapat ditambahkan pada tahap
> perancangan berikutnya.

---

## 3. Ruang Lingkup Fungsional

| No | Fitur (SRS) | Use case | Sequence | Kebutuhan utama |
|---|---|---|---|---|
| 1 | Autentikasi | 3 | SD-01 s.d. SD-03 | AUTH-1 s.d. AUTH-10 |
| 2 | Katalog Produk | 3 | SD-04 s.d. SD-06 | CAT-1 s.d. CAT-5 |
| 3 | Keranjang Belanja | 4 | SD-07 s.d. SD-10 | CART-1 s.d. CART-7 |
| 4 | Checkout dan Pembuatan Pesanan | 3 | SD-11 s.d. SD-13 | CHK-1 s.d. CHK-8 |
| 5 | Riwayat Pesanan | 2 | SD-14 s.d. SD-15 | ORD-1 s.d. ORD-4 |
| 6 | Dashboard Admin | 5 | SD-16 s.d. SD-20 | DSH-1 s.d. DSH-5 |
| 7 | Manajemen Produk | 4 | SD-21 s.d. SD-24 | PRD-1 s.d. PRD-6 |
| 8 | Manajemen Transaksi | 3 | SD-25 s.d. SD-27 | TRX-1 s.d. TRX-6 |
| 9 | Manajemen Pelanggan | 2 | SD-28 s.d. SD-29 | CUS-1 s.d. CUS-4 |
| | **Total** | **29** | **29** | |

### Aktor dan hak akses

| Aktor | Peran | Fitur |
|---|---|---|
| Pelanggan | `CUSTOMER` | Autentikasi, katalog, keranjang, checkout, riwayat pesanan |
| Admin | `ADMIN` | Dashboard, manajemen produk, manajemen transaksi, manajemen pelanggan |

Pembedaan peran ditegakkan di sisi server (AUTH-7, AUTH-8, SEC-5), bukan hanya
dengan menyembunyikan elemen UI.

---

## 4. Traceability Ringkas

| Fitur | Artefak analisis | Artefak desain |
|---|---|---|
| Autentikasi | Use case Registrasi, Login, Logout | Sequence SD-01..03; class `User`, enum `Role` |
| Katalog | Use case Katalog, Detail, Cari/Filter | Sequence SD-04..06; class `Product` |
| Keranjang | Use case Lihat, Tambah, Ubah, Hapus | Sequence SD-07..10; class `CartItem`, `Product` |
| Checkout | Use case Checkout, Alamat, Konfirmasi | Sequence SD-11..13; class `Order`, `OrderItem`, `ShippingAddress` |
| Riwayat Pesanan | Use case Riwayat, Detail Pesanan Saya | Sequence SD-14..15; class `Order`, `OrderItem` |
| Dashboard | Use case Dashboard + 4 ringkasan | Sequence SD-16..20; agregasi `Order`, `User`, `Product` |
| Manajemen Produk | Use case Daftar, Tambah, Ubah, Hapus | Sequence SD-21..24; class `Product` |
| Manajemen Transaksi | Use case Semua Pesanan, Detail, Ubah Status | Sequence SD-25..27; class `Order`, `OrderItem` |
| Manajemen Pelanggan | Use case Daftar Pelanggan, Jumlah Pesanan | Sequence SD-28..29; class `User`, `Order` |

---

## 5. Object Diagram — N1

**File:** [`diagram-object/object-diagram.drawio`](./diagram-object/object-diagram.drawio)
**Dokumentasi:** [`diagram-object/README.md`](./diagram-object/README.md)

Object diagram melengkapi class diagram dengan menunjukkan **snapshot
instance** pada satu titik waktu: objek apa yang ada, nilai atributnya, dan
link yang menghubungkannya.

| Snapshot | Objek | Fokus |
|---|---|---|
| OD-1 Keranjang | `rani: User`, `ci1`/`ci2: CartItem`, `p1`/`p2: Product` | Keadaan sebelum checkout; subtotal Rp75.000 |
| OD-2 Pesanan | `rani: User`, `ord1: Order`, `addr1: ShippingAddress`, `oi1`/`oi2: OrderItem`, `p1`/`p2: Product` | Pesanan ORD-001 berstatus DIKIRIM; total Rp75.000 |

### Checklist N1

| Kriteria | Bukti | Status |
|---|---|---|
| Instance untuk setiap class domain | 6/6 class muncul: `User`, `Product`, `CartItem`, `Order`, `OrderItem`, `ShippingAddress` | ✅ 100% |
| Nilai atribut terisi | Setiap objek memiliki slot value yang konsisten | ✅ 100% |
| Link antar objek | 10 instance link sesuai association/composition | ✅ 100% |
| Konsistensi ID | `userId`, `productId`, `orderId` saling cocok | ✅ 100% |
| Snapshot bermakna | OD-1 keranjang dan OD-2 pesanan | ✅ 100% |
| Dokumentasi | README + dua pratinjau PNG | ✅ 100% |
| **Total** | | **✅ 100% N1** |

### Konsistensi dengan class diagram

| Objek | Class | Link |
|---|---|---|
| `rani` | `User` | ke `ci1`, `ci2`, dan `ord1` |
| `ci1`, `ci2` | `CartItem` | ke `rani` dan `p1`/`p2` |
| `ord1` | `Order` | ke `rani`, `addr1`, `oi1`, `oi2` |
| `oi1`, `oi2` | `OrderItem` | ke `ord1` dan `p1`/`p2` |
| `addr1` | `ShippingAddress` | ke `ord1` |
| `p1`, `p2` | `Product` | ke `ci1`/`ci2` dan `oi1`/`oi2` |

Nilai `oi2.hargaSatuan = 25000` sengaja berbeda dari `p2.harga = 26000` untuk
menunjukkan aturan **BR-5**: harga pada item pesanan adalah snapshot saat
checkout, bukan harga produk saat ini.

---

## 6. Catatan Teknis dan Kualitas

| Aspek | Implementasi | Rujukan |
|---|---|---|
| Autentikasi | Sesi berbasis cookie HTTP-only; kata sandi di-hash (bcrypt + salt) | AUTH-4, AUTH-6, SEC-1, SEC-4 |
| Otorisasi | Pemeriksaan peran `CUSTOMER`/`ADMIN` di server | AUTH-7, AUTH-8, SEC-5 |
| Checkout | Satu transaksi database: buat Order + OrderItem, kurangi stok, kosongkan keranjang | CHK-3, CHK-6, CHK-7, SAF-1 |
| Harga pesanan | Snapshot `namaProduk` dan `hargaSatuan` pada OrderItem | CHK-3, BR-5 |
| Stok | Dikurangi dalam transaksi yang sama; gagal total jika stok kurang | CHK-6, BR-4 |
| Status pesanan | Satu arah: `PENDING → DIPROSES → DIKIRIM → SELESAI` | BR-2, BR-3, TRX-3, TRX-4 |
| Hapus produk | Soft-delete dengan `deletedAt` agar riwayat pesanan aman | PRD-4 |
| Keranjang | Tersimpan per akun di database | CART-7 |
| Tampilan | Mobile-first, lebar maksimum saat dibuka di desktop | UI-1, OE-3 |
| Kualitas | Transaksi konsisten, validasi server, escaping output | SQA-5, SEC-2, SEC-3 |

---

## 7. Kesimpulan

1. Seluruh artefak inti RPL tersedia: SRS, use case, activity, sequence,
   class, dan object diagram.
2. Object diagram N1 selesai **100%**: dua snapshot, 9 objek unik, 10 link,
   dan seluruh class domain terwakili.
3. Diagram konsisten dengan SRS dan class diagram, termasuk aturan snapshot
   harga (BR-5) serta pengosongan keranjang setelah checkout (CHK-7).
4. Dengan demikian, paket **N1 — Object Diagram** dinyatakan lengkap dan siap
   dilampirkan pada laporan proyek RPL Kelompok 3.
