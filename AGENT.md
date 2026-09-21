# 🍔 Frozen Food & Snack E-Commerce - AI Vibe Coding Prompt

## 📌 Project Overview

Buatkan sistem pemesanan makanan frozen dan snack berbasis web. Sistem ini melayani dua jenis pengguna: **Customer** (untuk berbelanja) dan **Admin** (untuk mengelola operasional toko). Aplikasi hanya tampilan mobile version saja dengan menggunakan max width jika di buka di desktop, cepat, dan memiliki UI/UX yang modern serta menggugah selera.

## 🛠️ Tech Stack

- **Framework:** Next.js (App Router)
- **Styling:** Tailwind CSS (dengan komponen modern, bisa gunakan shadcn/ui jika memungkinkan)
- **Database:** MySQL
- **ORM:** Prisma (agar lebih mudah berinteraksi dengan MySQL di Next.js)

## 👤 User Roles & Core Features

### 1. Customer (Pelanggan)

- **Authentication:** Register & Login.
- **Katalog Produk:** Melihat daftar makanan frozen dan snack (grid view dengan gambar, harga, dan tombol _add to cart_).
- **Keranjang Belanja (Cart):** Menambah, mengurangi, dan menghapus produk dari keranjang.
- **Checkout:** Mengisi alamat pengiriman dan menyelesaikan pesanan (status pesanan menjadi _Pending_).
- **Pesanan Saya:** Melihat riwayat transaksi.

### 2. Admin

- **Dashboard:** Melihat ringkasan (Total Pendapatan, Total Pesanan, Total Pelanggan).
- **Manajemen Produk:** CRUD (Create, Read, Update, Delete) data makanan frozen & snack (Nama, Deskripsi, Harga, Stok, Gambar).
- **Manajemen Transaksi:** Melihat daftar pesanan masuk dan mengubah status pesanan (Pending -> Diproses -> Dikirim -> Selesai).
- **Manajemen Pelanggan:** Melihat daftar pelanggan terdaftar.

---
