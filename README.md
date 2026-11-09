# GYVER STUDIO — Halaman Unduhan

Landing page statis (satu file HTML) untuk membagikan file Windows / Mac + donasi rekening & QRIS.

## Mengisi

Semua data ada di `index.html`, bagian `EDIT DI SINI`.

1. **Paket ZIP Windows**: isi `file` dan `size` tiap aplikasi di `PRODUCTS`. ZIP CueRundown 0.4.6 = 144 MB (`D:\CUERUNDOWN\release\CueRundown 0.4.6 - Paket.zip`); ZIP CueDirector 1.1.3 = 162 MB (`D:\CUEDIRECTOR\release\CueDirector 1.1.3 - Paket.zip`). Keduanya sudah diunggah ke Release `v1` (https://github.com/edfgyver/gyver-download/releases/tag/v1) dan `file` berisi link-nya. Versi baru: `gh release create v2 <zip...>`, lalu ambil URL aset dari halaman Release (spasi di nama file jadi titik).
2. **Mac**: CueRundown 0.4.11 sudah aktif (Release `v3`: `CueRundown-0.4.11-Windows.zip`, `CueRundown-Update-0.4.11.exe`, `CueRundown-0.4.11-mac-arm64.dmg`, `CueRundown-0.4.11-mac-x64.dmg`; tiap tombol punya pop-up `info`; .dmg dibuat GitHub Actions di repo private `edfgyver/cuerundown`). CueDirector masih `soon: true`; nanti hapus itu lalu isi `file`, `size`, dan `info` (pop-up saat hover, di HP tampil di bawah tombol). Penghitung unduhan menjumlah semua aset Release yang namanya diawali nama aplikasi, jadi versi lama tetap terhitung.
3. **Versi baru**: ubah `version`, `file` dan `size`.
4. **Video**: `assets/video/<nama>.mp4` + poster `.jpg` (15 detik, dipotong dari video brag 60 detik di folder project masing-masing).
5. **Rekening**: `BANKS` (sudah berisi BCA). **QRIS**: `assets/qris-gopay.png` (sudah ada) dan `assets/qris-bca.png` (belum; tampil "Dalam proses" sampai file ada).
6. **Kontak**: bagian `<section ... h-contact>` di HTML.

## Menjalankan lokal

```bash
python -m http.server 5174 --directory "D:\GYVER STUDIO\download"
```

## Deploy

Live di GitHub Pages: https://edfgyver.github.io/gyver-download/ (repo `edfgyver/gyver-download`, branch `main`). Update: `git add -A && git commit -m "..." && git push`; Pages terbit ulang otomatis dalam 1-2 menit.

### Alternatif hosting gratis

Upload isi folder `download/` apa adanya (tanpa build):
- **Netlify Drop**: seret folder ke https://app.netlify.com/drop
- **Vercel**: `vercel deploy` dari folder ini
- **GitHub Pages / Cloudflare Pages**: publikasikan folder ini sebagai root

Catatan: hosting gratis biasanya membatasi ukuran file (mis. GitHub 100 MB per file, Cloudflare Pages 25 MB). Installer besar lebih aman ditaruh di GitHub Releases atau Google Drive, lalu isi `file` dengan link-nya.
