# Kastrat — Kajian & Aksi Strategis BEM FTI

Kastrat adalah **portal informasi dan kanal aspirasi organisasi mahasiswa** untuk
Departemen Kajian dan Aksi Strategis (Kastrat) BEM FTI. Website ini bukan hanya
landing page: pengunjung dapat membaca arsip kajian, melihat program kerja, dan
mengirimkan aduan mahasiswa melalui formulir yang terdokumentasi.

## Fitur

- Halaman publik dengan profil Kastrat BEM FTI, arsip kajian, dan program kerja.
- Detail kajian dalam modal.
- Kanal aduan umum dan aduan pemberdayaan perempuan.
- Dashboard admin untuk mengelola arsip kajian.
- Efek visual, animasi, dan pemutar audio untuk pengalaman editorial.

> **Status:** beberapa bagian masih berupa prototype. Arsip kajian di sisi
> frontend saat ini menggunakan `localStorage`, tab aduan dan program kerja di
> dashboard masih menampilkan data mockup, dan autentikasi admin belum cocok
> untuk deployment produksi.

## Teknologi

- React 18 dan Vite
- Tailwind CSS
- Framer Motion dan Lucide React
- Express.js dan Prisma dengan database SQLite untuk API

## Menjalankan frontend

Dari folder root proyek:

```bash
npm install
npm run dev
```

Frontend tersedia di `http://localhost:5173`.

## Menjalankan backend API

Backend memiliki `package.json` sendiri. Buka terminal kedua:

```bash
cd server
npm install
npm run db:push
npm start
```

API tersedia di `http://localhost:3000`.

Endpoint yang tersedia:

- `GET /api/studies` dan `POST /api/studies`
- `GET /api/complaints` dan `POST /api/complaints`
- `PATCH /api/complaints/:id/status`

### Data contoh (opsional)

Setelah database dibuat dengan `npm run db:push`, data contoh dapat dimasukkan
dari folder `server`:

```bash
node seed.js
node seed_complaints.js
```

## Struktur direktori

```text
src/                 Aplikasi React dan komponen UI
src/components/      Komponen halaman publik dan dashboard admin
src/context/         State arsip kajian berbasis React Context
src/data/             Data kajian mockup
server/               Express API, Prisma schema, dan SQLite database
public/               Asset statis
```

## Build produksi

```bash
npm run build
npm run preview
```
