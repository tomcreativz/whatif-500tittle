# 500 Ide Konten What If (PWA)

Planner 500 judul video format *What If* + terjemahan Indonesia. Bisa dipasang seperti aplikasi dan jalan offline.

## Isi folder
- `index.html` – aplikasi (semua data judul sudah di dalam)
- `manifest.webmanifest` – identitas aplikasi untuk install
- `sw.js` – service worker (offline + update otomatis)
- `icons/` – ikon aplikasi
- `.nojekyll` – supaya GitHub Pages menyajikan file apa adanya

## Deploy ke GitHub Pages
1. Buat repo baru di GitHub, lalu upload **seluruh isi folder ini** ke root repo (pastikan `.nojekyll` ikut).
2. Buka **Settings → Pages**.
3. Di *Build and deployment*, pilih **Deploy from a branch**, branch `main`, folder `/ (root)`, lalu Save.
4. Tunggu 1–2 menit. Alamatnya: `https://USERNAME.github.io/NAMA-REPO/`

Semua path di dalam aplikasi sudah relatif, jadi aman di alamat subfolder seperti di atas.

## Cara memasang
- **Android / Chrome / Edge:** buka alamatnya, lalu menu ⋯ di aplikasi → *Pasang sebagai aplikasi* (atau ikon install di address bar).
- **iPhone / iPad (Safari):** tombol Bagikan → *Tambah ke Layar Utama*.
- **Laptop (Chrome/Edge):** ikon install di sebelah kanan address bar.

## Update
Setiap kali kamu mengubah file dan push ke GitHub, pengguna yang membuka aplikasi akan melihat pesan **"Versi baru siap dipakai → Perbarui"**.
Jika kamu hanya mengubah `index.html`, ubah juga angka `VERSION` di `sw.js` (isi apa saja yang baru, mis. `'v2'`) supaya cache lama diganti.

## Tentang data progres
- Tanda "sudah tayang" disimpan di browser (localStorage), bukan di server.
- Laptop, HP, dan aplikasi terpasang di iPhone punya penyimpanan **terpisah**. Pindahkan lewat menu ⋯ → *Cadangkan progres* lalu *Pulihkan progres*.
- Menghapus data situs/cache browser akan menghapus tanda. Cadangkan secara berkala.

## Catatan
- Service worker butuh HTTPS. GitHub Pages sudah HTTPS, dan `localhost` juga boleh untuk uji lokal (`python3 -m http.server`). Membuka `index.html` langsung dari file tetap jalan, tapi tanpa fitur offline/install.
- Font tulisan tangan diambil dari Google Fonts dan otomatis ikut tersimpan untuk offline setelah pernah dimuat sekali.
