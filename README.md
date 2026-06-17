# 💊 PharmaStock (V1.0.0) — Sistem Manajemen Inventaris & Keuangan Apotek

<div align="center">

<img src="https://img.shields.io/badge/Challenge%20Project-14%20%2F%2050-58A6FF?style=for-the-badge&logo=github&logoColor=white" />
<img src="https://img.shields.io/badge/Next.js%2016-000000?style=for-the-badge&logo=next.js&logoColor=white" />
<img src="https://img.shields.io/badge/Supabase-3ECF8E?style=for-the-badge&logo=supabase&logoColor=white" />
<img src="https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge&logo=typescript&logoColor=white" />
<img src="https://img.shields.io/badge/Status-Commercial%20Product-10b981?style=for-the-badge&logo=shopify&logoColor=white" />

</div>

---

### 📋 Mini Formula Project
**PharmaStock** adalah **Sistem Manajemen Inventaris & Keuangan Farmasi** berbasis web yang dirancang khusus untuk **pemilik apotek, kepala gudang, dan apoteker** guna **mengatasi permasalahan pencatatan stok manual, kebocoran data omset, dan keterlambatan deteksi obat kedaluwarsa** lewat fitur **Dashboard Finansial Otomatis, Notifikasi Stok Kritis, Pelacakan No. Batch & Expired, serta Isolasi Data Multi-Role (RBAC + RLS)**. Dibangun menggunakan **Next.js 16, TypeScript, dan Supabase (PostgreSQL 17)** karena **kebutuhan akan Single Enterprise Architecture yang ringan, responsif di mobile, dan memiliki Row Level Security 100% untuk memisahkan data Owner, Apoteker, dan Staff Gudang**.

> **🏷️ Catatan Penting — Mirror / Shadow Repository**
>
> *Berkas ini merupakan **Mirror / Shadow Repository** dari **PharmaStock (Project Challenge 14/50)** yang sengaja disediakan secara publik untuk menampilkan dokumentasi arsitektur, bagan alur kerja, cetak biru struktur folder, dan Ketentuan Lisensi Komersial secara transparan. **Kode sumber inti (Core Engine) tidak disertakan** dalam repositori ini dan disimpan aman di repositori privat demi melindungi hak cipta kekayaan intelektual, kredensial API, dan skema basis data produksi.*

---

## 🌐 Live Production Demo
Aplikasi telah dikompilasi ke level *Production-Ready Build* dan berjalan live di server pribadi Curzy:

