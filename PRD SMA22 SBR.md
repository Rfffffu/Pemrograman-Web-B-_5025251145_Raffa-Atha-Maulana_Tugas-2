# Product Requirement Document (PRD)

## Website Resmi SMA Negeri 22 Surabaya

|  |  |
| --- | --- |
| **Versi Dokumen** | 1.0 |
| **Tanggal** | 29 September 2026 |
| **Status** | Draft untuk Peninjauan |
| **Pemilik Produk** | Humas / Tim TIK SMA Negeri 22 Surabaya |

---

## 1. Latar Belakang

SMA Negeri 22 Surabaya membutuhkan sebuah portal informasi resmi berbasis web sebagai media komunikasi utama antara sekolah dengan siswa, orang tua, calon peserta didik, dan masyarakat umum. Selama ini informasi sekolah tersebar di berbagai kanal tanpa satu sumber yang terpusat, resmi, dan mudah diakses.

Website ini dibangun sebagai portal statis (HTML/CSS) yang menampilkan profil sekolah, sambutan kepala sekolah, visi-misi, informasi jurusan, serta kanal kontak — dengan struktur yang dapat dikembangkan lebih lanjut ke arah CMS di iterasi berikutnya.

## 2. Tujuan Produk

1. Menyediakan media penyampaian informasi resmi tentang SMA Negeri 22 Surabaya yang mudah diakses kapan saja.
2. Meningkatkan citra dan kredibilitas sekolah melalui tampilan digital yang profesional dan modern.
3. Mempermudah calon siswa dan orang tua memperoleh informasi jurusan serta menyampaikan pertanyaan melalui form kontak.
4. Menjadi wahana pembelajaran dan publikasi kegiatan bagi siswa-siswi dan masyarakat luas.

## 3. Target Pengguna

| Persona | Kebutuhan Utama |
| --- | --- |
| Calon siswa & orang tua (PPDB) | Info jurusan, profil sekolah, cara menghubungi sekolah |
| Siswa aktif | Info kegiatan siswa, galeri, ekstrakurikuler |
| Alumni | Info ikatan alumni, kegiatan reuni |
| Guru & Tenaga Kependidikan (GTK) | Informasi kepegawaian, tupoksi |
| Masyarakat umum | Profil, visi-misi, kontak sekolah |

## 4. Lingkup Produk (Scope)

### 4.1 Dalam Lingkup (In Scope)

- Halaman **Beranda** (`index.html`) dengan hero banner, sambutan kepala sekolah, dan visi-misi.
- Halaman **Jurusan** (`jurusan.html`) berisi daftar program peminatan dan tabel jumlah siswa per jurusan.
- Halaman **Kontak** (`kontak.html`) berisi informasi kontak dan form pesan.
- Navigasi global (top bar info, header, navbar dropdown) yang konsisten di seluruh halaman.
- Tampilan responsif untuk desktop, tablet, dan mobile.

### 4.2 Di Luar Lingkup (Out of Scope) — iterasi berikutnya

- Backend pemrosesan form kontak (saat ini `action="#"`, belum terhubung ke email/database).
- Sistem manajemen konten (CMS) agar admin sekolah bisa mengubah konten tanpa coding.
- Halaman penuh untuk menu Profil, Tupoksi, GTK, Siswa, Alumni, Galeri, Link, dan Dharma Wanita (saat ini placeholder `#`).
- Sistem PPDB online, login siswa/guru, dan integrasi Dapodik.
- Multi-bahasa (saat ini hanya Bahasa Indonesia).

## 5. Fitur & Kebutuhan Fungsional

### 5.1 Komponen Global (seluruh halaman)

| ID | Fitur | Deskripsi | Prioritas |
| --- | --- | --- | --- |
| F-01 | Top Info Bar | Menampilkan nomor telepon, email, jam operasional, dan tautan media sosial sekolah | Must Have |
| F-02 | Header Kontak | Logo & nama sekolah, blok "Call Now", "Send Message", dan "Our Location" | Must Have |
| F-03 | Navigasi Utama | Menu horizontal dengan dropdown (Profil, Tupoksi, GTK, Siswa, Alumni, Galeri, Link, Dharma Wanita) serta tautan langsung ke Jurusan dan Kontak | Must Have |
| F-04 | Footer | Informasi hak cipta di seluruh halaman | Should Have |
| F-05 | Desain Responsif | Layout menyesuaikan otomatis di breakpoint ≤992px dan ≤600px | Must Have |

### 5.2 Halaman Beranda (`index.html`)

| ID | Fitur | Deskripsi | Prioritas |
| --- | --- | --- | --- |
| F-06 | Hero Slider | Banner utama dengan judul, subjudul, dan tombol navigasi sebelumnya/berikutnya | Must Have |
| F-07 | Sambutan Kepala Sekolah | Teks sambutan resmi beserta foto kepala sekolah, tanda tangan, dan identitas jabatan | Must Have |
| F-08 | Visi & Misi | Kartu Visi dan daftar bernomor Misi sekolah | Must Have |

