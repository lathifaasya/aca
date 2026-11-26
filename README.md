# Lathifa — Portofolio UI/UX Editorial

Portofolio statis satu halaman dengan tema gelap dan aksen emas. Seluruh aset disimpan lokal, sehingga siap diunggah ke GitHub dan diaktifkan sebagai GitHub Pages.

## Struktur berkas

```text
stitch_dark_luxury_designer_portfolio/
├── index.html          # Halaman utama
├── 404.html            # Halaman saat alamat tidak ditemukan
├── favicon.svg         # Ikon tab browser
├── process-art.svg     # Ilustrasi bagian Proses (menggantikan tautan Google Drive)
├── foto-lathifa.jpeg   # Foto hero
├── Nirmana.jpeg        # Proyek 1
├── Desain-baju.jpeg    # Proyek 2
├── Figma.png           # Proyek 3
├── foto-aca.jpeg       # Testimoni 1
├── footage.jpeg        # Testimoni 2
├── foto-acaw.jpeg      # Testimoni 3
├── robots.txt          # Aturan dasar untuk mesin pencari
├── .nojekyll           # Menonaktifkan pemrosesan Jekyll di GitHub Pages
├── .gitignore          # Berkas yang tidak perlu diunggah
└── README.md           # Dokumentasi ini
```

## Menjalankan di komputer lokal

Cukup buka `index.html` di browser. Jika ingin memakai server statis (disarankan agar fitur clipboard bekerja), jalankan:

```bash
python -m http.server 8000
```

Lalu buka `http://localhost:8000`.

> Di Windows, `python` kadang hanya alias Microsoft Store. Jika belum terpasang, membuka `index.html` langsung tetap berfungsi selama komputer terhubung internet, karena Tailwind dan font dimuat dari CDN.

## Upload ke GitHub tanpa Git

1. Buat repository baru di <https://github.com/new>.
2. Centang **Add a README file** tidak perlu, karena `README.md` sudah ada.
3. Klik **Add file → Upload files**.
4. Unggah **semua isi folder** ini (file-file di dalamnya), bukan folder induknya.
5. Klik **Commit changes**.
6. Buka **Settings → Pages**.
7. Pada **Build and deployment**, pilih **Source: Deploy from a branch**.
8. Pilih branch `main` dan folder `/(root)`, lalu klik **Save**.
9. Tunggu beberapa menit. Situs tersedia di `https://<username>.github.io/<nama-repo>/`.

## Upload lewat Git CLI

Jika Git belum terpasang, unduh dari <https://git-scm.com/download/win>.

```bash
git init
git add .
git commit -m "Initial portfolio site"
git branch -M main
git remote add origin https://github.com/<username>/<nama-repo>.git
git push -u origin main
```

Setelah itu aktifkan GitHub Pages lewat **Settings → Pages** seperti langkah di atas.

## Sebelum dipublikasikan

- [ ] Ganti `hello@lathifa.design` di `index.html` dengan email asli (muncul di tombol kontak dan skrip salin email).
- [ ] Ganti tautan Dribbble, Behance, LinkedIn, dan X dengan profil asli.
- [ ] Sesuaikan atau hapus klaim `8+ Tahun Keahlian` agar sesuai dengan profil mahasiswa.
- [ ] Jika memakai domain sendiri, buat berkas teks bernama `CNAME` berisi domain, misalnya `portofolio.example.com`, lalu unggah bersama berkas lain.

## Catatan teknis

- Semua gambar memakai path relatif. GitHub Pages bersifat **case-sensitive**, jadi nama berkas harus persis sama, termasuk huruf besar/kecil.
- Tautan Google Drive pada bagian Proses sebelumnya mengembalikan halaman HTML, bukan gambar. Tautan itu diganti dengan `process-art.svg` lokal agar tidak ada gambar rusak.
- `.nojekyll` memastikan GitHub Pages menyajikan berkas apa adanya tanpa pemrosesan Jekyll.
- Tailwind masih dimuat lewat CDN. Untuk situs skala besar, versi produksi sebaiknya memakai CSS yang dibangun lokal.