* **🔗 URL Aplikasi Live:** [https://pharma-stock.curzy.dev/](https://pharma-stock.curzy.dev/)

### 🔑 Akun Tes (Sandbox Demo)

| Peran | Username | Password | Hak Akses |
|-------|----------|----------|-----------|
| **Admin (Owner)** | `admin` | `Curzy7Day#` | Akses penuh: dashboard finansial, karyawan, semua laporan |
| **Apoteker** | `apoteker1` | `Curzy7Day#` | Stok kritis, katalog, barang keluar, kalkulator |
| **Gudang** | `gudang1` | `Curzy7Day#` | Stok kritis, lihat katalog, barang masuk, kalkulator |

> ⚠️ *Akun staff di atas **hanya untuk simulasi**. Data dapat di-reset sewaktu-waktu oleh admin.*

---

## 📝 Deskripsi Singkat & Solusi Masalah
Banyak apotek kecil hingga menengah masih mengandalkan pencatatan stok di buku tulis atau spreadsheet terpisah yang sering kali tidak sinkron. Kondisi ini memicu kerugian akibat selisih stok, obat kedaluwarsa yang tidak terdeteksi, serta kebocoran omset karena tidak ada isolasi data antara owner dan staff.

### 🧠 Masalah yang Diselesaikan:
1. **Pencatatan Manual yang Rawan Error:** Buku tulis atau Excel terpisah menyebabkan selisih stok fisik dan catatan yang sulit dilacak ulang.
2. **Tidak Ada Deteksi Dini Stok Kritis & Expired:** Obat yang akan kedaluwarsa atau stok di bawah ambang batas sering tidak terdeteksi sampai pelanggan kecewa.
3. **Kebocoran Data Finansial:** Owner tidak punya visibility omset real-time, sementara staff lapangan tidak boleh melihat margin keuntungan dan laporan sensitif.
4. **Kalkulasi Pajak yang Memakan Waktu:** Perhitungan PPN 11% & PPh Pasal 22 untuk obat tertentu sering keliru hitung saat input transaksi.

### ✨ Solusi & Fitur Unggulan PharmaStock:
* **Dashboard Finansial Otomatis:** Owner dapat melihat total omset, margin, dan grafik pergerakan barang masuk-keluar secara real-time.
* **Deteksi Stok Kritis & Near-Expiry:** Sistem otomatis menandai produk dengan stok di bawah ambang batas dan obat yang akan kedaluwarsa dalam 90 hari ke depan.
* **Pelacakan Nomor Batch & Tanggal Kedaluwarsa:** Setiap obat wajib menyertakan **No. Bets** dan **Expiry Date** sesuai standar regulasi farmasi.
* **Kalkulator PPN & PPh Otomatis:** Perhitungan PPN 11% dan PPh Pasal 22 langsung muncul saat input transaksi, tanpa kalkulator manual.
* **Isolasi Data Multi-Role (RBAC + RLS):** Tiga peran (Owner, Apoteker, Gudang) dengan akses yang dipisah ketat lewat Supabase Row Level Security 100%.
* **Activity Log Transparan:** Setiap transaksi tercatat dengan timestamp, user, dan detail perubahan untuk audit internal.
* **Responsif Mobile & Desktop:** Tampilan optimal di smartphone untuk staff lapangan dan di desktop untuk owner di kasir/admin.

---

## 🛠️ Tech Stack & Alasan Pemilihan
* **Frontend:** **Next.js 16 (App Router)** + **TypeScript** + **Tailwind CSS**. Dipilih untuk performa server-side rendering, optimasi bundle, dan type-safety penuh agar minim bug di produksi.
* **Backend:** **Next.js Server Actions & Route Handlers (REST API)** yang berjalan satu wadah dengan frontend. Menghemat infrastruktur dan mempercepat waktu respon.
* **Database & Security:** **Supabase (PostgreSQL 17)** dengan **Row Level Security (RLS 100%)** berbasis `(select auth.uid())` untuk mencegah kebocoran data antar-role.
* **State Management:** **SWR** untuk fetching data real-time yang hemat bandwidth dan otomatis revalidate.
* **Export Laporan:** **jsPDF** + **jspdf-autotable** untuk export PDF laporan finansial dan stok langsung dari dashboard.
* **Desain:** Tema dark mode presisi (Zinc-950 canvas, Zinc-900 panel) dengan aksen Emerald/Amber/Rose untuk status — lihat `DESIGN.md` untuk detail sistem desain.

---

## 🏗️ Struktur Folder Proyek (Architecture Blueprints)
Berikut adalah pohon direktori dari basis kode **PharmaStock (Challenge 14/50)** yang merepresentasikan seluruh modul, API route, middleware keamanan, hingga konfigurasi skema database:

```text
PharmaStock/
├── public/                        # Aset statis logo & ikon aplikasi
├── src/
│   ├── app/                       # Next.js App Router (server-first)
│   │   ├── api/                   # Route Handlers (REST API endpoints)
│   │   │   ├── auth/
│   │   │   │   ├── login/route.ts
│   │   │   │   └── logout/route.ts
│   │   │   ├── inventory/
│   │   │   │   └── low-stock/route.ts
│   │   │   ├── karyawan/
│   │   │   │   └── create/route.ts   # Admin-only: daftarkan karyawan baru
│   │   │   └── produk/
│   │   │       └── create/route.ts   # Tambah produk baru
│   │   ├── karyawan/              # Halaman & form manajemen karyawan (Admin)
│   │   ├── kategori/              # Halaman kelola kategori produk
│   │   ├── keluar/                # Halaman transaksi barang keluar
│   │   │   └── tambah/            # Form input penjualan
│   │   ├── laporan/               # Dashboard finansial (Admin only)
│   │   │   ├── analytics/
│   │   │   └── logs/              # Activity log semua transaksi
│   │   ├── login/                 # Halaman autentikasi multi-role
│   │   ├── masuk/                 # Halaman transaksi barang masuk
│   │   ├── produk/                # Katalog produk + form tambah
│   │   ├── setting/               # Pengaturan profil & preferensi
│   │   ├── error.tsx
│   │   ├── globals.css            # Tailwind core + tema Zinc-950
│   │   ├── layout.tsx             # Root layout + Auth Provider
│   │   ├── loading.tsx
│   │   ├── not-found.tsx
│   │   └── page.tsx               # Landing / redirect sesuai role
│   ├── components/                # Komponen UI reusable
│   ├── lib/                       # Helper, util, & Supabase client
│   ├── types/                     # TypeScript type definitions
│   └── proxy.ts                   # Edge middleware (auth guard)
├── supabase/
│   └── migrations/                # Skrip migrasi skema SQL otomatis
├── .env.example                   # Template variabel lingkungan
├── next.config.ts
├── package.json
├── tailwind.config.ts
└── tsconfig.json
```

---

## 🔄 Alur Kerja Sistem (System Usage Flow)
Arsitektur PharmaStock dirancang untuk meminimalkan klik dan memberikan visibilitas penuh ke owner sambil membatasi akses staff ke data sensitif:

```text
[ Pengguna ]
     │
     ├──► Login di /login (Validasi via Supabase Auth + RLS)
     │   │
     │   ├── Role: admin        ──► Redirect ke Dashboard Finansial (/laporan)
     │   ├── Role: apoteker     ──► Redirect ke Dashboard Stok Kritis
     │   └── Role: gudang       ──► Redirect ke Input Barang Masuk (/masuk)
     │
     ├──► Input Barang Masuk / Keluar
     │   │
     │   ├─► Produk dipilih dari katalog
     │   ├─► Sistem otomatis hitung PPN 11% & PPh 22 (jika applicable)
     │   ├─► Validasi: No. Bets + Expiry Date wajib diisi (produk farmasi)
     │   └─► Transaksi tersimpan + tercatat di Activity Log
     │
     ├──► Deteksi Otomatis
     │   │
     │   ├─► Stok < ambang batas  ──► Badge Amber di dashboard
     │   ├─► Expired < 90 hari    ──► Badge Rose + notifikasi
     │   └─► Update low-stock view di PostgreSQL
     │
     └──► Owner Membuka Dashboard Finansial
         │
         ├─► Total omset, margin, grafik 30 hari terakhir
         ├─► Export PDF laporan (jsPDF + autotable)
         └─► Lihat Activity Log semua staff (audit trail)

[ Sirkuit Keamanan Belakang Layar ]
     │
     ├──► Setiap request ──► proxy.ts cek session cookie
     │
     ├──► Query Supabase ──► RLS policy enforce role
     │   (Admin baca semua, Apoteker/Gudang hanya baca sesuai role)
     │
     └──► Transaksi gagal validasi ──► Rollback + tampilkan error
```

---

## 🛡️ Lisensi & Ketentuan Penggunaan Komersial
**Lisensi: Proprietary / Komersial Terbatas.**

PharmaStock adalah **produk komersial** yang dijual kepada pengguna akhir. Pembeli **diperbolehkan** menggunakan dan memodifikasi sistem untuk kebutuhan operasional apoteknya sendiri, namun **dilarang keras** menjual ulang, membagikan, mempublikasikan, atau mendistribusikan ulang kode sumber dalam bentuk apa pun tanpa izin tertulis dari pemilik hak cipta.

Seluruh ketentuan lengkap tersedia di berkas [`LICENSE`](./LICENSE) pada repositori ini. Pembelian produk ini mengindikasikan persetujuan otomatis terhadap seluruh klausul yang tercantum di dalamnya.

---

## 👤 Pengembang & Penandatangan Resmi
Dikembangkan, dimiliki, dan dilindungi hak cipta oleh:

**@Curzyori (Yuken Velino)**
*Founder & Lead Engineer — Curzy*
*Indonesia, 2026*

> Segala bentuk pelanggaran terhadap lisensi ini akan ditindaklanjuti sesuai hukum yang berlaku di Republik Indonesia, termasuk namun tidak terbatas pada **UU Hak Cipta No. 28 Tahun 2014** dan **UU ITE No. 19 Tahun 2016**.
