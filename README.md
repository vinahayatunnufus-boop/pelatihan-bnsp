# Portal Manajemen & Informasi Tim

Aplikasi full-stack React + Express untuk mengelola anggota tim, barang dan kategori, serta menampilkan berita terkini. Backend menyimpan data ke MySQL.

## Teknologi

- Frontend: React, Vite, Tailwind CSS, dan Zod
- Backend: Node.js, Express, mysql2, dan Zod
- Database: MySQL

## Persiapan

Pastikan Node.js dan npm sudah terpasang. Untuk memakai fitur anggota/barang, nyalakan MySQL di Laragon.

Pasang dependency dari folder proyek:

```powershell
npm install
npm --prefix server install
```

Salin konfigurasi contoh dan sesuaikan dengan MySQL lokal:

```powershell
Copy-Item server\.env.example server\.env
```

Nilai bawaan pada `server/.env.example` cocok untuk Laragon dengan pengguna `root`, kata sandi kosong, dan port MySQL `3306`. Jangan bagikan atau commit `server/.env`.

## Menjalankan aplikasi

Jalankan sekali untuk membuat database, tabel, dan data contoh:

```powershell
npm run seed
```

Lalu buka dua terminal di folder proyek:

```powershell
npm run server
```

```powershell
npm run dev
```

Buka alamat frontend yang ditampilkan Vite (biasanya `http://localhost:5173`). API berjalan di `http://localhost:3000`; Vite meneruskan permintaan `/api` ke backend.

## Fitur

- Anggota tim: tambah, cari, edit, hapus, ubah status, dan beri bintang.
- Data barang: tambah, cari, edit, dan hapus barang serta mengelola kategori.
- Berita terkini: mengambil berita CNN Indonesia dari Berita Indo API.
- Validasi form di frontend dan backend.

## Perintah lain

| Perintah | Kegunaan |
| --- | --- |
| `npm run server:dev` | Menjalankan backend dengan pemantauan perubahan |
| `npm test` | Menjalankan tes frontend |
| `npm run test:server` | Menjalankan tes backend |
| `npm run lint` | Memeriksa kode dengan ESLint |
| `npm run build` | Membuat build produksi frontend |

Database dan tabel dibuat otomatis oleh backend. Perintah seed aman dijalankan berulang kali dan tidak menimpa data yang sudah ada.
