# GYVER STUDIO — Halaman Unduhan

Landing page statis (satu file HTML) untuk membagikan file Windows / Mac + donasi rekening & QRIS.

## Mengisi

Semua data ada di `index.html`, bagian `EDIT DI SINI`.

1. **Paket ZIP Windows**: isi `file` dan `size` tiap aplikasi di `PRODUCTS`. ZIP CueRundown 0.4.6 = 144 MB (`D:\CUERUNDOWN\release\CueRundown 0.4.6 - Paket.zip`); ZIP CueDirector 1.1.3 = 162 MB (`D:\CUEDIRECTOR\release\CueDirector 1.1.3 - Paket.zip`). File sebesar ini melebihi batas kebanyakan hosting gratis, jadi unggah ke **GitHub Releases** (maks. 2 GB per file) lalu isi `file` dengan link-nya. Path `files/...zip` sekarang hanya placeholder.
2. **Mac nanti**: di baris `mac`, hapus `soon: true` lalu isi `file` dan `size`.
3. **Versi baru**: ubah `version`, `file` dan `size`.
4. **Video**: `assets/video/<nama>.mp4` + poster `.jpg` (15 detik, dipotong dari video brag 60 detik di folder project masing-masing).
5. **Rekening**: `BANKS` (sudah berisi BCA). **QRIS**: simpan gambar sebagai `assets/qris.png`.
6. **Kontak**: bagian `<section ... h-contact>` di HTML.

## Menjalankan lokal

```bash
python -m http.server 5174 --directory "D:\GYVER STUDIO\download"
```

## Deploy gratis

Upload isi folder `download/` apa adanya (tanpa build):
- **Netlify Drop**: seret folder ke https://app.netlify.com/drop
- **Vercel**: `vercel deploy` dari folder ini
- **GitHub Pages / Cloudflare Pages**: publikasikan folder ini sebagai root

Catatan: hosting gratis biasanya membatasi ukuran file (mis. GitHub 100 MB per file, Cloudflare Pages 25 MB). Installer besar lebih aman ditaruh di GitHub Releases atau Google Drive, lalu isi `file` dengan link-nya.
