# Portfolio — Nabil Alfahmi Labib

Interactive Engineering Workspace: portfolio berbasis view (bukan scroll panjang) dengan sidebar navigasi, Projects dalam tampilan List + Detail, dan lightbox gambar.
Dibuat dengan HTML, CSS, dan JavaScript murni (tanpa framework dan tanpa build tool), sehingga langsung bisa dipublikasikan di GitHub Pages.

## Struktur File

```
.
├── index.html      # Seluruh website (HTML + CSS + JS)
├── README.md
└── assets/         # Gambar (buat folder ini sendiri)
    ├── foto-profil.jpg
    ├── 01-layout-1.jpg ... -2 ... -3            -> Project 01 Production Layout
    ├── 04-equipment-1.jpg ... -2 ... -3         -> Project 02 Equipment
    ├── 05-warehouse-1.jpg ... -2 ... -3         -> Project 03 Warehouse & QCC
    ├── 03-vsm-1.jpg ... -2 ... -3               -> Project 04 VSM
    └── 02-dashboard-1.jpg ... -2 ... -3         -> Project 05 Dashboard
```

Format JPG, PNG, JPEG, dan WEBP dibaca otomatis (cukup samakan nama dasarnya). Nama file gambar tidak diubah dari versi sebelumnya, sehingga gambar yang sudah Anda upload tetap terbaca. Nomor project yang tampil di website mengikuti urutan tampil (01–05), sedangkan nama file mengikuti penamaan lama.

## Arsitektur Navigasi

Website memakai routing hash ringan, sehingga tombol Back dan Forward browser berfungsi:

| URL | Tampilan |
|---|---|
| `#/overview` | Overview (intro, foto, aksi utama) |
| `#/projects` | Daftar project + detail project pertama |
| `#/projects/layout` | Detail project tertentu (`layout`, `equipment`, `warehouse`, `vsm`, `dashboard`) |
| `#/experience`, `#/skills`, `#/about`, `#/contact` | View lainnya |

- **Desktop:** sidebar tetap di kiri (bisa diciutkan), Projects tampil terbagi dua (daftar dan detail).
- **Tablet:** sidebar otomatis berupa ikon; daftar dan detail project tampil bergantian.
- **Mobile:** navigasi bawah, daftar project dan detail project berupa dua layar dengan tombol "Back to Projects".
- Filter project (All, Applied in Workplace, Team Project, Academic Project) tetap terjaga saat berpindah project atau menekan tombol Back.

## Mengganti Konten

Teks project ada di `index.html`, pada `const P=[` di dalam tag `<script>`. Setiap project berisi `t` (judul), `cat`, `st` (status), `k` (`work`, `team`, atau `academic`), `d` (deskripsi di daftar), `img` (tiga path gambar), dan `s` (isi detail). Bagian pada `s` yang tidak ada, atau yang berisi teks "Belum ada data", tidak ditampilkan kepada pengunjung.

Teks Overview, Experience, Skills, About, dan Contact ditulis langsung sebagai HTML di dalam tag `<main>`. Warna ada di `:root` pada bagian CSS (`--blue` #155687, `--navy`).

## Menambahkan Gambar

1. Buat folder `assets/` di samping `index.html`.
2. Simpan gambar dengan nama seperti tabel di atas.
3. Upload folder `assets` ke repository GitHub.

Saran: foto profil rasio 4:5 (sekitar 800 x 1000 px). Gambar project dibingkai A4 landscape (297:210) dan ditampilkan utuh. Kompres hingga di bawah 300 KB per gambar. Klik gambar di detail project untuk membuka preview besar; di dalam preview gunakan tombol panah atau keyboard.

## Deploy ke GitHub Pages

1. Upload `index.html`, `README.md`, dan folder `assets` ke repository (pilih Replace untuk file yang sama).
2. Buka **Settings, Pages**, pilih **Deploy from a branch**, Branch `main`, folder `/ (root)`, lalu **Save**.
3. Tunggu 1–2 menit, lalu buka website dan tekan Ctrl+F5.

## Kerahasiaan Dokumen

Sensor nama pelanggan, kode part, data produksi internal, dan detail fasilitas sebelum mengunggah gambar. Repository public bisa dilihat siapa saja.
