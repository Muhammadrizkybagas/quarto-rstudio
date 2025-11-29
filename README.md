
Repositori ini adalah template buku Quarto (mirip Bookdown) yang bisa digunakan oleh mahasiswa, atau siapa pun yang ingin membuat buku digital, modul, laporan panjang, atau dokumentasi proyek. Template ini dibuat sebagai portofolio belajar dan dapat digunakan ulang dengan mudah.
Template ini sudah dipaketkan dengan struktur folder yang rapi, file chapter, file referensi, serta stylesheet yang bisa dikustomisasi.

---

## **Fitur Utama**

- Format buku dengan struktur chapter yang telah disiapkan
- Mendukung output HTML, PDF, dan EPUB
- Termasuk:

  - Contoh chapter
  - File referensi `.bib` dan style sitasi IEEE
  - Folder dataset
  - Folder gambar
  - Custom CSS
    
Dapat dipublikasikan ke **Quarto Pub** dan cocok sebagai bahan ajar, dokumentasi akademik, atau portofolio

---

# **Struktur Direktori**

Struktur proyek dijelaskan sebagai berikut:

```
/
├── _site/               # Output hasil render (dibuat otomatis)
├── css/
│   └── style.css        # (Opsional) custom style
├── data/
│   └── ...              # Dataset yang digunakan dalam buku
├── img/
│   └── ...              # Gambar atau foto yang digunakan
├── referensi/
│   ├── referensi.bib    # Daftar pustaka (wajib disesuaikan)
│   └── ieee.csl         # Format sitasi IEEE
├── chapter1.qmd
├── chapter2.qmd
├── chapter3.qmd
├── chapter4.qmd
├── chapter5.qmd
├── intro.qmd
├── _quarto.yml          # Konfigurasi utama proyek
└── _publish.yml         # Pengaturan publikasi ke Quarto Pub
```

### **Folder/berkas yang wajib disesuaikan**

* `data/` → sesuaikan dataset
* `img/` → sesuaikan gambar yang dibutuhkan
* `referensi/referensi.bib` → isi daftar pustaka yang relevan

### **Opsional**

* `css/style.css` → digunakan jika ingin melakukan penyesuaian tampilan
* Folder lain dapat dibiarkan sebagaimana adanya

---

# **Instalasi Quarto**

1. Unduh Quarto dari:
   [https://quarto.org](https://quarto.org)

2. Instal sesuai sistem operasi.

3. Periksa instalasi:

```bash
quarto check
```

Jika seluruh komponen ditandai “OK”, Quarto sudah siap digunakan.

---

# **Rendering Proyek**

Render seluruh buku:

```bash
quarto render
```

`atau CTRL + SHIFT + K`

Output akan tersimpan pada direktori:

```
_site/
```

---

# **Publikasi ke Quarto Pub**

1. Login terlebih dahulu:

Lalu di terminal RStudio lakukan ini

```bash
quarto render
```

```bash
quarto publish quarto-pub
```
Setelah proses selesai, Quarto akan memberikan tautan publikasi buku Anda.

---

# **Menambahkan Chapter Baru**

Tambahkan file baru, misalnya:

```
chapter6.qmd
```

Kemudian daftarkan pada bagian `chapters:` di dalam `_quarto.yml`:

```yaml
    contents:
      - text: "**INTRODUCTION**"
        href: intro.qmd
      - section: "**MATERI**"
        contents:
          - text: "1. Naive Bayes"
            href: chapter1.qmd
            
          - text: "2. Linear Discriminant Analyis"
            href: chapter2.qmd
            
          - text: "3. Quadratic Discriminant Analyis"
            href: chapter3.qmd
            
          - text: "4. Logistic Regression"
            href: chapter4.qmd
            
          - text: "5. Perbandingan"
            href: chapter5.qmd
            
          - text: "6. Lorem Ipsum Dolor"
            href: chapter6.qmd
```

Setelah itu, lakukan render `CTRL + SHIFT + K` ulang.

---

# **Pengelolaan Referensi**

Edit daftar pustaka pada:

```
referensi/referensi.bib
```

Format mengikuti BibTeX, misalnya:

```bibtex
@article{contoh2024,
  title={Judul Artikel},
  author={Nama Penulis},
  year={2024},
  journal={Nama Jurnal}
}

@online{online_artikel2025,      # Online Article
  author = {Nama Author},
  title = {Judul Artikel},
  year = {2025},
  note = {Opsional},
  url = {Link artikel},
  urldate = {2025-11-19}         # Tanggal
}
```

Quarto akan memproses sitasi secara otomatis berdasarkan file `.bib` dan `.csl`.

---

# **Penyesuaian Tampilan (Opsional)**

Jika ingin menyesuaikan warna, tipografi, atau detail visual lainnya, edit:

```
css/style.css
```

Pastikan file tersebut sudah terhubung dalam `_quarto.yml`:

```yaml
format:
  html:
    css: css/style.css
```

---

# **Sasaran Pengguna**

Template ini ditujukan untuk:

* Mahasiswa yang menyiapkan modul atau laporan proyek
* Pengguna umum yang ingin mempelajari atau menggunakan Quarto secara praktis

---

# **Tujuan Proyek**

Template ini dikembangkan sebagai **portofolio belajar** dan dapat digunakan sebagai dasar untuk mengembangkan buku digital atau dokumentasi akademik yang lebih kompleks.

---

`Disusun dan dikembangkan oleh Muhammad Rizky Bagas.`