### 5.3 Halaman Jurusan (`jurusan.html`)

| ID | Fitur | Deskripsi | Prioritas |
| --- | --- | --- | --- |
| F-09 | Daftar Jurusan | Penjelasan singkat dan daftar program peminatan (MIPA, IPS) dalam format `<ul>` | Must Have |
| F-10 | Tabel Jumlah Siswa | Tabel jumlah siswa per jurusan, per tingkat kelas (X, XI, XII), dan baris total | Must Have |

### 5.4 Halaman Kontak (`kontak.html`)

| ID | Fitur | Deskripsi | Prioritas |
| --- | --- | --- | --- |
| F-11 | Informasi Kontak | Alamat, telepon, email, dan jam operasional dalam kolom terpisah | Must Have |
| F-12 | Form Kontak | Input nama (text), email (email), subjek (text), pesan (textarea), dan tombol kirim (button) | Must Have |
| F-13 | Validasi Form Dasar | Atribut `required` pada nama, email, dan pesan | Should Have |

## 6. Kebutuhan Non-Fungsional

| Kategori | Kebutuhan |
| --- | --- |
| **Performa** | Halaman statis harus termuat penuh dalam \< 3 detik pada koneksi standar |
| **Kompatibilitas** | Tampil dengan benar di Chrome, Firefox, Edge, dan Safari versi terbaru |
| **Aksesibilitas** | Kontras warna teks memadai; elemen interaktif dapat diakses dengan keyboard |
| **Konsistensi Desain** | Satu file `style.css` bersama digunakan di seluruh halaman untuk menjaga konsistensi visual |
| **Maintainability** | Struktur HTML semantik (`header`, `nav`, `section`, `footer`) agar mudah dikembangkan lebih lanjut |
| **SEO Dasar** | Setiap halaman memiliki `<title>` unik dan struktur heading yang jelas |

## 7. Arsitektur Informasi (Sitemap Saat Ini)

```
├── index.html        (Beranda: Hero, Sambutan Kepala Sekolah, Visi & Misi)
├── jurusan.html       (Daftar Jurusan, Tabel Jumlah Siswa)
├── kontak.html        (Info Kontak, Form Kontak)
├── style.css           (Stylesheet bersama)
├── logo-placeholder.svg
├── hero-placeholder.svg
└── kepala-sekolah-placeholder.svg
```

## 8. Asumsi

- Konten Visi-Misi, jumlah siswa, dan sebagian teks lain masih berupa **data contoh** yang perlu diverifikasi/diganti oleh pihak sekolah dengan data resmi.
- Gambar hero, logo, dan foto kepala sekolah masih berupa **placeholder SVG** dan perlu diganti dengan aset foto asli sebelum situs dipublikasikan.
- Form kontak belum tersambung ke email/server sungguhan; memerlukan backend (mis. PHP, Node.js, atau layanan pihak ketiga seperti Formspree) pada iterasi berikutnya.

## 9. Kriteria Keberhasilan (Success Metrics)

| Metrik | Target |
| --- | --- |
| Waktu muat halaman | \< 3 detik |
| Kompatibilitas perangkat | Tampil baik di ≥ 95% perangkat desktop & mobile umum |
| Tautan navigasi berfungsi | 100% tautan internal (Beranda, Jurusan, Kontak) tidak error |
| Pengiriman form kontak berhasil (pasca-integrasi backend) | ≥ 95% pesan terkirim tanpa gagal |

## 10. Risiko & Mitigasi

| Risiko | Dampak | Mitigasi |
| --- | --- | --- |
| Menu dropdown (Profil, Tupoksi, dll.) masih placeholder `#` | Pengguna kebingungan saat mengklik menu tanpa isi | Prioritaskan pembuatan halaman-halaman tersebut pada iterasi berikutnya |
| Form kontak belum fungsional | Pesan dari pengunjung tidak benar-benar terkirim | Integrasikan backend/layanan form sebelum go-live |
| Data placeholder belum diganti | Informasi yang tampil tidak akurat | Lakukan review konten oleh Humas sebelum publikasi |

## 11. Rencana Iterasi Berikutnya

1. Melengkapi halaman untuk menu Profil, Tupoksi, GTK, Siswa, Alumni, Galeri, Link, dan Dharma Wanita.
2. Mengintegrasikan form kontak dengan backend pengiriman email.
3. Mengganti seluruh aset placeholder dengan foto dan data resmi sekolah.
4. Evaluasi migrasi ke CMS agar konten dapat dikelola tanpa keterlibatan developer.
5. Audit aksesibilitas dan SEO lanjutan.

