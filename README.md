# Ruang Jelajah: Landing Page Tailwind CSS

Landing page informasi pariwisata Jawa Tengah yang menggunakan **HTML5 dan Tailwind CSS v4**. Konten destinasi dan tautan ke situs resmi dipertahankan dari versi sebelumnya. Desain diperbarui dengan tema hijau gelap, kartu destinasi bergaya editorial, panduan wisata lengkap, menu mobile, dan FAQ interaktif.

## Cara menjalankan

1. Ekstrak seluruh file proyek.
2. Buka `index.html` langsung melalui browser, atau jalankan ekstensi **Live Server** di Visual Studio Code.
3. Situs sudah menggunakan `style.css` hasil build Tailwind, sehingga **tidak perlu memasang Node.js** hanya untuk melihat atau mengunggahnya.
4. Gambar tetap memiliki ilustrasi SVG lokal saat foto dari Wikimedia Commons tidak dapat diakses. Font Google memakai fallback sistem jika offline.

## Deploy ke GitHub Pages

1. Buat repository **Public**, misalnya `ruang-jelajah`.
2. Unggah `index.html`, `style.css`, folder `assets`, dan dokumen yang disertakan ke direktori utama repository. Pastikan jangan hanya mengunggah ZIP atau satu folder pembungkus.
3. Buka **Settings > Pages > Build and deployment**.
4. Atur **Source: Deploy from a branch**, **Branch: main**, **Folder: /(root)**, kemudian klik **Save**.
5. Setelah deployment selesai, kunjungi `https://USERNAME.github.io/ruang-jelajah/` dengan mengganti `USERNAME` menggunakan username GitHub.

Karena CSS Tailwind sudah dikompilasi, GitHub Pages tidak perlu menjalankan npm saat deployment.

## Cara mengedit dengan Tailwind CSS

Sumber pengaturan Tailwind berada di `src/input.css`. Ubah kelas utilitas di `index.html` atau aturan tema di `src/input.css`, lalu jalankan:

```bash
npm install
npm run build
```

Untuk menyusun ulang CSS otomatis saat mengedit:

```bash
npm run dev
```

**Penting:** setelah menjalankan build lokal, lakukan commit **index.html, src/input.css, dan style.css** agar tampilan baru muncul di GitHub Pages. `node_modules` tidak perlu diunggah.

## Struktur proyek

```
ruang-jelajah/
├── index.html              # Halaman utama
├── style.css               # CSS Tailwind v4 terkompilasi, siap deploy
├── src/
│   └── input.css           # Sumber Tailwind, tema dan CSS tambahan
├── assets/
│   ├── borobudur.svg       # Fallback visual destinasi
│   ├── karimunjawa.svg
│   ├── dieng.svg
│   ├── semarang.svg
│   └── favicon.svg
├── package.json            # Build Tailwind CLI
├── .gitignore
├── README.md
├── CATATAN-DATA.md         # Referensi dan tanggal verifikasi konten
└── KREDIT-FOTO.md          # Rujukan media fotografi
```

## Konten dan sumber

- **Borobudur:** situs Warisan Dunia UNESCO dan portal tiket Borobudur.
- **Karimunjawa:** Balai Taman Nasional dan Ditjen KSDAE.
- **Dieng:** portal resmi Indonesia Travel.
- **Kota Lama Semarang:** Pemerintah Kota Semarang dan data cagar budaya.

Harga tiket, jadwal kapal, atau aturan kunjungan bisa berubah. Konten memberikan tautan resmi agar pengunjung dapat memeriksa keadaan terbaru. Informasi ini tidak menyatakan adanya layanan pemesanan dari website.

## Catatan teknis

- Tailwind CSS v4 digunakan sebagai utilitas desain dan telah dikompilasi ke `style.css` untuk deployment statis.
- Tidak menggunakan Tailwind Play CDN karena ditujukan untuk pengembangan, bukan publikasi produksi.
- Menu mobile dan FAQ menggunakan elemen `<details>` HTML sehingga dapat berfungsi tanpa JavaScript tambahan.
- Path CSS, ikon, dan gambar menggunakan path relatif agar kompatibel dengan repository GitHub Pages yang memakai subfolder.
- Desain responsif pada layar desktop maupun mobile, menyertakan tautan lompat konten, label navigasi, dan dukungan preferensi reduced motion.
