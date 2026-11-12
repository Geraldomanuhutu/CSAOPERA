# OPERA – Demo alur CSA ICoFR

Prototype web statis untuk alur CSA ICoFR di OPERA: Lini 2 menyiapkan proses bisnis, RCM, dan template kontrol, lalu dispatch kertas kerja; Lini 1 mengisi dan submit; Lini 2 memvalidasi (setujui atau kembalikan untuk revisi); hasilnya masuk dashboard.

Semua data contoh. Tidak ada backend, tidak ada build step.

## Jalankan di laptop

Buka `index.html` di browser, atau jalankan server lokal:

```bash
npx serve .
```

## Deploy ke Vercel

1. Push folder ini ke repository GitHub.
2. Di Vercel: **Add New → Project → Import** repository tersebut.
3. Framework Preset: **Other**. Build Command: kosong. Output Directory: `.` (root).
4. **Deploy**.

Routing pakai hash (`#/...`), jadi tidak perlu konfigurasi rewrite.

## Cara demo

Mulai dari halaman masuk, pilih akun **Lini 2 (Rina Pratama)**, lalu ikuti tombol utama tiap layar. Tombol **Ganti ke akun Lini 1/2** di kanan atas memindahkan peran sesuai urutan cerita. Di layar validasi, tandai satu atribut "Tidak sesuai" untuk melihat tombol Setujui hilang, atau klik **Kembalikan ke Lini 1** untuk jalur revisi.

## Daftar layar

| Rute | Layar |
|---|---|
| `#/` | Masuk |
| `#/proses-bisnis/tambah` | Tambah proses bisnis ICoFR |
| `#/proses-bisnis` | Proses bisnis ICoFR |
| `#/rcm` | RCM ICoFR |
| `#/rcm/tambah` | Input RCM ICoFR |
| `#/rcm/tersimpan` | RCM ICoFR |
| `#/template-kontrol` | Template kontrol CSA |
| `#/csa` | Control Self Assessment |
| `#/csa/new-assessment` | New Assessment |
| `#/csa/terkirim` | Control Self Assessment |
| `#/lini1/tugas` | Tugas CSA saya |
| `#/lini1/kertas-kerja` | Kertas kerja CSA |
| `#/lini1/tugas/terkirim` | Tugas CSA saya |
| `#/csa/antrian` | Control Self Assessment |
| `#/csa/validasi` | Validasi kertas kerja CSA |
| `#/csa/disetujui` | Control Self Assessment |
| `#/csa/dikembalikan` | Control Self Assessment |
| `#/lini1/tugas/revisi` | Tugas CSA saya |
| `#/lini1/kertas-kerja/revisi` | Revisi kertas kerja CSA |
| `#/lini1/tugas/terkirim-ulang` | Tugas CSA saya |
| `#/csa/antrian-revisi` | Control Self Assessment |
| `#/dashboard` | Dashboard ICoFR |

## Struktur

- `index.html` — kerangka halaman
- `assets/app.js` — router
- `assets/runtime.js` — renderer template
- `assets/screens.js` — template, gaya, dan logika tiap layar
