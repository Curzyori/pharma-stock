# 💊 PharmaStock (V1.0.0) — Sistem Manajemen Inventaris & Keuangan Apotek

<p align="center">
  <img src="images/logo.svg" alt="PharmaStock Logo" width="120"/>
</p>

<h1 align="center">PharmaStock</h1>
<p align="center">
  <strong>Sistem Manajemen Inventaris & Keuangan Apotek</strong>
</p>

<p align="center">
  <a href="https://pharma-stock.curzy.dev/"><strong>🌐 Live Demo</strong></a>
</p>

<div align="center">

[![Stars](https://img.shields.io/github/stars/Curzyori/pharma-stock?style=for-the-badge&color=emerald)](https://github.com/Curzyori/pharma-stock/stargazers)
[![Forks](https://img.shields.io/github/forks/Curzyori/pharma-stock?style=for-the-badge&color=emerald)](https://github.com/Curzyori/pharma-stock/network/members)
[![License](https://img.shields.io/badge/License-Proprietary-red?style=for-the-badge)](#license)
[![Platform](https://img.shields.io/badge/Platform-Web%20%7C%20Commercial-black?style=for-the-badge)](#)

</div>

<p align="center">
  <a href="#-masalah">Masalah</a> ·
  <a href="#-fitur-unggulan">Fitur</a> ·
  <a href="#-tech-stack">Tech Stack</a> ·
  <a href="#-struktur">Struktur</a> ·
  <a href="#-demo">Demo</a>
</p>

---

## 🕒 Apa Itu PharmaStock?

PharmaStock adalah sistem manajemen inventaris dan keuangan farmasi berbasis web yang dirancang khusus untuk pemilik apotek, kepala gudang, dan apoteker.

### Masalah yang Diselesaikan

| Masalah | Dampak |
|--------|--------|
| Pencatatan stok manual (buku/Excel) | Selisih stok fisik yang sulit dilacak |
| Tidak ada deteksi dini expired | Obat kedaluwarsa tidak terdeteksi |
| Owner tidak punya visibility omset real-time | Kebocoran data finansial |
| Staff bisa lihat data sensitif | Margin keuntungan terbuka |

### Solusi

PharmaStock menyediakan **Dashboard Finansial Otomatis**, **Deteksi Stok Kritis & Near-Expiry**, **Pelacakan No. Batch**, **Kalkulasi PPN/PPh Otomatis**, dan **Isolasi Data Multi-Role (RBAC + RLS)**.

---

## 🎯 Fitur Unggulan

| Fitur | Status | Deskripsi |
| :--- | :---: | :--- |
| **Dashboard Finansial** | ✅ | Total omset, margin, grafik real-time untuk Owner |
| **Deteksi Stok Kritis** | ✅ | Otomatis tandai produk di bawah ambang batas |
| **Deteksi Near-Expiry** | ✅ | Obat kedaluwarsa dalam 90 hari ditandai |
| **Pelacakan Batch & Expired** | ✅ | No. Bets + Expiry Date sesuai standar farmasi |
| **Kalkulator PPN & PPh** | ✅ | PPN 11% & PPh 22 otomatis saat input transaksi |
| **Isolasi Multi-Role (RBAC + RLS)** | ✅ | Owner, Apoteker, Gudang dengan akses terpisah |
| **Activity Log** | ✅ | Setiap transaksi tercatat dengan timestamp & user |
| **Responsif Mobile & Desktop** | ✅ | Optimasi untuk staff lapangan & kasir |

---

## 🛠️ Tech Stack

| Layer | Teknologi | Alasan |
| :---- | :-------- | :------ |
| **Frontend** | Next.js 16, TypeScript, Tailwind CSS | SSR, type-safety, optimasi bundle |
| **Backend** | Next.js Server Actions & Route Handlers | Satu wadah dengan frontend |
| **Database** | Supabase (PostgreSQL 17) | Row Level Security 100% |
| **State** | SWR | Fetching real-time hemat bandwidth |
| **Export** | jsPDF + jspdf-autotable | Export PDF laporan langsung dari dashboard |

---

## 🏗️ Struktur Proyek

```
PharmaStock/
├── public/                  # Aset statis logo & ikon
├── src/
│   ├── app/               # Next.js App Router
│   │   ├── api/           # Route Handlers (REST API)
│   │   ├── karyawan/      # Manajemen karyawan (Admin)
│   │   ├── kategori/     # Kelola kategori produk
│   │   ├── keluar/       # Transaksi barang keluar
│   │   ├── masuk/         # Transaksi barang masuk
│   │   ├── produk/        # Katalog produk
│   │   ├── laporan/       # Dashboard finansial + logs
│   │   └── login/         # Autentikasi multi-role
│   ├── components/         # Komponen UI reusable
│   ├── lib/               # Helper, util, Supabase client
│   └── types/             # TypeScript definitions
├── supabase/migrations/   # Skrip migrasi SQL
└── package.json
```

---

## 🔑 Akun Demo (Sandbox)

| Peran | Username | Password | Hak Akses |
|-------|----------|----------|-----------|
| **Admin (Owner)** | `admin` | `Curzy7Day#` | Dashboard finansial, karyawan, semua laporan |
| **Apoteker** | `apoteker1` | `Curzy7Day#` | Stok kritis, katalog, barang keluar, kalkulator |
| **Gudang** | `gudang1` | `Curzy7Day#` | Stok kritis, katalog, barang masuk, kalkulator |

> ⚠️ *Akun demo hanya untuk simulasi. Data dapat di-reset sewaktu-waktu.*

---

## 🖼️ Preview

<!-- Tambah preview dengan screenshot/gif aplikasi -->

---

## 📦 Lisensi

**PharmaStock** adalah produk komersial. Lisensi selengkapnya tersedia di [`LICENSE`](./LICENSE).

### Ketentuan Utama:

| Ketentuan | Detail |
|----------|--------|
| **Penggunaan** | Diperbolehkan untuk operasional apotek sendiri |
| **Modifikasi** | Diperbolehkan untuk kebutuhan internal |
| **Dilarang** | Menjual ulang, membagikan, atau mempublikasikan ulang kode |
| **Logo & Nama** | **TIDAK BOLEH** diganti atau dihapus |
| **Kepemilikan** | Seluruh hak cipta milik @Curzyori (Yuken Velino) |

---

## 💰 Pembelian & Kontak

PharmaStock adalah produk komersial. Untuk informasi harga dan pembelian:

| Kontak | Detail |
|--------|--------|
| **WhatsApp** | [Hubungi via WhatsApp](https://wa.me/6285141495185) |
| **GitHub** | [@Curzyori](https://github.com/Curzyori) |
| **Portfolio** | [curzy.dev](https://curzy.dev) |

---

## 👤 Pengembang

Dikembangkan dan dilindungi hak cipta oleh:

**@Curzyori (Yuken Velino)**
*Founder & Lead Engineer — Curzy*

---

<sub>Built with passion as the 14th Project of the <strong>50 Projects Challenge</strong> by <strong>@curzyori</strong></sub>
