# 📘 BELAJAR HTML & CSS DARI NOL HINGGA MAHIR
### Panduan Super Lengkap, Super Kompleks, dan Super Detail untuk Pemula

> **Tujuan**: Setelah membaca panduan ini, Anda benar-benar bisa membuat website statis modern dengan animasi, layout kompleks, dan memahami setiap baris kode HTML/CSS yang Anda tulis.

---

# 📋 DAFTAR ISI

1. [BAGIAN 1: HTML (HyperText Markup Language)](#-bagian-1-html-hypertext-markup-language)
   - [1.1 Apa Itu HTML?](#11-apa-itu-html)
   - [1.2 Struktur Dasar Dokumen HTML](#12-struktur-dasar-dokumen-html)
   - [1.3 Daftar Lengkap Elemen HTML](#13-daftar-lengkap-elemen-html)
   - [1.4 Elemen Blok vs Inline & Void Elements](#14-elemen-blok-vs-inline--void-elements)
   - [1.5 Tabel Ringkasan Atribut Global](#15-tabel-ringkasan-atribut-global)
2. [BAGIAN 2: CSS (Cascading Style Sheets)](#-bagian-2-css-cascading-style-sheets)
   - [2.1 Cara Kerja CSS](#21-cara-kerja-css)
   - [2.2 Tiga Cara Implementasi CSS](#22-tiga-cara-implementasi-css)
   - [2.3 Daftar Lengkap Selektor CSS](#23-daftar-lengkap-selektor-css)
   - [2.4 Daftar Lengkap Properti CSS](#24-daftar-lengkap-properti-css)
3. [BAGIAN 3: Implementasi Praktis (Proyek Lengkap)](#-bagian-3-implementasi-praktis-proyek-lengkap)
4. [BAGIAN 4: Bonus & Best Practices](#-bagian-4-bonus--best-practices)

---

# 🎯 BAGIAN 1: HTML (HyperText Markup Language)

## 1.1 Apa Itu HTML?

### Definisi

**HTML** adalah singkatan dari **HyperText Markup Language** — bukan bahasa pemrograman, melainkan **bahasa markup** yang digunakan untuk membuat struktur dan konten halaman web.

| Istilah | Penjelasan |
|---------|-----------|
| **HyperText** | Teks yang memiliki tautan (link) ke dokumen lain. Konsep ini memungkinkan pengguna berpindah dari satu halaman ke halaman lain dengan mengklik tautan. |
| **Markup** | Sistem penandaan (tag) yang digunakan untuk memberi tahu browser bagaimana cara menampilkan konten. |
| **Language** | Seperangkat aturan dan sintaks yang terstandarisasi. |

### Sejarah Singkat HTML

| Tahun | Versi | Fitur Penting |
|-------|-------|---------------|
| 1991 | HTML 1.0 (Tim Berners-Lee) | Versi pertama, hanya teks dan link sederhana. |
| 1995 | HTML 2.0 | Standarisasi pertama oleh IETF. Menambahkan form dasar. |
| 1997 | HTML 3.2 | Menambahkan tabel, applet, dan text flow. |
| 1999 | HTML 4.01 | Stabil dan paling populer. Menambahkan CSS, scripting, dan aksesibilitas. |
| 2000 | XHTML 1.0 | HTML yang ditulis ulang sebagai XML — lebih ketat aturannya. |
| 2014 | **HTML5** (Revolusi!) | Standar modern. Menambahkan elemen semantik (`<header>`, `<nav>`, `<section>`, `<article>`, `<aside>`, `<footer>`), elemen multimedia (`<audio>`, `<video>`), canvas, SVG, API lokal storage, geolocation, dan banyak lagi. |
| 2016+ | HTML 5.1, 5.2, Living Standard | Perbaikan berkelanjutan. Sekarang HTML adalah "Living Standard" yang terus diperbarui oleh **WHATWG** (Web Hypertext Application Technology Working Group). |

### Peran HTML dalam Web

HTML adalah **tulang punggung** dari setiap halaman web. Tanpa HTML, browser tidak akan tahu apa yang harus ditampilkan.

```
┌─────────────────────────────────────┐
│          Halaman Web                │
├─────────────────────────────────────┤
│  HTML  →  Struktur & Konten         │
│  CSS   →  Tampilan & Layout         │
│  JS    →  Interaktivitas & Logika   │
└─────────────────────────────────────┘
```

> **Catatan Penting**: HTML, CSS, dan JavaScript adalah **tiga pilar utama** pengembangan web front-end. HTML untuk struktur, CSS untuk gaya, JavaScript untuk perilaku.

---

## 1.2 Struktur Dasar Dokumen HTML

Setiap dokumen HTML yang valid **WAJIB** memiliki struktur dasar berikut:

```html
<!DOCTYPE html>
<html lang="id" dir="ltr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Deskripsi halaman untuk SEO">
    <meta name="keywords" content="html, css, belajar, pemula">
    <meta name="author" content="Nama Anda">
    <title>Judul Halaman Web Saya</title>
    <link rel="stylesheet" href="style.css">
    <style>
        /* CSS internal bisa ditulis di sini */
    </style>
</head>
<body>
    <!-- Semua konten yang tampil di browser ditulis di sini -->
    <h1>Halo, Dunia!</h1>
    <p>Ini adalah halaman web pertama saya.</p>

    <script src="script.js"></script>
</body>
</html>
```

### Penjelasan Setiap Bagian:

#### 1. `<!DOCTYPE html>`

```html
<!DOCTYPE html>
```

| Aspek | Penjelasan |
|-------|-----------|
| **Fungsi** | Mendeklarasikan bahwa dokumen ini menggunakan HTML5. |
| **Posisi** | **WAJIB** berada di baris PERTAMA dokumen, sebelum tag `<html>`. |
| **Sejarah** | Di versi HTML sebelumnya (4.01), deklarasi ini panjang dan rumit. HTML5 menyederhanakannya. |
| **Case** | Tidak case-sensitive. `<!DOCTYPE html>`, `<!doctype html>`, `<!Doctype HTML>` semuanya valid. |
| **Akibat jika tidak ada** | Browser akan masuk ke **quirks mode** — mode kompatibilitas mundur yang bisa menyebabkan rendering tidak konsisten. |

#### 2. `<html>` — Elemen Akar (Root Element)

```html
<html lang="id" dir="ltr">
```

| Atribut | Fungsi | Nilai yang Valid |
|---------|--------|------------------|
| `lang` | Menentukan bahasa konten halaman. Penting untuk aksesibilitas (screen reader) dan SEO. | Kode bahasa ISO 639-1: `"id"` (Indonesia), `"en"` (Inggris), `"ms"` (Melayu), `"ar"` (Arab), dll. |
| `dir` | Menentukan arah teks. | `"ltr"` (left-to-right — default), `"rtl"` (right-to-left — untuk bahasa Arab/Ibrani), `"auto"` (browser yang menentukan). |
| `xmlns` | Hanya untuk XHTML. | `"http://www.w3.org/1999/xhtml"` |

**Fungsi**: Tag pembungkus utama yang mencakup **seluruh** konten dokumen HTML. Semua elemen lain berada di dalam tag ini.

#### 3. `<head>` — Kepala Dokumen (Metadata Container)

```html
<head>
    <!-- Metadata dan informasi tentang halaman -->
</head>
```

| Aspek | Penjelasan |
|-------|-----------|
| **Fungsi** | Wadah untuk **metadata** — informasi tentang halaman yang **tidak tampil** langsung di browser. |
| **Isi yang umum** | `<title>`, `<meta>`, `<link>`, `<style>`, `<script>` (untuk JavaScript yang tidak perlu ditampilkan). |
| **Urutan** | Harus menjadi **anak pertama** dari `<html>`, sebelum `<body>`. |
| **Konten yang tampak** | Konten di `<head>` **TIDAK** akan terlihat oleh pengguna (kecuali `<title>` yang muncul di tab browser). |

#### 4. `<title>` — Judul Halaman

```html
<title>Belajar HTML & CSS - Panduan Lengkap</title>
```

| Aspek | Penjelasan |
|-------|-----------|
| **Fungsi** | Menentukan judul halaman yang muncul di **tab browser**, **bookmark**, dan **hasil pencarian Google**. |
| **Posisi** | **WAJIB** ada di dalam `<head>`. |
| **SEO** | Sangat penting untuk SEO. Usahakan judul unik per halaman, maksimal 50-60 karakter. |
| **Best Practice** | Format: `"Nama Halaman | Nama Situs"` atau `"Keyword Utama - Keyword Pendukung"` |

#### 5. `<meta>` — Metadata Lainnya

Tag `<meta>` adalah **void element** (tidak perlu tag penutup) yang menyediakan metadata terstruktur tentang halaman.

```html
<!-- Character encoding — WAJIB -->
<meta charset="UTF-8">

<!-- Viewport — WAJIB untuk responsive design -->
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<!-- SEO: Deskripsi halaman -->
<meta name="description" content="Panduan lengkap belajar HTML dan CSS dari nol hingga mahir. Cocok untuk pemula yang ingin menguasai web development.">

<!-- SEO: Kata kunci -->
<meta name="keywords" content="HTML, CSS, belajar HTML, belajar CSS, web development, pemula">

<!-- SEO: Author -->
<meta name="author" content="Nama Anda">

<!-- SEO: Robots (kontrol crawler) -->
<meta name="robots" content="index, follow">
<!-- Nilai: index/noindex, follow/nofollow, all, none -->

<!-- Open Graph (untuk share di Facebook, WhatsApp, dll) -->
<meta property="og:title" content="Belajar HTML & CSS">
<meta property="og:description" content="Panduan lengkap untuk pemula.">
<meta property="og:image" content="https://example.com/thumbnail.jpg">
<meta property="og:url" content="https://example.com">
<meta property="og:type" content="website">

<!-- Twitter Card -->
<meta name="twitter:card" content="summary_large_image">
<meta name="twitter:title" content="Belajar HTML & CSS">
<meta name="twitter:description" content="Panduan lengkap untuk pemula.">

<!-- Refresh/Muatan ulang otomatis (HATI-HATI) -->
<meta http-equiv="refresh" content="30">
<!-- Atau redirect setelah 5 detik -->
<meta http-equiv="refresh" content="5; url=https://example.com">

<!-- Tema warna untuk browser mobile -->
<meta name="theme-color" content="#1a73e8">
```

**Tabel Atribut `<meta>`:**

| Atribut | Fungsi | Contoh Nilai |
|---------|--------|-------------|
| `charset` | Mendeklarasikan encoding karakter. | `"UTF-8"` (paling umum dan direkomendasikan) |
| `name` | Nama metadata. | `"description"`, `"keywords"`, `"viewport"`, `"robots"` |
| `content` | Nilai dari metadata. | Bergantung pada `name` |
| `http-equiv` | Simulasi header HTTP. | `"refresh"`, `"content-type"`, `"X-UA-Compatible"` |
| `property` | Untuk Open Graph / metadata sosial. | `"og:title"`, `"og:image"` |

#### 6. `<link>` — Menghubungkan ke Sumber Daya Eksternal

```html
<!-- CSS Eksternal (paling umum) -->
<link rel="stylesheet" href="style.css">

<!-- Icon / Favicon -->
<link rel="icon" type="image/png" sizes="32x32" href="/favicon-32x32.png">

<!-- Preconnect untuk optimasi performa -->
<link rel="preconnect" href="https://fonts.googleapis.com">

<!-- Preload font / resource penting -->
<link rel="preload" href="font.woff2" as="font" type="font/woff2" crossorigin>

<!-- Google Fonts -->
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;700&display=swap" rel="stylesheet">

<!-- Canonical URL (mencegah konten duplikat) -->
<link rel="canonical" href="https://example.com/halaman-ini">

<!-- Alternate language version -->
<link rel="alternate" href="https://example.com/en" hreflang="en">
```

**Tabel Atribut `<link>`:**

| Atribut | Fungsi | Nilai Umum |
|---------|--------|-----------|
| `rel` | **Wajib**. Hubungan file yang ditautkan dengan dokumen saat ini. | `"stylesheet"`, `"icon"`, `"preconnect"`, `"preload"`, `"canonical"`, `"alternate"`, `"manifest"` |
| `href` | **Wajib**. URL dari file eksternal. | Path relatif atau absolut |
| `type` | Tipe MIME dari file yang ditautkan. | `"text/css"`, `"image/png"`, `"font/woff2"` |
| `sizes` | Ukuran icon (untuk favicon). | `"16x16"`, `"32x32"`, `"any"` |
| `crossorigin` | Pengaturan CORS untuk font/sumber daya. | `"anonymous"`, `"use-credentials"` |
| `media` | Media query untuk stylesheet kondisional. | `"print"`, `"(max-width: 768px)"` |

#### 7. `<style>` — CSS Internal

```html
<style>
    /* CSS ditulis langsung di sini */
    body {
        font-family: Arial, sans-serif;
        background-color: #f0f0f0;
    }
    h1 {
        color: blue;
    }
</style>
```

| Aspek | Penjelasan |
|-------|-----------|
| **Fungsi** | Menulis CSS langsung di dalam dokumen HTML. |
| **Posisi** | Biasanya di dalam `<head>`, tapi HTML5 juga mengizinkannya di `<body>` (untuk CSS spesifik-konten). |
| **Atribut** | `type="text/css"` (default, bisa diabaikan), `media="all|screen|print"` |
| **Kekurangan** | Tidak bisa digunakan di banyak halaman (tidak reusable). |

#### 8. `<script>` — JavaScript

```html
<!-- JavaScript Eksternal (direkomendasikan di akhir body) -->
<script src="script.js"></script>

<!-- JavaScript Eksternal dengan async/defer -->
<script src="script.js" defer></script>
<script src="analytics.js" async></script>

<!-- JavaScript Internal -->
<script>
    console.log("Halo dari JavaScript!");
</script>

<!-- Module JavaScript (ES6+) -->
<script type="module" src="app.js"></script>

<!-- JSON-LD untuk data terstruktur SEO -->
<script type="application/ld+json">
{
    "@context": "https://schema.org",
    "@type": "WebPage",
    "name": "Belajar HTML & CSS"
}
</script>
```

**Tabel Atribut `<script>`:**

| Atribut | Fungsi | Nilai |
|---------|--------|-------|
| `src` | URL file JavaScript eksternal. | Path file `.js` |
| `type` | Tipe script. | `"text/javascript"` (default), `"module"`, `"application/ld+json"` |
| `defer` | Script dijalankan setelah HTML selesai di-parsing. | Boolean (tidak perlu nilai) |
| `async` | Script dijalankan segera setelah di-download (tidak menunggu parsing HTML). | Boolean |
| `crossorigin` | Untuk script dari domain lain. | `"anonymous"`, `"use-credentials"` |
| `integrity` | Subresource Integrity — verifikasi bahwa file tidak dimodifikasi. | Hash kriptografi |
| `nomodule` | Script hanya dijalankan jika browser **tidak** mendukung module. | Boolean |

**Perbedaan `defer` vs `async`:**

```
Tanpa atribut:
  [-- HTML Parsing --][ Eksekusi Script ][-- Sisa HTML --]
  Script memblokir parsing HTML.

defer:
  [-------- HTML Parsing --------][ Eksekusi Script ]
  Script di-download bersamaan, eksekusi setelah parsing selesai.
  Urutan eksekusi sesuai urutan script di HTML.

async:
  [-- HTML Parsing --][ Eksekusi Script ][-- Sisa HTML --]
       [-- Download Script --]
  Script di-download bersamaan, eksekusi langsung setelah download.
  Urutan eksekusi TIDAK dijamin.
```

#### 9. `<body>` — Tubuh Dokumen

```html
<body>
    <!-- Semua konten visual halaman web -->
    <header>...</header>
    <main>...</main>
    <footer>...</footer>
</body>
```

| Aspek | Penjelasan |
|-------|-----------|
| **Fungsi** | Berisi **semua** konten yang akan ditampilkan oleh browser. |
| **Atribut** | Semua atribut global + event handler (onload, onscroll, onclick, dll). |
| **Atribut khusus** | `onload` — dijalankan setelah halaman selesai dimuat. |
| **Best Practice** | Simpan tag `<script>` di akhir `<body>` (sebelum `</body>`) untuk performa lebih baik. |

---

## 1.3 Daftar Lengkap Elemen HTML

### A. Elemen Semantik Struktural (HTML5)

Elemen semantik adalah elemen yang **memiliki makna** — mereka menjelaskan arti konten di dalamnya, bukan hanya tampilannya.

#### `<header>` — Kepala/Bagian Atas

```html
<header>
    <h1>Nama Website Saya</h1>
    <nav>
        <ul>
            <li><a href="#home">Beranda</a></li>
            <li><a href="#about">Tentang</a></li>
            <li><a href="#contact">Kontak</a></li>
        </ul>
    </nav>
</header>
```

| Aspek | Penjelasan |
|-------|-----------|
| **Fungsi** | Menampung konten pengantar atau navigasi. Bisa digunakan untuk header halaman utama **atau** header sebuah artikel/section. |
| **Penggunaan** | Bisa muncul lebih dari sekali dalam satu halaman (misal: header global + header tiap artikel). |
| **Konten** | Biasanya berisi logo, judul, navigasi, elemen pengantar. |
| **Catatan** | Jangan bingung dengan `<head>` (metadata) — `<header>` adalah bagian visual. |

---

#### `<nav>` — Navigasi

```html
<nav aria-label="Navigasi utama">
    <ul>
        <li><a href="/">Beranda</a></li>
        <li><a href="/blog">Blog</a></li>
        <li><a href="/tutorial">Tutorial</a></li>
        <li><a href="/kontak">Kontak</a></li>
    </ul>
</nav>
```

| Aspek | Penjelasan |
|-------|-----------|
| **Fungsi** | Mendefinisikan sekumpulan tautan navigasi utama. |
| **Aksesibilitas** | Gunakan `aria-label` jika ada lebih dari satu `<nav>` di halaman. |
| **Catatan** | Tidak semua kumpulan link harus di dalam `<nav>`. Hanya navigasi **utama** saja. Link di footer (seperti "Tentang kami", "Privasi") tidak selalu perlu `<nav>`. |

---

#### `<main>` — Konten Utama

```html
<main>
    <article>
        <h2>Judul Artikel</h2>
        <p>Isi artikel...</p>
    </article>
</main>
```

| Aspek | Penjelasan |
|-------|-----------|
| **Fungsi** | Menampung konten **utama** dan **unik** dari halaman. Hanya ada **SATU** `<main>` per halaman. |
| **Aksesibilitas** | Membantu screen reader langsung menuju konten utama (skip navigation). |
| **Catatan** | Jangan letakkan konten yang berulang di beberapa halaman (misal: sidebar, navigasi, footer) di dalam `<main>`. |

---

#### `<section>` — Bagian Konten

```html
<section id="tentang">
    <h2>Tentang Saya</h2>
    <p>Saya adalah seorang web developer yang suka mengajar...</p>
</section>

<section id="keahlian">
    <h2>Keahlian Saya</h2>
    <ul>
        <li>HTML</li>
        <li>CSS</li>
        <li>JavaScript</li>
    </ul>
</section>
```

| Aspek | Penjelasan |
|-------|-----------|
| **Fungsi** | Mengelompokkan konten yang memiliki **tema yang sama**. |
| **Aturan Penting** | Setiap `<section>` **HARUS** memiliki judul/heading (`<h1>`-`<h6>`). |
| **Perbedaan dengan `<article>`** | `<section>` adalah bagian dari sesuatu yang lebih besar. `<article>` adalah konten mandiri. |

---

#### `<article>` — Konten Mandiri

```html
<article>
    <header>
        <h2>Cara Membuat Website dengan HTML</h2>
        <p>Diposting pada <time datetime="2026-06-01">1 Juni 2026</time></p>
    </header>
    <p>Artikel ini akan membahas langkah-langkah...</p>
    <footer>
        <p>Kategori: Tutorial Web</p>
    </footer>
</article>
```

| Aspek | Penjelasan |
|-------|-----------|
| **Fungsi** | Konten yang **mandiri** dan bisa **berdiri sendiri** (bisa di-reuse/di-share tanpa konteks halaman). |
| **Contoh** | Postingan blog, berita, komentar, produk, forum post. |
| **Nesting** | `<article>` bisa berisi `<section>`, dan `<section>` bisa berisi `<article>`. |

---

#### `<aside>` — Konten Sampingan

```html
<aside>
    <h3>Artikel Terkait</h3>
    <ul>
        <li><a href="#">Belajar CSS Dasar</a></li>
        <li><a href="#">Memahami Flexbox</a></li>
    </ul>
</aside>
```

| Aspek | Penjelasan |
|-------|-----------|
| **Fungsi** | Konten yang **terkait** tapi **tidak esensial** untuk konten utama (sidebar, kutipan, iklan, link terkait). |
| **Posisi** | Bisa di dalam atau di luar `<main>`. |

---

#### `<footer>` — Kaki/Bagian Bawah

```html
<footer>
    <p>&copy; 2026 Belajar HTML CSS. Semua hak dilindungi.</p>
    <address>
        Email: <a href="mailto:admin@example.com">admin@example.com</a>
    </address>
</footer>
```

| Aspek | Penjelasan |
|-------|-----------|
| **Fungsi** | Informasi tentang penulis, copyright, link ke halaman terkait, kontak. |
| **Lokasi** | Bisa di akhir halaman utama **dan/atau** di akhir setiap section/article. |

---

#### `<figure>` & `<figcaption>` — Gambar dengan Keterangan

```html
<figure>
    <img src="diagram-html.png" alt="Diagram struktur HTML" width="600" height="400">
    <figcaption>Gambar 1: Struktur dasar dokumen HTML</figcaption>
</figure>
```

| Aspek | Penjelasan |
|-------|-----------|
| **Fungsi** | Mengelompokkan konten ilustratif (gambar, diagram, kode, kutipan) dengan keterangannya. |
| **`<figcaption>`** | Keterangan/caption. Bisa diletakkan sebelum atau sesudah konten. |
| **Manfaat** | Membantu aksesibilitas dan SEO dengan menghubungkan gambar dengan deskripsinya. |

---

### B. Elemen Heading — `<h1>` sampai `<h6>`

```html
<h1>Heading Level 1 — Judul Utama (hanya satu per halaman)</h1>
<h2>Heading Level 2 — Sub Judul</h2>
<h3>Heading Level 3 — Sub-sub Judul</h3>
<h4>Heading Level 4</h4>
<h5>Heading Level 5</h5>
<h6>Heading Level 6</h6>
```

**Tabel Heading:**

| Tag | Tingkat | Penggunaan |
|-----|---------|-----------|
| `<h1>` | Paling penting | Judul halaman. **Hanya SATU** per halaman. Paling penting untuk SEO. |
| `<h2>` | Penting | Sub-judul utama. Bagian besar dari halaman. |
| `<h3>` | Sedang | Sub-bagian dari `<h2>`. |
| `<h4>` | Kurang penting | Sub-bagian lebih detail. |
| `<h5>` | Tidak terlalu penting | Detail kecil. |
| `<h6>` | Paling tidak penting | Paling rendah. Jarang digunakan. |

**Aturan Penting Heading:**

1. **Hierarki**: Heading harus digunakan secara hierarkis. Jangan lompat dari `<h1>` ke `<h3>` tanpa `<h2>`.
   ```html
   <!-- BENAR -->
   <h1>Judul</h1>
   <h2>Sub Judul</h2>
   <h3>Detail</h3>

   <!-- SALAH (lompat hierarki) -->
   <h1>Judul</h1>
   <h3>Detail</h3>
   ```

2. **SEO**: Hanya satu `<h1>` per halaman. Mesin pencari menggunakan heading untuk memahami struktur konten.

3. **Aksesibilitas**: Screen reader menggunakan heading untuk navigasi cepat. Struktur heading yang baik sangat penting.

4. **Styling**: Heading memiliki ukuran default (bisa diubah dengan CSS). Gunakan CSS untuk styling, bukan heading level yang salah hanya untuk ukuran.

---

### C. Elemen Teks & Formatting

#### `<p>` — Paragraf

```html
<p>Ini adalah sebuah paragraf teks. Paragraf secara otomatis memiliki jarak (margin) di atas dan bawahnya.</p>
<p>Ini adalah paragraf kedua. Browser akan menampilkan setiap paragraf sebagai blok baru.</p>
```

| Aspek | Penjelasan |
|-------|-----------|
| **Fungsi** | Mendefinisikan sebuah paragraf teks. |
| **Tipe** | Block-level element. |
| **Atribut** | Atribut global saja (class, id, style, dll). |
| **Catatan** | Jangan gunakan `<p>` untuk konten yang bukan paragraf. Jangan gunakan `<br>` berganda untuk membuat jarak antar paragraf — gunakan CSS `margin` atau `<p>` baru. |

#### `<span>` — Kontainer Inline

```html
<p>Teks ini memiliki <span class="highlight">bagian yang di-highlight</span> dengan warna kuning.</p>
```

| Aspek | Penjelasan |
|-------|-----------|
| **Fungsi** | Kontainer **inline** generik tanpa makna khusus. Biasanya digunakan untuk styling atau manipulasi JavaScript pada bagian kecil teks. |
| **Tipe** | Inline element. |
| **Kapan digunakan** | Ketika tidak ada elemen semantik yang lebih cocok. |

#### `<div>` — Kontainer Blok

```html
<div class="container">
    <h2>Bagian Konten</h2>
    <p>Ini adalah grup elemen yang dibungkus dengan div.</p>
</div>
```

| Aspek | Penjelasan |
|-------|-----------|
| **Fungsi** | Kontainer **block** generik tanpa makna khusus. **Paling sering digunakan** untuk layout dan styling. |
| **Tipe** | Block-level element. |
| **Catatan** | Di HTML5, usahakan gunakan elemen semantik (`<section>`, `<article>`, `<nav>`) daripada `<div>` jika memungkinkan. `<div>` adalah pilihan terakhir jika tidak ada elemen semantik yang cocok. |

#### `<em>` — Penekanan (Emphasis)

```html
<p>Saya <em>sangat</em> suka belajar HTML.</p>
<!-- Tampilan default: miring (italic) -->
```

| Aspek | Penjelasan |
|-------|-----------|
| **Fungsi** | Memberikan **penekanan** pada teks. Mempengaruhi cara screen reader membacakan teks (dengan intonasi berbeda). |
| **Tipe** | Inline element. |
| **Default styling** | `italic` (miring). |
| **Aksesibilitas** | Screen reader akan membacanya dengan penekanan vokal. |
| **Perbedaan dengan `<i>`** | `<i>` hanya untuk tampilan miring tanpa makna penekanan. |

#### `<strong>` — Penting (Strong Importance)

```html
<p><strong>Peringatan!</strong> Jangan bagikan password Anda kepada siapapun.</p>
<!-- Tampilan default: tebal (bold) -->
```

| Aspek | Penjelasan |
|-------|-----------|
| **Fungsi** | Menandai teks dengan **tingkat kepentingan tinggi** (urgensi, serius, bahaya). |
| **Tipe** | Inline element. |
| **Default styling** | `bold` (tebal). |
| **Aksesibilitas** | Screen reader akan membacanya dengan nada lebih tegas. |
| **Perbedaan dengan `<b>`** | `<b>` hanya untuk tampilan tebal tanpa makna. |

#### `<mark>` — Teks yang Ditandai (Highlight)

```html
<p>Bagian yang <mark>paling penting</mark> dalam dokumen ini adalah...</p>
<!-- Tampilan default: background kuning -->
```

| Aspek | Penjelasan |
|-------|-----------|
| **Fungsi** | Menandai atau **menyorot** teks yang relevan (seperti marker/stable). |
| **Tipe** | Inline element. |
| **Default styling** | `background-color: yellow; color: black;` |
| **Penggunaan** | Hasil pencarian, kata kunci, bagian yang perlu diperhatikan. |

#### `<small>` — Teks Kecil

```html
<p>Harga: Rp 100.000 <small>(belum termasuk pajak)</small></p>
```

| Aspek | Penjelasan |
|-------|-----------|
| **Fungsi** | Menampilkan teks dengan ukuran lebih kecil — untuk disclaimer, catatan kaki, hak cipta. |
| **Default styling** | `font-size: smaller` |

#### `<del>` & `<ins>` — Teks yang Dihapus & Disisipkan

```html
<p>Harga lama: <del>Rp 150.000</del> Harga baru: <ins>Rp 100.000</ins></p>
<!-- del: coret tengah, ins: underline -->
```

| Elemen | Fungsi | Default Styling |
|--------|--------|-----------------|
| `<del>` | Teks yang telah **dihapus** dari dokumen. | `text-decoration: line-through` |
| `<ins>` | Teks yang baru **disisipkan** ke dokumen. | `text-decoration: underline` |

#### `<sub>` & `<sup>` — Subscript & Superscript

```html
<p>Rumus kimia air: H<sub>2</sub>O</p>
<p>Persamaan kuadrat: x<sup>2</sup> + 2x + 1 = 0</p>
```

| Elemen | Fungsi | Contoh |
|--------|--------|--------|
| `<sub>` | Teks subscript (lebih rendah). | H₂O, CO₂ |
| `<sup>` | Teks superscript (lebih tinggi). | x², 10¹⁰ |

#### `<blockquote>` & `<q>` — Kutipan

```html
<!-- Kutipan panjang (block) -->
<blockquote cite="https://example.com/sumber">
    <p>"Ilmu pengetahuan tanpa agama adalah pincang." — Albert Einstein</p>
</blockquote>

<!-- Kutipan pendek (inline) -->
<p>Dia berkata, <q cite="https://example.com">HTML itu mudah dipelajari</q>.</p>
```

| Aspek | `<blockquote>` | `<q>` |
|-------|---------------|-------|
| **Tipe** | Block | Inline |
| **Default styling** | Indentasi kiri & kanan | Tanda kutip otomatis |
| **Atribut `cite`** | URL sumber kutipan | URL sumber kutipan |
| **Kapan digunakan** | Kutipan panjang (≥ 1 paragraf) | Kutipan pendek (dalam paragraf) |

#### `<abbr>` — Singkatan / Akronim

```html
<p><abbr title="HyperText Markup Language">HTML</abbr> adalah bahasa markup untuk web.</p>
<!-- Saat di-hover, tooltip akan menampilkan kepanjangan -->
```

| Aspek | Penjelasan |
|-------|-----------|
| **Fungsi** | Menandai singkatan/akronim dan memberikan kepanjangannya. |
| **Atribut `title`** | **WAJIB** — berisi kepanjangan dari singkatan. |
| **Aksesibilitas** | Screen reader akan membacakan `title` saat menemukan `<abbr>`. |
| **Styling** | Default: `text-decoration: underline dotted` (garis bawah titik-titik). |

#### `<address>` — Informasi Kontak

```html
<address>
    Ditulis oleh <a href="mailto:penulis@example.com">John Doe</a>.<br>
    Kunjungi kami di:<br>
    Jl. Merdeka No. 123<br>
    Jakarta, Indonesia
</address>
```

| Aspek | Penjelasan |
|-------|-----------|
| **Fungsi** | Menampilkan informasi kontak penulis/pemilik halaman. |
| **Default styling** | `font-style: italic` (miring). |
| **Catatan** | Hanya untuk kontak. Jangan gunakan untuk alamat sembarang (gunakan `<p>`). |

#### `<code>`, `<pre>`, `<kbd>`, `<samp>`, `<var>` — Kode & Input

```html
<!-- <code>: Kode dalam baris -->
<p>Gunakan fungsi <code>console.log()</code> untuk debugging di JavaScript.</p>

<!-- <pre>: Teks yang telah diformat sebelumnya (mempertahankan spasi & baris baru) -->
<pre>
function halo() {
    console.log("Halo, Dunia!");
}
</pre>

<!-- <kbd>: Input keyboard -->
<p>Tekan <kbd>Ctrl</kbd> + <kbd>C</kbd> untuk menyalin teks.</p>

<!-- <samp>: Output program -->
<p>Program akan menampilkan: <samp>Halo, Dunia!</samp></p>

<!-- <var>: Variabel matematika/programming -->
<p>Nilai <var>x</var> adalah 10.</p>
```

| Elemen | Fungsi | Tipe |
|--------|--------|------|
| `<code>` | Menampilkan kode komputer. | Inline |
| `<pre>` | Teks yang diformat (preformatted) — mempertahankan spasi dan baris baru. | Block |
| `<kbd>` | Input keyboard. | Inline |
| `<samp>` | Output sampel dari program. | Inline |
| `<var>` | Variabel dalam konteks matematika/programming. | Inline |

#### `<time>` — Waktu & Tanggal

```html
<p>Acara akan diadakan pada <time datetime="2026-06-15T09:00:00+07:00">15 Juni 2026, pukul 09:00 WIB</time>.</p>
```

| Aspek | Penjelasan |
|-------|-----------|
| **Fungsi** | Menandai tanggal dan/atau waktu dalam format yang bisa dibaca mesin. |
| **Atribut `datetime`** | Format standar ISO 8601: `YYYY-MM-DDThh:mm:ssTZD` |
| **Manfaat** | Membantu mesin pencari dan aplikasi kalender memahami tanggal. |

#### `<br>` — Baris Baru (Line Break)

```html
<p>Jalan Merdeka No. 123<br>
Jakarta Pusat<br>
Indonesia</p>
```

| Aspek | Penjelasan |
|-------|-----------|
| **Fungsi** | Membuat baris baru dalam teks. **Void element** (tidak perlu tag penutup). |
| **Tipe** | Inline element (void). |
| **Warning** | JANGAN gunakan `<br>` untuk membuat jarak antar paragraf! Gunakan CSS `margin` atau paragraf terpisah. |
| **Penggunaan yang tepat** | Alamat, puisi, lirik lagu, baris dalam alamat. |

#### `<hr>` — Garis Horizontal (Thematic Break)

```html
<h2>Bagian 1</h2>
<p>Konten bagian pertama...</p>

<hr>

<h2>Bagian 2</h2>
<p>Konten bagian kedua...</p>
```

| Aspek | Penjelasan |
|-------|-----------|
| **Fungsi** | Memisahkan konten secara tematis. **Void element**. |
| **Default styling** | Garis horizontal (`border-top: 1px solid`). |
| **Catatan** | Jangan gunakan hanya untuk dekorasi. Gunakan CSS `border` untuk garis dekoratif. |

---

### D. Elemen Tautan & Multimedia

#### `<a>` — Anchor (Hyperlink)

**INI ADALAH SALATU ELEMEN PALING PENTING DALAM HTML!**

```html
<!-- Tautan dasar -->
<a href="https://example.com">Kunjungi Example</a>

<!-- Tautan relatif -->
<a href="/tentang.html">Tentang Kami</a>

<!-- Tautan ke bagian dalam halaman yang sama (anchor) -->
<a href="#bab-2">Langsung ke Bab 2</a>
...
<h2 id="bab-2">Bab 2: CSS</h2>

<!-- Tautan email -->
<a href="mailto:admin@example.com?subject=Pertanyaan&body=Halo%20Admin">Kirim Email</a>

<!-- Tautan telepon (mobile) -->
<a href="tel:+6281234567890">Hubungi: 0812-3456-7890</a>

<!-- Tautan download -->
<a href="file.pdf" download="nama-file-baru.pdf">Download PDF</a>

<!-- Tautan dengan target -->
<a href="https://example.com" target="_blank" rel="noopener noreferrer">Buka di tab baru</a>

<!-- Tombol dengan link (JavaScript) -->
<a href="#" onclick="alert('Hello!'); return false;">Klik Saya</a>

<!-- Tautan tanpa href (hanya untuk JavaScript) -->
<a href="javascript:void(0)" onclick="doSomething()">Aksi</a>
```

**Tabel Atribut `<a>`:**

| Atribut | Fungsi | Nilai yang Valid | Contoh |
|---------|--------|------------------|--------|
| `href` | **Wajib** (untuk link). URL tujuan. | URL absolut, URL relatif, `#id`, `mailto:`, `tel:`, `javascript:` | `href="https://example.com"` |
| `target` | Di mana halaman tujuan akan dibuka. | `_self` (default — tab yang sama), `_blank` (tab baru), `_parent` (frame induk), `_top` (jendela penuh) | `target="_blank"` |
| `rel` | Hubungan halaman saat ini dengan halaman tujuan. | `noopener`, `noreferrer`, `nofollow`, `ugc`, `sponsored`, `external` | `rel="noopener noreferrer"` |
| `download` | Memicu download file. | Nama file opsional | `download="laporan.pdf"` |
| `hreflang` | Bahasa dari halaman tujuan. | Kode bahasa ISO | `hreflang="en"` |
| `type` | Tipe MIME dari halaman tujuan. | `"text/html"`, `"application/pdf"` | `type="application/pdf"` |

**⚠️ KEAMANAN: `target="_blank"` WAJIB pakai `rel="noopener"`**

```html
<!-- AMAN -->
<a href="https://example.com" target="_blank" rel="noopener noreferrer">Link</a>

<!-- TIDAK AMAN (tanpa noopener) -->
<a href="https://example.com" target="_blank">Link</a>
```

**Alasan**: Tanpa `rel="noopener"`, halaman yang dibuka di tab baru bisa mengakses `window.opener` dari halaman asal, yang merupakan celah keamanan (tabnabbing).

#### `<img>` — Gambar

**Void element — tidak perlu tag penutup!**

```html
<!-- Gambar dasar -->
<img src="foto.jpg" alt="Deskripsi foto">

<!-- Gambar dengan ukuran -->
<img src="logo.png" alt="Logo Perusahaan" width="200" height="100">

<!-- Gambar responsif dengan srcset -->
<img src="foto-640.jpg"
     srcset="foto-320.jpg 320w, foto-640.jpg 640w, foto-1280.jpg 1280w"
     sizes="(max-width: 600px) 100vw, 50vw"
     alt="Pemandangan gunung">

<!-- Gambar dengan lazy loading -->
<img src="foto-besar.jpg" alt="Foto besar" loading="lazy">

<!-- Gambar sebagai link -->
<a href="halaman-lain.html">
    <img src="tombol.png" alt="Klik untuk masuk">
</a>
```

**Tabel Atribut `<img>`:**

| Atribut | Status | Fungsi | Contoh Nilai |
|---------|--------|--------|-------------|
| `src` | **WAJIB** | URL/lokasi file gambar. | `"images/foto.jpg"`, `"https://example.com/gambar.png"` |
| `alt` | **WAJIB** | Teks alternatif jika gambar gagal dimuat. Penting untuk aksesibilitas. | `"Foto pemandangan gunung merapi"` |
| `width` | Opsional | Lebar gambar dalam pixel. | `"300"` |
| `height` | Opsional | Tinggi gambar dalam pixel. | `"200"` |
| `loading` | Opsional | Strategi loading gambar. | `"lazy"` (slow loading — direkomendasikan), `"eager"` (muat langsung) |
| `srcset` | Opsional | Kumpulan sumber gambar untuk resolusi berbeda. | `"foto-320w.jpg 320w, foto-640w.jpg 640w"` |
| `sizes` | Opsional | Ukuran gambar berdasarkan media query. | `"(max-width: 600px) 100vw, 50vw"` |
| `decoding` | Opsional | Petunjuk decoding ke browser. | `"async"`, `"sync"`, `"auto"` |
| `fetchpriority` | Opsional | Prioritas fetch. | `"high"`, `"low"`, `"auto"` |

**⚠️ PENTING: `alt` BUKAN opsional!**

- **Gambar informatif**: `alt` harus mendeskripsikan gambar. Misal: `alt="Ilustrasi diagram alur login user"`.
- **Gambar dekoratif**: Gunakan `alt=""` (string kosong) — screen reader akan melewatinya. Jangan pernah menghapus atribut `alt`!
- **Gambar dalam link**: `alt` harus mendeskripsikan tujuan link, bukan gambarnya.

```html
<!-- Gambar dekoratif — alt kosong -->
<img src="garis-pemisah.png" alt="" role="presentation">

<!-- Gambar informatif -->
<img src="grafik-penjualan.png" alt="Grafik penjualan tahun 2026 menunjukkan kenaikan 20%">

<!-- Gambar dalam link -->
<a href="produk.html"><img src="produk-123.jpg" alt="Lihat detail produk Sepatu Nike Air Max"></a>
```

#### `<picture>` — Gambar Responsif (Advanced)

```html
<picture>
    <!-- Format modern WebP untuk browser yang mendukung -->
    <source srcset="foto.webp" type="image/webp">
    <!-- Format AVIF yang lebih baik -->
    <source srcset="foto.avif" type="image/avif">
    <!-- Fallback ke JPEG untuk browser lama -->
    <img src="foto.jpg" alt="Deskripsi foto" loading="lazy">
</picture>
```

| Aspek | Penjelasan |
|-------|-----------|
| **Fungsi** | Memberikan **beberapa sumber gambar** untuk situasi berbeda (format, ukuran layar). |
| **Cara kerja** | Browser akan memilih `<source>` pertama yang cocok, lalu fallback ke `<img>`. |
| **Keuntungan** | Menggunakan format modern (WebP/AVIF) dengan fallback ke JPEG/PNG. |

#### `<figure>` & `<figcaption>` — (Sudah dijelaskan di bagian Semantik)

---

### E. Elemen Daftar (List)

#### `<ul>` & `<ol>` & `<li>` — Daftar Tidak Berurutan & Berurutan

```html
<!-- Unordered List (bullet points) -->
<ul>
    <li>Apel</li>
    <li>Pisang</li>
    <li>Jeruk</li>
</ul>

<!-- Ordered List (nomer) -->
<ol>
    <li>Bangun tidur</li>
    <li>Mandi</li>
    <li>Sarapan</li>
</ol>

<!-- Ordered List dengan tipe berbeda -->
<ol type="A">  <!-- A, B, C, ... -->
    <li>Langkah pertama</li>
    <li>Langkah kedua</li>
</ol>

<ol type="a">  <!-- a, b, c, ... -->
    <li>Item a</li>
    <li>Item b</li>
</ol>

<ol type="I">  <!-- I, II, III, ... -->
    <li>Bab 1</li>
    <li>Bab 2</li>
</ol>

<ol type="i">  <!-- i, ii, iii, ... -->
    <li>Bagian i</li>
    <li>Bagian ii</li>
</ol>

<!-- Ordered List dengan mulai dari angka tertentu -->
<ol start="5">
    <li>Item 5</li>
    <li>Item 6</li>
</ol>

<!-- Ordered List dengan urutan terbalik -->
<ol reversed>
    <li>Peringkat 3</li>
    <li>Peringkat 2</li>
    <li>Peringkat 1</li>
</ol>

<!-- Nested List (daftar bersarang) -->
<ul>
    <li>Buah-buahan
        <ul>
            <li>Apel</li>
            <li>Pisang</li>
            <li>Jeruk</li>
        </ul>
    </li>
    <li>Sayuran
        <ul>
            <li>Bayam</li>
            <li>Wortel</li>
        </ul>
    </li>
</ul>
```

**Tabel Elemen List:**

| Elemen | Tipe | Fungsi |
|--------|------|--------|
| `<ul>` | Block | Daftar dengan bullet (tanpa urutan). |
| `<ol>` | Block | Daftar dengan nomor (berurutan). |
| `<li>` | Block | Item dalam daftar (anak dari `<ul>` atau `<ol>`). |

**Atribut `<ol>`:**

| Atribut | Fungsi | Nilai |
|---------|--------|-------|
| `type` | Jenis penomoran. | `"1"` (default), `"A"`, `"a"`, `"I"`, `"i"` |
| `start` | Angka awal penomoran. | Angka integer (misal: `5`) |
| `reversed` | Urutan terbalik. | Boolean |

#### `<dl>`, `<dt>`, `<dd>` — Daftar Definisi

```html
<dl>
    <dt>HTML</dt>
    <dd>HyperText Markup Language — bahasa markup untuk membuat struktur halaman web.</dd>

    <dt>CSS</dt>
    <dd>Cascading Style Sheets — bahasa untuk mendesain tampilan halaman web.</dd>

    <dt>JavaScript</dt>
    <dd>Bahasa pemrograman untuk menambahkan interaktivitas ke halaman web.</dd>
</dl>
```

| Elemen | Fungsi |
|--------|--------|
| `<dl>` | Daftar definisi (definition list). |
| `<dt>` | Istilah yang akan didefinisikan (definition term). |
| `<dd>` | Definisi/penjelasan dari istilah (definition description). |

---

### F. Elemen Tabel

#### `<table>`, `<tr>`, `<th>`, `<td>` — Tabel

```html
<table>
    <caption>Data Penjualan Bulanan</caption>
    <thead>
        <tr>
            <th>Bulan</th>
            <th>Penjualan (Rp)</th>
            <th>Keuntungan (Rp)</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Januari</td>
            <td>10.000.000</td>
            <td>2.500.000</td>
        </tr>
        <tr>
            <td>Februari</td>
            <td>12.500.000</td>
            <td>3.000.000</td>
        </tr>
        <tr>
            <td>Maret</td>
            <td>8.000.000</td>
            <td>1.800.000</td>
        </tr>
    </tbody>
    <tfoot>
        <tr>
            <td>Total</td>
            <td>30.500.000</td>
            <td>7.300.000</td>
        </tr>
    </tfoot>
</table>
```

**Tabel Elemen Tabel:**

| Elemen | Fungsi | Catatan |
|--------|--------|---------|
| `<table>` | Membungkus seluruh tabel. | |
| `<caption>` | Judul/deskripsi tabel. | Langsung setelah `<table>`, opsional. |
| `<thead>` | Bagian kepala tabel (kolom judul). | Untuk SEO & aksesibilitas. |
| `<tbody>` | Bagian tubuh tabel (data). | |
| `<tfoot>` | Bagian kaki tabel (total/rangkuman). | Bisa diletakkan sebelum/after `<tbody>`. |
| `<tr>` | Baris tabel (table row). | |
| `<th>` | Sel judul (table header). | Cetak tebal & rata tengah secara default. |
| `<td>` | Sel data (table data). | |

**Atribut Penting untuk `<th>` dan `<td>`:**

```html
<!-- colspan: menggabungkan kolom -->
<td colspan="2">Menggabungkan 2 kolom</td>

<!-- rowspan: menggabungkan baris -->
<td rowspan="3">Menggabungkan 3 baris</td>

<!-- scope: untuk aksesibilitas (menjelaskan apakah th untuk kolom atau baris) -->
<th scope="col">Nama</th>        <!-- Judul untuk kolom -->
<th scope="row">Januari</th>     <!-- Judul untuk baris -->

<!-- headers: menghubungkan td dengan th untuk aksesibilitas -->
<td headers="nama-email">user@example.com</td>
```

**Tabel lengkap dengan colspan & rowspan:**

```html
<table border="1">
    <tr>
        <th rowspan="2">Nama</th>
        <th colspan="2">Kontak</th>
    </tr>
    <tr>
        <th>Email</th>
        <th>Telepon</th>
    </tr>
    <tr>
        <td>John Doe</td>
        <td>john@example.com</td>
        <td>08123456789</td>
    </tr>
    <tr>
        <td>Jane Doe</td>
        <td>jane@example.com</td>
        <td>08987654321</td>
    </tr>
</table>
```

**Visual hasil:**

| Nama | Kontak | |
|------|--------|---|
| | Email | Telepon |
| John Doe | john@example.com | 08123456789 |
| Jane Doe | jane@example.com | 08987654321 |

---

### G. Elemen Form — PALING KOMPLEKS

**Form adalah cara untuk mengumpulkan input dari pengguna!**

#### `<form>` — Formulir

```html
<form action="/proses-pendaftaran" method="POST" enctype="multipart/form-data" novalidate>
    <!-- Semua elemen input di sini -->
    <button type="submit">Kirim</button>
</form>
```

**Tabel Atribut `<form>`:**

| Atribut | Fungsi | Nilai yang Valid |
|---------|--------|------------------|
| `action` | URL tujuan pengiriman data. | URL absolut atau relatif. |
| `method` | Metode HTTP pengiriman. | `"GET"` (data di URL — untuk pencarian), `"POST"` (data di body — untuk login/upload). |
| `enctype` | Encoding data saat method=POST. | `"application/x-www-form-urlencoded"` (default), `"multipart/form-data"` (untuk upload file), `"text/plain"` (jarang). |
| `novalidate` | Menonaktifkan validasi HTML5 bawaan. | Boolean (tidak perlu nilai). |
| `target` | Di mana response akan ditampilkan. | `_self`, `_blank`, `_parent`, `_top`. |
| `autocomplete` | Mengaktifkan/mematikan autocomplete. | `"on"` (default), `"off"`. |
| `name` | Nama form (untuk JavaScript). | String. |

#### `<input>` — Elemen Input Paling Serbaguna

**Void element — tidak perlu tag penutup!**

```html
<!-- TEXT — Input teks biasa -->
<input type="text" id="nama" name="nama" placeholder="Masukkan nama lengkap" maxlength="50" required>

<!-- EMAIL — Input email (validasi otomatis) -->
<input type="email" id="email" name="email" placeholder="contoh@email.com" required multiple>

<!-- PASSWORD — Input password (karakter tersembunyi) -->
<input type="password" id="password" name="password" minlength="8" pattern="(?=.*\d)(?=.*[a-z])(?=.*[A-Z]).{8,}" required>

<!-- NUMBER — Input angka -->
<input type="number" id="usia" name="usia" min="0" max="150" step="1" value="25">

<!-- TEL — Input telepon (tidak ada validasi otomatis, hanya untuk mobile keyboard) -->
<input type="tel" id="telepon" name="telepon" pattern="[0-9]{10,15}" placeholder="08123456789">

<!-- URL — Input URL (validasi otomatis) -->
<input type="url" id="website" name="website" placeholder="https://example.com">

<!-- SEARCH — Input pencarian (bisa memiliki tombol clear) -->
<input type="search" id="cari" name="cari" placeholder="Cari..." aria-label="Kotak pencarian">

<!-- DATE — Input tanggal (date picker) -->
<input type="date" id="tanggal" name="tanggal" min="2024-01-01" max="2026-12-31" value="2026-06-01">

<!-- TIME — Input waktu -->
<input type="time" id="waktu" name="waktu" min="09:00" max="17:00">

<!-- DATETIME-LOCAL — Input tanggal & waktu lokal -->
<input type="datetime-local" id="jadwal" name="jadwal">

<!-- MONTH — Input bulan -->
<input type="month" id="bulan" name="bulan">

<!-- WEEK — Input minggu -->
<input type="week" id="minggu" name="minggu">

<!-- COLOR — Color picker -->
<input type="color" id="warna" name="warna" value="#ff0000">

<!-- RANGE — Slider -->
<input type="range" id="volume" name="volume" min="0" max="100" value="50" step="1">

<!-- FILE — Upload file -->
<input type="file" id="dokumen" name="dokumen" accept=".pdf,.doc,.docx" multiple>

<!-- CHECKBOX — Kotak centang (bisa pilih banyak) -->
<input type="checkbox" id="setuju" name="setuju" checked required>
<label for="setuju">Saya setuju dengan syarat dan ketentuan</label>

<!-- RADIO — Tombol radio (hanya bisa pilih satu dalam grup) -->
<input type="radio" id="pria" name="jenis_kelamin" value="pria" checked>
<label for="pria">Pria</label>
<input type="radio" id="wanita" name="jenis_kelamin" value="wanita">
<label for="wanita">Wanita</label>

<!-- SUBMIT — Tombol kirim -->
<input type="submit" value="Kirim Data">

<!-- RESET — Tombol reset (kembali ke nilai default) -->
<input type="reset" value="Reset Form">

<!-- BUTTON — Tombol generik (biasanya untuk JavaScript) -->
<input type="button" value="Klik Saya" onclick="alert('Hello!')">

<!-- HIDDEN — Input tersembunyi (tidak tampak, untuk data background) -->
<input type="hidden" name="token" value="abc123xyz">

<!-- IMAGE — Gambar sebagai tombol submit -->
<input type="image" src="tombol-kirim.png" alt="Kirim" width="100">
```

**Tabel Semua Tipe Input:**

| Tipe `type` | Fungsi | Validasi Bawaan | Keyboard Mobile |
|-------------|--------|-----------------|-----------------|
| `text` | Teks biasa | Tidak ada | Keyboard teks |
| `email` | Alamat email | Memeriksa format email (@) | Keyboard dengan @ |
| `password` | Kata sandi | Teks disembunyikan | Keyboard teks |
| `number` | Angka | Hanya angka, tombol ↑↓ | Keyboard numerik |
| `tel` | Nomor telepon | Tidak ada validasi otomatis | Keyboard telepon |
| `url` | URL | Memeriksa format URL | Keyboard dengan / dan .com |
| `search` | Pencarian | Tombol clear otomatis | Keyboard teks |
| `date` | Tanggal | Date picker, format YYYY-MM-DD | Date picker |
| `time` | Waktu | Format HH:MM | Time picker |
| `datetime-local` | Tanggal & waktu lokal | Format YYYY-MM-DDTHH:MM | Date-time picker |
| `month` | Bulan & tahun | Format YYYY-MM | Month picker |
| `week` | Minggu & tahun | Format YYYY-Www | Week picker |
| `color` | Warna | Color picker | Color picker |
| `range` | Nilai rentang | Slider | Slider |
| `file` | Upload file | Dialog file | File manager |
| `checkbox` | Centang (boolean) | Kotak centang | Checkbox |
| `radio` | Pilihan tunggal | Tombol radio | Radio button |
| `submit` | Kirim form | Tombol submit | - |
| `reset` | Reset form | Tombol reset | - |
| `button` | Tombol generik | Tidak ada fungsi bawaan | - |
| `hidden` | Tersembunyi | Tidak ditampilkan | - |
| `image` | Gambar sebagai tombol | Seperti submit | - |

**Tabel Atribut Global Input:**

| Atribut | Fungsi | Contoh Nilai |
|---------|--------|-------------|
| `type` | Tipe input. | `"text"`, `"email"`, `"password"`, dll. |
| `name` | **WAJIB** untuk pengiriman data. Nama field saat dikirim ke server. | `"username"` |
| `id` | Identifikasi unik (untuk label, CSS, JavaScript). | `"input-username"` |
| `value` | Nilai default input. | `"John Doe"` |
| `placeholder` | Teks petunjuk dalam input. | `"Masukkan nama..."` |
| `required` | Input **WAJIB** diisi. | Boolean |
| `disabled` | Input dinonaktifkan (tidak bisa diisi, tidak dikirim). | Boolean |
| `readonly` | Input hanya-baca (bisa dilihat, tidak bisa diubah, tetap dikirim). | Boolean |
| `maxlength` | Maksimum jumlah karakter. | `50` |
| `minlength` | Minimum jumlah karakter. | `3` |
| `min` | Nilai minimum (untuk number/date). | `0`, `2024-01-01` |
| `max` | Nilai maksimum (untuk number/date). | `100`, `2026-12-31` |
| `step` | Kelipatan nilai (untuk number/range). | `1`, `0.01`, `5` |
| `pattern` | Regex untuk validasi. | `"[A-Za-z]{3,}"` |
| `autocomplete` | Autocomplete browser. | `"on"`, `"off"`, `"name"`, `"email"`, `"username"` |
| `autofocus` | Fokus otomatis saat halaman dimuat. | Boolean |
| `multiple` | Pilih/upload banyak (file, email). | Boolean |
| `accept` | Tipe file yang diterima (untuk type=file). | `".pdf,.jpg"`, `"image/*"`, `"application/pdf"` |
| `checked` | Centang default (untuk checkbox/radio). | Boolean |
| `size` | Lebar input dalam karakter. | `20` |
| `inputmode` | Tipe keyboard yang muncul di mobile. | `"text"`, `"numeric"`, `"decimal"`, `"tel"`, `"email"`, `"url"`, `"search"` |
| `aria-*` | Atribut aksesibilitas ARIA. | berbagai nilai |

#### `<label>` — Label untuk Input

```html
<!-- Cara 1: Membungkus input (implisit) -->
<label>Nama Lengkap:
    <input type="text" name="nama">
</label>

<!-- Cara 2: Menggunakan for (eksplisit — REKOMENDASI) -->
<label for="email">Alamat Email:</label>
<input type="email" id="email" name="email">

<!-- Label dengan aksesibilitas -->
<label for="cari">
    <span class="sr-only">Cari di situs ini</span>
</label>
<input type="search" id="cari" name="cari" placeholder="Cari...">
```

| Atribut | Fungsi |
|---------|--------|
| `for` | Menghubungkan label ke input dengan `id` yang sama. |
| **Manfaat** | Mengklik label akan memfokuskan/mengaktifkan input. Penting untuk checkbox/radio. |

**⚠️ PENTING: Setiap input WAJIB memiliki label!**

Alasan:
1. **Aksesibilitas**: Screen reader membutuhkan label untuk membacakan nama input.
2. **UX**: Mengklik label memfokuskan input — area klik lebih besar.
3. **Validitas HTML**: Validator HTML akan memberi warning jika input tanpa label.

#### `<textarea>` — Input Teks Multibaris

```html
<label for="pesan">Pesan:</label>
<textarea id="pesan" name="pesan" rows="5" cols="40" placeholder="Tulis pesan Anda di sini..." maxlength="500" required></textarea>

<!-- Dengan ukuran tetap (resize: both secara default) -->
<textarea id="alamat" name="alamat" rows="3" style="resize: vertical;">Alamat lengkap...</textarea>
```

| Atribut | Fungsi | Nilai |
|---------|--------|-------|
| `rows` | Jumlah baris (tinggi). | Angka (default: 2) |
| `cols` | Jumlah kolom (lebar). | Angka (default: 20) |
| `maxlength` | Maksimum karakter. | Angka |
| `minlength` | Minimum karakter. | Angka |
| `placeholder` | Teks petunjuk. | Teks |
| `wrap` | Pembungkusan teks. | `"soft"` (default), `"hard"` |
| `readonly` | Hanya baca. | Boolean |
| `disabled` | Nonaktif. | Boolean |

**Perbedaan `<input type="text">` vs `<textarea>`:**

| Fitur | `<input type="text">` | `<textarea>` |
|-------|----------------------|-------------|
| Baris | 1 baris | Banyak baris |
| Value | Atribut `value` | Konten di antara tag |
| Tag penutup | Void element | WAJIB `</textarea>` |
| Resize | Tidak bisa | Bisa di-resize (CSS) |
| Enter | Submit form | Baris baru |

#### `<select>` & `<option>` — Dropdown List

```html
<label for="negara">Negara:</label>
<select id="negara" name="negara" required>
    <option value="">— Pilih Negara —</option>
    <option value="id">Indonesia</option>
    <option value="my">Malaysia</option>
    <option value="sg">Singapura</option>
    <option value="th">Thailand</option>
    <option value="vn" disabled>Vietnam (sedang tidak tersedia)</option>
</select>

<!-- Multiple select (bisa pilih banyak — tahan Ctrl) -->
<label for="hobi">Hobi (pilih beberapa):</label>
<select id="hobi" name="hobi[]" multiple size="4">
    <option value="membaca">Membaca</option>
    <option value="menulis">Menulis</option>
    <option value="coding" selected>Coding</option>
    <option value="musik">Musik</option>
    <option value="olahraga">Olahraga</option>
    <option value="traveling">Traveling</option>
</select>

<!-- Grouped options -->
<label for="makanan">Pilih Makanan:</label>
<select id="makanan" name="makanan">
    <optgroup label="Makanan Indonesia">
        <option value="nasi-goreng">Nasi Goreng</option>
        <option value="sate">Sate</option>
        <option value="gado-gado">Gado-Gado</option>
    </optgroup>
    <optgroup label="Makanan Barat">
        <option value="pasta">Pasta</option>
        <option value="steak">Steak</option>
        <option value="salad">Salad</option>
    </optgroup>
</select>
```

**Atribut `<select>`:**

| Atribut | Fungsi |
|---------|--------|
| `name` | Nama untuk pengiriman data. |
| `multiple` | Bisa memilih banyak opsi. |
| `size` | Jumlah opsi yang terlihat tanpa scroll. |
| `required` | Wajib memilih. |
| `disabled` | Nonaktif. |

**Atribut `<option>`:**

| Atribut | Fungsi |
|---------|--------|
| `value` | Nilai yang dikirim ke server (jika tidak ada, teks option yang dikirim). |
| `selected` | Opsi yang terpilih secara default. |
| `disabled` | Opsi tidak bisa dipilih. |
| `label` | Label alternatif (jarang digunakan). |

**Atribut `<optgroup>`:**

| Atribut | Fungsi |
|---------|--------|
| `label` | **WAJIB** — judul grup. |
| `disabled` | Nonaktifkan seluruh grup. |

#### `<button>` — Tombol

```html
<!-- Tombol submit (default) — mengirim form -->
<button type="submit">Kirim Data</button>

<!-- Tombol reset — mereset form -->
<button type="reset">Reset</button>

<!-- Tombol biasa — untuk JavaScript -->
<button type="button" onclick="alert('Halo!')">Klik Saya</button>

<!-- Tombol dengan ikon dan teks -->
<button type="submit" class="btn btn-primary">
    <svg><!-- icon --></svg>
    <span>Simpan Data</span>
</button>

<!-- Tombol disabled -->
<button type="submit" disabled>Kirim (belum bisa)</button>

<!-- Tombol dengan formaction (override action form) -->
<button type="submit" formaction="/simpan-sementara">Simpan Sementara</button>
```

| Aspek | `<button>` | `<input type="submit">` |
|-------|-----------|-------------------------|
| **Konten** | Bisa berisi HTML (gambar, ikon, teks dengan format). | Hanya teks plain. |
| **Default type** | `submit` (jika di dalam form) | Tergantung `type` |
| **Styling** | Lebih fleksibel | Terbatas |
| **Rekomendasi** | ✅ Gunakan `<button>` untuk semua tombol! | ❌ Hindari kecuali alasan spesifik. |

**Atribut `<button>`:**

| Atribut | Fungsi | Nilai |
|---------|--------|-------|
| `type` | Tipe tombol. | `"submit"` (default), `"reset"`, `"button"` |
| `disabled` | Nonaktif. | Boolean |
| `name` | Nama untuk pengiriman data (jarang). | String |
| `value` | Nilai yang dikirim (jarang). | String |
| `form` | Mengaitkan tombol dengan form (jika di luar form). | ID dari form |
| `formaction` | Override action form (hanya untuk type=submit). | URL |
| `formmethod` | Override method form. | `"GET"`, `"POST"` |
| `formnovalidate` | Override novalidate. | Boolean |

#### `<fieldset>` & `<legend>` — Grup Form

```html
<fieldset>
    <legend>Informasi Pribadi</legend>

    <label for="nama">Nama:</label>
    <input type="text" id="nama" name="nama" required>

    <label for="email">Email:</label>
    <input type="email" id="email" name="email" required>
</fieldset>

<fieldset disabled>
    <legend>Informasi Pembayaran (nonaktif)</legend>
    <label for="kartu">Nomor Kartu:</label>
    <input type="text" id="kartu" name="kartu">
</fieldset>
```

| Aspek | Penjelasan |
|-------|-----------|
| **Fungsi** | Mengelompokkan elemen form yang terkait secara visual dan semantik. |
| **`<legend>`** | Memberikan judul/keterangan untuk grup. |
| **Atribut `disabled`** | Menonaktifkan **semua** input di dalam fieldset sekaligus. |

#### `<datalist>` — Daftar Saran

```html
<label for="buah">Buah favorit:</label>
<input type="text" id="buah" name="buah" list="daftar-buah">
<datalist id="daftar-buah">
    <option value="Apel">
    <option value="Pisang">
    <option value="Jeruk">
    <option value="Mangga">
    <option value="Anggur">
</datalist>
```

| Aspek | Penjelasan |
|-------|-----------|
| **Fungsi** | Menyediakan daftar saran autocomplete untuk input. |
| **Perbedaan dengan `<select>`** | User tetap bisa mengetik teks bebas (tidak terbatas pada opsi). |
| **Hubungan** | Input menggunakan atribut `list` = `id` dari `<datalist>`. |

#### `<progress>` & `<meter>` — Indikator

```html
<!-- Progress bar (indeterminate atau determinate) -->
<label for="download">Progress download:</label>
<progress id="download" value="70" max="100">70%</progress>

<!-- Meter (nilai dalam rentang) -->
<label for="nilai">Nilai ujian:</label>
<meter id="nilai" value="85" min="0" max="100" low="40" high="80" optimum="90">85 dari 100</meter>

<!-- Meter dengan berbagai warna otomatis -->
<p>Baterai: <meter value="0.8" min="0" max="1">80%</meter></p>
```

| Elemen | Fungsi | Atribut Kunci |
|--------|--------|---------------|
| `<progress>` | Menunjukkan progress tugas. | `value`, `max` |
| `<meter>` | Menunjukkan nilai dalam rentang (seperti gauge). | `value`, `min`, `max`, `low`, `high`, `optimum` |

---

### H. Elemen Multimedia

#### `<audio>` — Audio

```html
<!-- Audio dasar dengan kontrol -->
<audio controls>
    <source src="lagu.mp3" type="audio/mpeg">
    <source src="lagu.ogg" type="audio/ogg">
    Browser Anda tidak mendukung elemen audio.
</audio>

<!-- Autoplay (HATI-HATI: banyak browser memblokir autoplay) -->
<audio src="backsound.mp3" autoplay loop muted>
    <!-- muted diperlukan agar autoplay diizinkan beberapa browser -->
</audio>
```

**Atribut `<audio>`:**

| Atribut | Fungsi |
|---------|--------|
| `src` | URL file audio. |
| `controls` | Menampilkan kontrol play/pause/volume/progress. |
| `autoplay` | Putar otomatis saat halaman dimuat. |
| `loop` | Ulang terus menerus. |
| `muted` | Senyap (mute) secara default. |
| `preload` | Strategi preloading: `"none"` (jangan preload), `"metadata"` (preload info saja), `"auto"` (preload penuh). |

#### `<video>` — Video

```html
<!-- Video dasar dengan kontrol -->
<video controls width="640" height="360" poster="thumbnail.jpg">
    <source src="video.mp4" type="video/mp4">
    <source src="video.webm" type="video/webm">
    <source src="video.ogg" type="video/ogg">
    <track src="subtitle_id.vtt" kind="subtitles" srclang="id" label="Bahasa Indonesia">
    <track src="subtitle_en.vtt" kind="subtitles" srclang="en" label="English">
    Browser Anda tidak mendukung elemen video.
</video>

<!-- Video sebagai background (tanpa kontrol) -->
<video autoplay loop muted playsinline>
    <source src="background.mp4" type="video/mp4">
</video>
```

**Atribut `<video>`:**

| Atribut | Fungsi |
|---------|--------|
| `src` | URL file video. |
| `controls` | Menampilkan kontrol video. |
| `autoplay` | Putar otomatis. |
| `loop` | Ulang terus. |
| `muted` | Senyap default. |
| `poster` | Gambar thumbnail sebelum video dimainkan. |
| `width` / `height` | Ukuran player. |
| `preload` | Strategi preloading. |
| `playsinline` | Penting untuk iOS — video tidak fullscreen otomatis. |

Elemen `<track>` digunakan untuk subtitle/teks:

| Atribut | Fungsi |
|---------|--------|
| `src` | File `.vtt` (WebVTT format). |
| `kind` | `"subtitles"` (terjemahan), `"captions"` (dialog + efek suara), `"descriptions"` (deskripsi audio). |
| `srclang` | Bahasa subtitle. |
| `label` | Nama yang ditampilkan di menu subtitle. |
| `default` | Subtitle default. |

#### `<canvas>` — Gambar 2D/3D dengan JavaScript

```html
<canvas id="myCanvas" width="400" height="300">
    Browser Anda tidak mendukung canvas.
</canvas>
```

| Aspek | Penjelasan |
|-------|-----------|
| **Fungsi** | Area gambar yang bisa dimanipulasi dengan JavaScript (2D atau WebGL untuk 3D). |
| **Ukuran** | Atribut `width` & `height` menentukan ukuran kanvas sebenarnya (bukan CSS). |
| **Catatan** | Konten di antara tag adalah fallback jika browser tidak mendukung. |
| **Penggunaan** | Game, grafik, visualisasi data, editing gambar. |

#### `<svg>` — Grafik Vektor

```html
<svg width="100" height="100" viewBox="0 0 100 100" xmlns="http://www.w3.org/2000/svg">
    <circle cx="50" cy="50" r="40" fill="red" stroke="black" stroke-width="3"/>
    <rect x="10" y="10" width="80" height="80" fill="blue" opacity="0.5"/>
</svg>

<!-- SVG sebagai file eksternal -->
<img src="icon.svg" alt="Icon SVG" width="24" height="24">
```

| Aspek | Penjelasan |
|-------|-----------|
| **Fungsi** | Grafik vektor berbasis XML — dapat diperbesar tanpa kehilangan kualitas. |
| **Keunggulan** | Ukuran file kecil, scalable, bisa dimanipulasi CSS/JavaScript. |
| **Format** | Bisa inline di HTML atau file `.svg` eksternal. |

---

### I. Elemen Lainnya

#### `<details>` & `<summary>` — Disclosure Widget

```html
<details>
    <summary>Klik untuk melihat detail lebih lanjut</summary>
    <p>Ini adalah konten yang tersembunyi. User bisa mengklik summary untuk membuka/menutupnya tanpa JavaScript!</p>
    <ul>
        <li>Fitur 1: Mudah digunakan</li>
        <li>Fitur 2: Tanpa JavaScript</li>
        <li>Fitur 3: Aksesibel secara default</li>
    </ul>
</details>

<!-- Terbuka secara default -->
<details open>
    <summary>FAQ: Apa itu HTML?</summary>
    <p>HTML adalah...</p>
</details>
```

| Aspek | Penjelasan |
|-------|-----------|
| **Fungsi** | Widget expand/collapse murni HTML, **tanpa JavaScript**. |
| **`<summary>`** | Judul yang selalu terlihat. |
| **Atribut `open`** | Widget terbuka secara default. |
| **Aksesibilitas** | Bawaan browser sudah aksesibel (keyboard: Enter/Space untuk toggle). |

#### `<dialog>` — Modal/Dialog

```html
<dialog id="myDialog">
    <h2>Selamat Datang!</h2>
    <p>Ini adalah dialog modal HTML5 murni.</p>
    <button id="closeDialog">Tutup</button>
</dialog>

<button id="openDialog">Buka Dialog</button>

<script>
    document.getElementById('openDialog').onclick = function() {
        document.getElementById('myDialog').showModal();
    };
    document.getElementById('closeDialog').onclick = function() {
        document.getElementById('myDialog').close();
    };
</script>
```

| Aspek | Penjelasan |
|-------|-----------|
| **Fungsi** | Elemen dialog/modal native HTML5. |
| **Method** | `.show()` (non-modal), `.showModal()` (modal — dengan overlay), `.close()`. |
| **Catatan** | Browser support meningkat, tapi masih perlu fallback/polyfill untuk browser lama. |

#### `<iframe>` — Bingkai Tertanam

```html
<iframe src="https://example.com" width="800" height="600" title="Contoh iframe" loading="lazy" allowfullscreen></iframe>

<!-- YouTube embed -->
<iframe width="560" height="315" src="https://www.youtube.com/embed/dQw4w9WgXcQ" title="YouTube video" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

<!-- Google Maps embed -->
<iframe src="https://www.google.com/maps/embed?pb=..." width="600" height="450" style="border:0;" allowfullscreen loading="lazy"></iframe>
```

| Atribut | Fungsi |
|---------|--------|
| `src` | URL halaman yang akan ditampilkan. |
| `width` / `height` | Ukuran iframe. |
| `title` | **WAJIB** untuk aksesibilitas — mendeskripsikan konten iframe. |
| `loading` | `"lazy"` (slow loading — rekomendasi). |
| `allow` | Permission policy (apa yang diizinkan: kamera, microphone, fullscreen). |
| `allowfullscreen` | Izinkan fullscreen. |
| `sandbox` | Pembatasan keamanan: `"allow-scripts"`, `"allow-same-origin"`, `"allow-forms"`, dll. |
| `srcdoc` | Konten HTML inline sebagai pengganti `src`. |

---

## 1.4 Elemen Blok vs Inline & Void Elements

### Elemen Block-Level

Elemen block **selalu dimulai di baris baru** dan mengambil **lebar penuh** dari kontainernya.

```html
<p>Ini blok.</p> <p>Ini blok juga.</p>
<div>Div juga block.</div>
<h1>Heading juga block.</h1>
```

**Visual:**
```
┌─────────────────────────────┐
│ Ini blok.                   │
└─────────────────────────────┘
┌─────────────────────────────┐
│ Ini blok juga.              │
└─────────────────────────────┘
┌─────────────────────────────┐
│ Div juga block.             │
└─────────────────────────────┘
```

**Contoh elemen block:**
`<div>`, `<p>`, `<h1>`-`<h6>`, `<ul>`, `<ol>`, `<li>`, `<table>`, `<form>`, `<header>`, `<footer>`, `<section>`, `<article>`, `<nav>`, `<aside>`, `<main>`, `<blockquote>`, `<pre>`, `<hr>`, `<figure>`, `<figcaption>`, `<details>`, `<dialog>`, `<fieldset>`

### Elemen Inline

Elemen inline **tidak memulai baris baru** dan hanya mengambil **lebar sesuai kontennya**.

```html
<p>Ini adalah <strong>teks tebal</strong> dan <em>teks miring</em> dalam satu baris.</p>
```

**Visual:**
```
┌──────────────────────────────────────────────┐
│ Ini adalah ┌──────────┐ dan ┌──────────┐    │
│            │teks tebal│    │teks miring│     │
│            └──────────┘    └──────────┘      │
└──────────────────────────────────────────────┘
```

**Contoh elemen inline:**
`<span>`, `<a>`, `<strong>`, `<em>`, `<b>`, `<i>`, `<u>`, `<mark>`, `<small>`, `<sub>`, `<sup>`, `<code>`, `<kbd>`, `<q>`, `<abbr>`, `<time>`, `<label>`, `<img>`, `<br>`, `<input>`, `<button>`, `<textarea>`, `<select>`

### Void Elements (Elemen Kosong)

**Void element** adalah elemen yang **tidak memiliki konten** dan **tidak memiliki tag penutup**.

```html
<!-- Void elements — tidak perlu </...> -->
<br>
<hr>
<img src="foto.jpg" alt="foto">
<input type="text" name="nama">
<meta charset="UTF-8">
<link rel="stylesheet" href="style.css">
<source src="video.mp4" type="video/mp4">
<track src="subtitle.vtt" kind="subtitles">
<wbr>  <!-- Word break opportunity -->
<area>  <!-- Area dalam image map -->
<col>   <!-- Kolom dalam tabel -->
<embed> <!-- Plugin embed -->
<param> <!-- Parameter untuk plugin -->
```

**Daftar Lengkap Void Elements di HTML5:**

`<area>`, `<base>`, `<br>`, `<col>`, `<embed>`, `<hr>`, `<img>`, `<input>`, `<link>`, `<meta>`, `<param>`, `<source>`, `<track>`, `<wbr>`

> **Catatan**: Void elements di HTML5 **tidak boleh** menggunakan self-closing tag `/>` seperti di XHTML. ` <br> ` valid, ` <br/> ` juga valid di HTML5, tapi direkomendasikan tanpa slash.

### Nesting yang Benar

Aturan dasar nesting:
1. **Elemen block bisa berisi elemen block dan inline.**
2. **Elemen inline HANYA bisa berisi elemen inline (atau teks), TIDAK boleh berisi elemen block.**
3. **Elemen harus ditutup dalam urutan terbalik dari pembukaannya** (LIFO — Last In First Out).

```html
<!-- ✅ BENAR -->
<div>
    <p>Paragraf dengan <strong>teks tebal</strong> di dalamnya.</p>
</div>

<!-- ✅ BENAR: Inline di dalam block -->
<p><span>Teks</span> dan <a href="#">link</a>.</p>

<!-- ✅ BENAR: Block di dalam block -->
<section>
    <article>
        <h2>Judul</h2>
        <p>Konten</p>
    </article>
</section>

<!-- ❌ SALAH: Block di dalam inline -->
<span>
    <p>Ini tidak valid!</p>
</span>

<!-- ❌ SALAH: Penutupan tidak sesuai urutan -->
<div><p>Teks</div></p>
<!-- Harusnya: <div><p>Teks</p></div> -->

<!-- ❌ SALAH: href di tag yang salah -->
<p href="link.html">Teks</p>  <!-- href hanya untuk <a> -->
```

**Aturan Khusus `<a>` di HTML5:**
Di HTML5, elemen `<a>` bisa **membungkus block element** (kecuali `<a>` lain, `<button>`, dan elemen interaktif lainnya).

```html
<!-- ✅ HTML5: Link membungkus beberapa elemen -->
<a href="artikel.html" class="card-link">
    <article>
        <h2>Judul Artikel</h2>
        <p>Deskripsi singkat artikel...</p>
        <img src="thumbnail.jpg" alt="Thumbnail">
    </article>
</a>
```

---

## 1.5 Tabel Ringkasan Atribut Global

Atribut global adalah atribut yang bisa digunakan di **SEMUA** elemen HTML (kecuali beberapa elemen spesifik).

| Atribut | Fungsi | Nilai yang Valid | Contoh |
|---------|--------|------------------|--------|
| `class` | Memberikan satu atau lebih nama kelas untuk CSS/JavaScript. | Satu atau lebih string, dipisah spasi. | `class="container utama highlight"` |
| `id` | Identifikasi **UNIK** untuk satu elemen. Hanya satu per halaman! | String (tanpa spasi, harus unik). | `id="header-utama"` |
| `style` | CSS inline untuk element spesifik. | Deklarasi CSS (`property: value;`). | `style="color: red; font-size: 16px;"` |
| `title` | Informasi tambahan (tooltip saat hover). | Teks. | `title="Klik untuk detail"` |
| `data-*` | Data kustom (custom data attributes) untuk JavaScript. | String setelah `data-`. | `data-user-id="123"` `data-product-name="Buku"` |
| `hidden` | Menyembunyikan elemen (seperti `display: none`). | Boolean (cukup `hidden` saja). | `hidden` |
| `tabindex` | Urutan fokus saat tekan Tab. | Integer: `-1` (tidak bisa fokus Tab), `0` (urutan dokumen), positif (urutan kustom). | `tabindex="0"` `tabindex="-1"` |
| `contenteditable` | Apakah konten elemen bisa diedit oleh user. | `"true"`, `"false"`, `"inherit"`. | `contenteditable="true"` |
| `draggable` | Apakah elemen bisa di-drag. | `"true"`, `"false"`, `"auto"`. | `draggable="true"` |
| `lang` | Bahasa konten elemen. | Kode bahasa ISO. | `lang="id"`, `lang="en-US"` |
| `dir` | Arah teks. | `"ltr"`, `"rtl"`, `"auto"`. | `dir="rtl"` |
| `spellcheck` | Apakah spell checker diaktifkan. | `"true"`, `"false"`. | `spellcheck="true"` |
| `translate` | Apakah konten harus diterjemahkan saat halaman diterjemahkan. | `"yes"`, `"no"`. | `translate="no"` |
| `accesskey` | Pintasan keyboard untuk mengaktifkan elemen. | Satu karakter. | `accesskey="s"` (Alt+S) |
| `autocapitalize` | Kontrol kapitalisasi otomatis. | `"off"`, `"none"`, `"on"`, `"sentences"`, `"words"`, `"characters"`. | `autocapitalize="sentences"` |
| `slot` | Untuk Web Components / Shadow DOM. | Nama slot. | `slot="header"` |
| `is` | Untuk custom elements (Web Components). | Nama elemen kustom. | `is="my-button"` |
| `part` | Mengekspos bagian elemen untuk styling dari luar Shadow DOM. | Nama part. | `part="icon"` |
| `exportparts` | Ekspor part dari elemen turunan. | Nama part. | `exportparts="icon: my-icon"` |

### Atribut Event Handler (on-*)

Atribut ini juga global dan bisa ditambahkan ke elemen mana pun:

| Atribut Event | Dipicu Saat |
|---------------|-------------|
| `onclick` | Elemen diklik. |
| `ondblclick` | Elemen di-double-click. |
| `onmouseover` | Mouse masuk ke area elemen. |
| `onmouseout` | Mouse keluar dari area elemen. |
| `onmouseenter` | Mouse masuk (tidak bubbling — lebih stabil). |
| `onmouseleave` | Mouse keluar (tidak bubbling). |
| `onmousedown` | Tombol mouse ditekan. |
| `onmouseup` | Tombol mouse dilepas. |
| `onkeydown` | Tombol keyboard ditekan. |
| `onkeyup` | Tombol keyboard dilepas. |
| `onkeypress` | Tombol keyboard ditekan dan menghasilkan karakter. |
| `onfocus` | Elemen mendapat fokus. |
| `onblur` | Elemen kehilangan fokus. |
| `onchange` | Nilai input berubah (setelah blur). |
| `oninput` | Nilai input berubah (setiap ketikan). |
| `onsubmit` | Form di-submit (hanya di `<form>`). |
| `onload` | Elemen selesai dimuat (body, img, iframe). |
| `onerror` | Error saat memuat elemen (img, script). |
| `onscroll` | Elemen di-scroll. |
| `onresize` | Jendela di-resize (hanya di `window`). |
| `oncontextmenu` | Klik kanan (context menu). |
| `ontouchstart` | Sentuhan mulai (mobile). |
| `ontouchend` | Sentuhan selesai (mobile). |

> **⚠️ PENTING**: Meskipun event handler bisa ditulis langsung di HTML (inline JavaScript), praktik terbaik adalah **memisahkan JavaScript** — gunakan `addEventListener()` di file JavaScript eksternal.

---

# 🎨 BAGIAN 2: CSS (Cascading Style Sheets)

## 2.1 Cara Kerja CSS

### Apa Itu CSS?

**CSS** = **Cascading Style Sheets** — bahasa yang digunakan untuk mendeskripsikan **tampilan** dan **format** dari dokumen HTML.

```
HTML = Struktur rumah (kerangka, tembok, pintu)
CSS  = Dekorasi rumah (cat, wallpaper, furniture, lampu)
```

### Konsep Dasar CSS

#### 1. Cascading (Berjenjang)

CSS adalah singkatan dari **Cascading** — artinya ada hierarki prioritas saat beberapa aturan CSS bertabrakan.

**Urutan prioritas (dari rendah ke tinggi):**
1. **User Agent** (style default browser)
2. **User** (style dari pengaturan browser pengguna)
3. **Author** (style yang ditulis developer — ANDA)
4. **!important** (pengambil-alih paksa)

**Aturan spesifisitas (dalam Author styles):**
```
Inline style  >  ID selector  >  Class/Pseudo-class  >  Type selector
(1000)            (100)              (10)                   (1)
```

**Contoh Cascading:**
```css
/* Spesifisitas: 0,0,0,1 */
p {
    color: blue;
}

/* Spesifisitas: 0,0,1,0 */
.text {
    color: green;
}

/* Spesifisitas: 0,1,0,0 */
#special {
    color: red;
}

/* Inline style: 1,0,0,0 */
```

```html
<p id="special" class="text" style="color: orange;">Apa warna saya?</p>
<!-- Jawaban: ORANGE (inline menang) -->
<!-- Tapi jika tanpa inline, RED (ID selector menang) -->
```

#### 2. Specificity (Spesifisitas)

Sistem perhitungan prioritas selektor:

| Level | Selektor | Nilai |
|-------|----------|-------|
| Inline style | Atribut `style=""` | 1,0,0,0 |
| ID | `#header`, `#content` | 0,1,0,0 |
| Class, Pseudo-class, Attribute | `.class`, `:hover`, `[type]` | 0,0,1,0 |
| Type (element) | `div`, `p`, `h1` | 0,0,0,1 |

**Cara menghitung:**
```css
/* 0,0,0,1 — satu element selector */
p { color: red; }

/* 0,1,0,0 — satu ID selector */
#content { color: blue; }

/* 0,0,1,1 — satu class + satu element */
p.text { color: green; }

/* 0,1,1,1 — satu ID + satu class + satu element */
div#content.card { color: purple; }

/* 0,0,2,0 — dua class */
.nav.item { color: orange; }
```

#### 3. Inheritance (Pewarisan)

Beberapa properti CSS **diwariskan** dari elemen induk ke elemen anak.

```css
/* Properti yang diwariskan (inherited): */
/* color, font-family, font-size, font-weight, line-height, text-align, visibility, cursor, dll. */

body {
    color: #333;         /* Diwariskan ke semua teks */
    font-family: Arial;  /* Diwariskan */
    font-size: 16px;     /* Diwariskan */
}

/* Properti yang TIDAK diwariskan: */
/* margin, padding, border, background, width, height, display, position, dll. */
```

**Kontrol inheritance:**
```css
.child {
    /* Memaksa mewarisi nilai dari induk */
    color: inherit;

    /* Mengambil nilai awal/default (bukan warisan) */
    color: initial;

    /* Kembali ke nilai natural (inherit jika bisa, initial jika tidak) */
    color: unset;

    /* Kembalikan ke nilai yang diwariskan (jika ada), atau initial */
    color: revert;
}
```

#### 4. Box Model

**Setiap elemen HTML pada dasarnya adalah sebuah kotak!**

```
┌─────────────────────────────────────────────────────┐
│  MARGIN (luar — transparan)                         │
│  ┌───────────────────────────────────────────────┐  │
│  │  BORDER (garis tepi)                          │  │
│  │  ┌─────────────────────────────────────────┐  │  │
│  │  │  PADDING (dalam — transparan)           │  │  │
│  │  │  ┌───────────────────────────────────┐  │  │  │
│  │  │  │  CONTENT (isi — teks/gambar)      │  │  │  │
│  │  │  │                                   │  │  │  │
│  │  │  └───────────────────────────────────┘  │  │  │
│  │  └─────────────────────────────────────────┘  │  │
│  └───────────────────────────────────────────────┘  │
└─────────────────────────────────────────────────────┘
```

**Rumus lebar total elemen:**
```
Lebar total = width + padding-left + padding-right + border-left + border-right + margin-left + margin-right
```

```css
.box {
    width: 300px;
    padding: 20px;      /* Tambah 20px kiri + 20px kanan = 40px */
    border: 5px solid;   /* Tambah 5px kiri + 5px kanan = 10px */
    margin: 10px;        /* Tambah 10px kiri + 10px kanan = 20px */
    /* Lebar TOTAL = 300 + 40 + 10 + 20 = 370px */
}
```

**Solusi: Gunakan `box-sizing: border-box`**
```css
* {
    box-sizing: border-box;  /* Mengubah cara perhitungan */
}

.box {
    width: 300px;
    padding: 20px;
    border: 5px solid;
    /* Dengan border-box, lebar TOTAL = 300px */
    /* Content akan menyusut menjadi: 300 - 40 - 10 = 250px */
}
```

---

## 2.2 Tiga Cara Implementasi CSS

### 1. Inline CSS

```html
<p style="color: red; font-size: 18px; margin-bottom: 10px;">
    Teks ini di-styling dengan CSS inline.
</p>
```

| Kelebihan | Kekurangan |
|-----------|-----------|
| Prioritas tinggi (override style lain). | Sulit di-maintain. |
| Berguna untuk testing/quick fix. | Tidak reusable. |
| Cocok untuk dynamic style dari JavaScript. | Mencampur konten dengan presentasi. |
| Prioritas tertinggi (setelah !important). | Tidak bisa gunakan pseudo-class (:hover). |

### 2. Internal CSS (Embedded)

```html
<head>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f5f5f5;
        }
        h1 {
            color: navy;
            text-align: center;
        }
        .card {
            background: white;
            padding: 20px;
            border-radius: 8px;
        }
    </style>
</head>
```

| Kelebihan | Kekurangan |
|-----------|-----------|
| Semua style di satu tempat (dalam file HTML). | Hanya berlaku untuk satu halaman. |
| Bisa gunakan selektor dan pseudo-class. | Jika banyak CSS, file HTML jadi besar. |
| Cocok untuk halaman tunggal / landing page. | Tidak efisien untuk multi-page. |
| Tidak perlu file eksternal tambahan. | Tidak bisa di-cache browser secara optimal. |

### 3. Eksternal CSS (Linked — REKOMENDASI)

```html
<head>
    <link rel="stylesheet" href="style.css">
    <!-- Bisa juga multiple stylesheets -->
    <link rel="stylesheet" href="reset.css">
    <link rel="stylesheet" href="main.css">
</head>
```

```css
/* style.css — file terpisah */
body {
    font-family: 'Inter', sans-serif;
    line-height: 1.6;
}

h1 {
    color: #2c3e50;
}
```

| Kelebihan | Kekurangan |
|-----------|-----------|
| **Reusable** — satu file CSS untuk banyak halaman. | Butuh request HTTP tambahan (tapi bisa di-cache). |
| **Separation of concerns** — HTML hanya struktur, CSS hanya gaya. | File terpisah bisa hilang/gagal dimuat. |
| **Cacheable** — browser bisa menyimpan file CSS. | - |
| **Mudah di-maintain** — ubah satu file, semua halaman berubah. | - |
| **Best practice** untuk semua proyek web profesional. | - |

### Perbandingan & Rekomendasi

| Aspek | Inline | Internal | Eksternal |
|-------|--------|----------|-----------|
| Prioritas | ⭐ Tertinggi | ⭐⭐ Sedang | ⭐⭐ Terendah |
| Reusability | ❌ Tidak | ❌ Satu halaman | ✅ Semua halaman |
| Maintainability | ❌ Sulit | ⭐ Lumayan | ✅✅ Mudah |
| Performa | ⭐ Cepat (1 request) | ⭐ Cepat (1 request) | ⭐⭐ Cacheable |
| **Kapan pakai** | Debugging/JS | Halaman tunggal | ✅ **Semua proyek serius** |

**Rekomendasi: Gunakan EKSTERNAL CSS sebagai utama. Inline/internal hanya untuk kasus spesifik.**

---

## 2.3 Daftar Lengkap Selektor CSS

### A. Selektor Dasar

#### 1. Type Selector (Elemen)

```css
/* Memilih semua elemen dengan tag tertentu */
p {
    color: blue;
}

h1 {
    font-size: 32px;
}

div {
    background: #f0f0f0;
}
```

```html
<p>❌ Biru</p>
<h1>❌ Ukuran 32px</h1>
<div>❌ Background abu-abu</div>
<span>❌ Tidak terpengaruh</span>
```

#### 2. Class Selector (.)

```css
/* Memilih semua elemen dengan class tertentu */
.highlight {
    background-color: yellow;
    font-weight: bold;
}

.card {
    border: 1px solid #ddd;
    padding: 20px;
    border-radius: 8px;
}

/* Kombinasi class */
.card.featured {
    border-color: gold;
    box-shadow: 0 4px 12px rgba(255, 215, 0, 0.3);
}

/* Elemen dengan class spesifik */
span.icon {
    font-size: 24px;
}
```

```html
<p class="highlight">❌ Background kuning</p>
<div class="card">❌ Card biasa</div>
<div class="card featured">❌ Card dengan border emas</div>
<span class="icon">❌ Icon 24px</span>
```

#### 3. ID Selector (#)

```css
/* Memilih satu elemen dengan ID tertentu */
#header {
    background: #2c3e50;
    color: white;
    padding: 20px;
}

#main-content {
    max-width: 1200px;
    margin: 0 auto;
}

/* Hindari kombinasi yang tidak perlu */
div#header { /* Boleh, tapi tidak perlu — ID sudah unik */
    height: 80px;
}
```

```html
<div id="header">❌ Header dengan background gelap</div>
<main id="main-content">❌ Konten utama dengan lebar 1200px</main>
```

**⚠️ PENTING: ID harus UNIK dan hanya satu per halaman!**

#### 4. Universal Selector (*)

```css
/* Memilih SEMUA elemen */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

/* Memilih semua elemen di dalam .container */
.container * {
    font-family: Arial, sans-serif;
}

/* Memilih semua elemen langsung anak dari nav */
nav > * {
    padding: 10px;
}
```

**⚠️ Peringatan Performa:** `*` bisa lambat jika digunakan tanpa konteks. Hindari `* { ... }` pada properti yang kompleks.

---

### B. Kombinator

Kombinator adalah karakter yang menghubungkan dua atau lebih selektor.

```css
/* ════════════════════════════════════ */
/* 1. DESCENDANT COMBINATOR (spasi)     */
/* ════════════════════════════════════ */
/* Memilih semua elemen p di DALAM article, berapa pun levelnya */
article p {
    color: #555;
    line-height: 1.6;
}

/* ════════════════════════════════════ */
/* 2. CHILD COMBINATOR (>)             */
/* ════════════════════════════════════ */
/* Memilih hanya elemen p yang LANGSUNG anak dari article */
article > p {
    margin-bottom: 1em;
}

/* ════════════════════════════════════ */
/* 3. ADJACENT SIBLING COMBINATOR (+)  */
/* ════════════════════════════════════ */
/* Memilih p yang LANGSUNG setelah h2 (bersaudara) */
h2 + p {
    font-weight: bold;
    color: #333;
}

/* ════════════════════════════════════ */
/* 4. GENERAL SIBLING COMBINATOR (~)   */
/* ════════════════════════════════════ */
/* Memilih SEMUA p yang SETELAH h2 (bersaudara) */
h2 ~ p {
    color: #666;
}
```

**Visualisasi Kombinator:**

```html
<article>
    <h2>Judul Artikel</h2>          <!-- h2 -->
    <p>Paragraf 1 (adjacent sibling: h2 + p)</p>      <!-- ✅ + dan ~ -->
    <div>
        <p>Paragraf 2 (descendant)</p>                <!-- ✅ descendant -->
        <p>Paragraf 3 (descendant)</p>                <!-- ✅ descendant -->
    </div>
    <p>Paragraf 4 (general sibling: h2 ~ p)</p>       <!-- ✅ ~ (tapi bukan +) -->
</article>
```

**Hasil:**
- `article p` → Paragraf 1, 2, 3, 4 (semua)
- `article > p` → Paragraf 1, 4 (langsung anak)
- `h2 + p` → Paragraf 1 (langsung setelah h2)
- `h2 ~ p` → Paragraf 1, 4 (setelah h2, di level sama)

---

### C. Pseudo-class

Pseudo-class menambahkan gaya ke elemen berdasarkan **status** atau **posisi** — bukan berdasarkan nama elemen.

#### 1. Pseudo-class Interaktif (User Action)

```css
/* Link yang BELUM pernah dikunjungi */
a:link {
    color: blue;
}

/* Link yang SUDAH pernah dikunjungi */
a:visited {
    color: purple;
}

/* Saat mouse di atas elemen (hover) */
a:hover {
    color: red;
    text-decoration: underline;
}

/* Saat elemen sedang aktif/ditekan (misal: tombol diklik) */
button:active {
    transform: scale(0.95);
}

/* Saat elemen mendapat fokus (input, link, atau tabindex) */
input:focus {
    outline: 2px solid #4A90D9;
    outline-offset: 2px;
}

/* Saat elemen kehilangan fokus — jarang digunakan, lebih sering :focus */
```

```html
<a href="#">Link biasa</a>
<button>Tombol</button>
<input type="text" placeholder="Fokus di sini">
```

**⚠️ PENTING: Urutan LVHA (LoVe HAte) untuk link:**
```css
/* Urutan ini PENTING agar tidak saling menimpa */
a:link    { color: blue; }      /* Link belum dikunjungi */
a:visited { color: purple; }    /* Link sudah dikunjungi */
a:hover   { color: red; }       /* Hover */
a:active  { color: orange; }    /* Sedang diklik */
```

#### 2. Pseudo-class Struktural

```css
/* Elemen pertama di antara saudara-saudaranya */
li:first-child {
    font-weight: bold;
}

/* Elemen terakhir di antara saudara-saudaranya */
li:last-child {
    border-bottom: none;
}

/* Elemen ke-n (mulai dari 1) */
li:nth-child(2) {
    color: red;            /* Anak kedua */
}

li:nth-child(odd) {
    background: #f9f9f9;   /* Anak ganjil (1, 3, 5, ...) */
}

li:nth-child(even) {
    background: #e9e9e9;   /* Anak genap (2, 4, 6, ...) */
}

li:nth-child(3n+1) {
    background: yellow;    /* Setiap anak ke-3 mulai dari 1: 1, 4, 7, ... */
}

/* n = 0, 1, 2, 3, ... (dimulai dari 1) */
/* Rumus: an + b  — a = interval, b = offset */
/* 2n   = 2, 4, 6, ... (genap) */
/* 2n+1 = 1, 3, 5, ... (ganjil) */
/* 3n   = 3, 6, 9, ... (kelipatan 3) */
/* n+4  = 4, 5, 6, ... (mulai dari 4) */
/* -n+3 = 1, 2, 3      (tiga pertama) */

/* Anak ke-n dari TIPE tertentu */
p:nth-of-type(2) {
    color: green;          /* Paragraf kedua di antara paragraf lain */
}

/* Elemen yang merupakan satu-satunya anak */
li:only-child {
    font-size: 1.2em;
}

/* Elemen yang merupakan satu-satunya dari tipenya */
p:only-of-type {
    font-style: italic;
}

/* Elemen pertama dari tipenya */
p:first-of-type {
    margin-top: 0;
}

/* Elemen terakhir dari tipenya */
p:last-of-type {
    margin-bottom: 0;
}
```

#### 3. Pseudo-class UI (Form)

```css
/* Input yang WAJIB diisi */
input:required {
    border-left: 4px solid red;
}

/* Input yang OPSIONAL */
input:optional {
    border-left: 4px solid gray;
}

/* Input yang valid */
input:valid {
    border-color: green;
}

/* Input yang tidak valid */
input:invalid {
    border-color: red;
}

/* Input yang berada dalam rentang (number/range) */
input:in-range {
    background: #e8f5e9;
}

/* Input di luar rentang */
input:out-of-range {
    background: #ffebee;
}

/* Input yang readonly */
input:read-only {
    background: #f5f5f5;
    cursor: not-allowed;
}

/* Input yang disabled */
input:disabled {
    opacity: 0.5;
    cursor: not-allowed;
}

/* Input yang enabled (default — semua input) */
input:enabled {
    cursor: text;
}

/* Checkbox/radio yang CHECKED */
input:checked {
    accent-color: #4CAF50;
}

/* Checkbox/radio yang indeterminate (belum ditentukan) */
input:indeterminate {
    /* Untuk checkbox yang tidak centang/tidak tidak centang */
}

/* Placeholder sedang tampil */
input:placeholder-shown {
    font-style: italic;
    color: #999;
}

/* Input yang default (dalam grup radio/checkbox) */
input:default {
    outline: 2px solid blue;
}
```

#### 4. Pseudo-class Negasi & Lainnya

```css
/* Negasi — elemen yang TIDAK cocok dengan selektor */
input:not([type="submit"]) {
    border: 1px solid #ccc;
}

/* Semua p kecuali yang memiliki class .skip */
p:not(.skip) {
    color: black;
}

/* Elemen yang memiliki fokus */
:focus {
    outline: 2px solid #4A90D9;
}

/* Elemen yang menjadi target (href=#id) */
:target {
    background: yellow;
    padding: 10px;
}

/* Elemen yang TIDAK memiliki anak (kosong) */
div:empty {
    display: none;
}

/* Root element (html) — selector ini mirip html */
:root {
    --primary-color: #3498db;
    --secondary-color: #2ecc71;
}

/* Elemen yang dipilih/di-select user */
::selection {
    background: #3498db;
    color: white;
}

/* CSS3: Element dengan ruang untuk scroll */
:scope {
    /* Dalam konteks scope tertentu */
}

/* Elemen yang memiliki konten tertentu (CSS4 — belum didukung penuh) */
/* p:has(span) { ... } */
```

---

### D. Pseudo-element

Pseudo-element memungkinkan Anda menata **bagian spesifik** dari elemen, atau menyisipkan konten sebelum/sesudah elemen.

#### `::before` dan `::after`

```css
/* ═══════════════════════════════ */
/* ::before — Sebelum konten */
/* ═══════════════════════════════ */
.quote::before {
    content: "\201C";           /* Tanda kutip buka Unicode */
    font-size: 2em;
    color: #999;
    position: absolute;
    left: -10px;
    top: -10px;
}

/* ═══════════════════════════════ */
/* ::after — Setelah konten */
/* ═══════════════════════════════ */
.required::after {
    content: " *";
    color: red;
    font-weight: bold;
}

/* ═══════════════════════════════ */
/* Contoh: Tooltip */
/* ═══════════════════════════════ */
[data-tooltip] {
    position: relative;
}

[data-tooltip]::after {
    content: attr(data-tooltip);
    position: absolute;
    bottom: 100%;
    left: 50%;
    transform: translateX(-50%);
    background: #333;
    color: white;
    padding: 5px 10px;
    border-radius: 4px;
    font-size: 12px;
    white-space: nowrap;
    opacity: 0;
    transition: opacity 0.3s;
    pointer-events: none;
}

[data-tooltip]:hover::after {
    opacity: 1;
}
```

```html
<p class="quote">Ini adalah kutipan yang menarik</p>
<label class="required">Nama Lengkap</label>
<button data-tooltip="Klik untuk menyimpan">Simpan</button>
```

**⚠️ PENTING: `content` WAJIB untuk `::before` dan `::after`!**

```css
.element::before {
    /* WAJIB ada content, minimal string kosong */
    content: "";
    /* content: "teks"; */
    /* content: url(icon.svg); */
    /* content: attr(data-custom); */
    /* content: counter(mycounter); */
    /* content: open-quote; */
}
```

#### `::first-line` — Baris Pertama

```css
/* Baris pertama paragraf (responsif — tergantung lebar) */
p::first-line {
    font-weight: bold;
    font-size: 1.2em;
    color: #2c3e50;
    font-variant: small-caps;
}
```

```html
<p>Ini adalah baris pertama yang akan di-bold. Baris kedua tidak akan terpengaruh. Baris ketiga juga tidak. Lorem ipsum dolor sit amet...</p>
```

#### `::first-letter` — Huruf Pertama

```css
/* Huruf pertama paragraf (drop cap) */
p::first-letter {
    font-size: 3em;
    font-weight: bold;
    color: #e74c3c;
    float: left;
    margin-right: 8px;
    line-height: 1;
    font-family: 'Georgia', serif;
}
```

#### `::selection` — Teks Terpilih

```css
/* Warna teks yang dipilih user */
::selection {
    background: #3498db;
    color: white;
}

/* Kustomisasi per elemen */
p::selection {
    background: #e74c3c;
    color: white;
}
```

#### `::placeholder` — Placeholder Input (Modern)

```css
/* CSS3 — pseudo-element untuk placeholder */
input::placeholder {
    color: #999;
    font-style: italic;
    opacity: 1;  /* Firefox mengurangi opacity default */
}

/* Prefix untuk browser lama */
input::-webkit-input-placeholder {
    color: #999;
}
input:-moz-placeholder {
    color: #999;
}
```

**Tabel Perbedaan Pseudo-class vs Pseudo-element:**

| Fitur | Pseudo-class | Pseudo-element |
|-------|-------------|----------------|
| **Sintaks** | Satu titik dua (`:`) | Dua titik dua (`::`) |
| **Fungsi** | Status/posisi elemen | Bagian spesifik elemen |
| **Contoh** | `:hover`, `:first-child` | `::before`, `::first-line` |
| **CSS1/2** | `:link`, `:visited` | `:before` (satu titik dua — CSS2) |
| **CSS3** | `:nth-child()`, `:not()` | `::before` (dua titik dua) |
| **Catatan** | Browser tetap dukung `:before` (satu titik dua) untuk kompatibilitas |

---

### E. Attribute Selector

```css
/* ═══════════════════════════════ */
/* [attr] — Memiliki atribut tertentu */
/* ═══════════════════════════════ */
[disabled] {
    opacity: 0.5;
    cursor: not-allowed;
}

[hidden] {
    display: none;
}

/* ═══════════════════════════════ */
/* [attr=value] — Nilai TEPAT */
/* ═══════════════════════════════ */
[type="submit"] {
    background: #3498db;
    color: white;
    border: none;
    padding: 10px 20px;
}

[target="_blank"]::after {
    content: " ↗";
}

/* ═══════════════════════════════ */
/* [attr~=value] — Mengandung kata (dipisah spasi) */
/* ═══════════════════════════════ */
[class~="featured"] {
    border: 2px solid gold;
}
/* Cocok: class="card featured" — ✅  */
/* Tidak cocok: class="featured-card" — ❌ */

/* ═══════════════════════════════ */
/* [attr|=value] — Diawali dengan value (dilanjutkan -) */
/* ═══════════════════════════════ */
[lang|="en"] {
    font-family: 'Georgia', serif;
}
/* Cocok: lang="en", lang="en-US", lang="en-GB" */
/* Tidak cocok: lang="english" */

[class|="btn"] {
    font-weight: bold;
}
/* Cocok: class="btn", class="btn-primary", class="btn-secondary" */

/* ═══════════════════════════════ */
/* [attr^=value] — Diawali dengan (prefix) */
/* ═══════════════════════════════ */
a[href^="https"] {
    color: green;          /* Link aman */
}

a[href^="http://"] {
    color: orange;         /* Link tidak aman */
}

a[href^="mailto:"] {
    color: purple;
    font-style: italic;
}

/* ═══════════════════════════════ */
/* [attr$=value] — Diakhiri dengan (suffix) */
/* ═══════════════════════════════ */
a[href$=".pdf"]::after {
    content: " [PDF]";
    color: red;
    font-size: 0.8em;
}

img[src$=".svg"] {
    background: #f5f5f5;
    padding: 10px;
}

/* ═══════════════════════════════ */
/* [attr*=value] — Mengandung substring di mana saja */
/* ═══════════════════════════════ */
a[href*="example.com"] {
    color: #e74c3c;
}

img[src*="thumbnail"] {
    width: 150px;
    height: 150px;
}

/* ═══════════════════════════════ */
/* Kombinasi attribute selector */
/* ═══════════════════════════════ */
/* Input type=text yang required */
input[type="text"][required] {
    border-left: 4px solid red;
}

/* Link yang dimulai dengan https DAN mengandung blog */
a[href^="https"][href*="blog"] {
    font-weight: bold;
}

/* Case-insensitive (CSS4) — tambahkan i sebelum ] */
[data-type="important" i] {
    color: red;
}
/* Cocok: data-type="important", data-type="Important", data-type="IMPORTANT" */
```

---

## 2.4 Daftar Lengkap Properti CSS

### A. Warna & Background

#### `color` — Warna Teks

```css
/* Nama warna */
p { color: red; }

/* HEX — 6 digit */
p { color: #ff0000; }

/* HEX — 3 digit (shorthand) */
p { color: #f00; }           /* Sama dengan #ff0000 */

/* HEX — 8 digit (termasuk alpha) */
p { color: #ff000080; }      /* Merah 50% transparan */

/* RGB */
p { color: rgb(255, 0, 0); }

/* RGBA (dengan alpha/opacity) */
p { color: rgba(255, 0, 0, 0.5); }

/* HSL (Hue, Saturation, Lightness) */
p { color: hsl(0, 100%, 50%); }

/* HSLA */
p { color: hsla(0, 100%, 50%, 0.5); }

/* CSS4: 8-digit HEX atau fungsi baru */
p { color: #ff0000cc; }
p { color: rgb(255 0 0 / 0.5); }     /* CSS4 dengan spasi */
p { color: hsl(0 100% 50% / 0.5); }  /* CSS4 dengan spasi */

/* Kata kunci sistem */
p { color: currentColor; }    /* Menggunakan nilai color dari induk */
```

**⚠️ AKsesibilitas Kontras Warna:** Pastikan rasio kontras antara teks dan background minimal **4.5:1** untuk teks normal, **3:1** untuk teks besar. Gunakan alat seperti WebAIM Contrast Checker.

#### `background-color` — Warna Latar

```css
.box { background-color: #f0f0f0; }
.box { background-color: rgba(0, 0, 0, 0.1); }
.box { background-color: transparent; }
```

#### `background-image` — Gambar Latar

```css
.element {
    background-image: url('bg.jpg');
    background-image: url('https://example.com/bg.jpg');
    background-image: none;           /* Default — tidak ada gambar */
    background-image: linear-gradient(to right, red, blue);  /* Gradien */
    background-image: radial-gradient(circle, red, blue);    /* Gradien radial */
    background-image: url('overlay.png'), url('bg.jpg');     /* Multiple backgrounds */
}
```

#### `background-repeat`

```css
.element {
    background-repeat: repeat;        /* Default — diulang ke dua arah */
    background-repeat: repeat-x;      /* Diulang horizontal saja */
    background-repeat: repeat-y;      /* Diulang vertikal saja */
    background-repeat: no-repeat;     /* Tidak diulang — sekali saja */
    background-repeat: space;         /* Diulang dengan spasi merata */
    background-repeat: round;         /* Diulang dengan skala agar pas */
}
```

#### `background-position`

```css
.element {
    background-position: center;           /* Tengah */
    background-position: top left;         /* Pojok kiri atas */
    background-position: right bottom;     /* Pojok kanan bawah */
    background-position: 50% 50%;          /* Tengah (persentase) */
    background-position: 20px 100px;       /* 20px dari kiri, 100px dari atas */
    background-position: right 20px bottom 10px;  /* CSS3: dari tepi */
}
```

#### `background-size`

```css
.element {
    background-size: auto;            /* Default — ukuran asli gambar */
    background-size: cover;           /* Memenuhi area (mungkin terpotong) */
    background-size: contain;         /* Seluruh gambar terlihat (mungkin ada ruang kosong) */
    background-size: 100% 100%;       /* Stretch penuh (distorsi mungkin) */
    background-size: 50%;             /* 50% dari lebar kontainer */
    background-size: 200px 100px;     /* Lebar 200px, tinggi 100px */
}
```

**Perbedaan `cover` vs `contain`:**

```
cover:
┌──────────────────────┐
│  ▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒  │   Gambar membungkus penuh
│  ▒▒ GAMBAR ▒▒▒▒▒▒▒  │   Mungkin ada bagian terpotong
│  ▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒  │
└──────────────────────┘

contain:
┌──────────────────────┐
│                      │   Gambar utuh terlihat
│    ┌──────────┐     │   Mungkin ada ruang kosong
│    │  GAMBAR  │     │
│    └──────────┘     │
│                      │
└──────────────────────┘
```

#### `background-attachment`

```css
.element {
    background-attachment: scroll;    /* Default — bergulir dengan konten */
    background-attachment: fixed;     /* Tetap di tempat (parallax effect) */
    background-attachment: local;     /* Bergulir dengan konten elemen (bisa scroll) */
}
```

#### `background-clip` & `background-origin`

```css
.element {
    background-clip: border-box;      /* Default — background sampai tepi border */
    background-clip: padding-box;     /* Background sampai tepi padding */
    background-clip: content-box;     /* Background hanya di area konten */
    background-clip: text;            /* Background di dalam teks (efek teks gradien) */

    background-origin: padding-box;   /* Default — background mulai dari padding */
    background-origin: border-box;    /* Background mulai dari border */
    background-origin: content-box;   /* Background mulai dari konten */
}
```

**Efek teks gradien dengan `background-clip: text`:**

```css
.gradient-text {
    background: linear-gradient(45deg, #f093fb, #f5576c);
    background-clip: text;
    -webkit-background-clip: text;   /* WebKit prefix */
    color: transparent;
}
```

```html
<h1 class="gradient-text">Teks Warna Gradien</h1>
```

#### `background` — Shorthand

```css
.element {
    /* Urutan: color image repeat attachment position / size */
    background: #f0f0f0 url('bg.jpg') no-repeat fixed center / cover;

    /* Multiple backgrounds (dipisah koma) */
    background:
        linear-gradient(45deg, rgba(0,0,0,0.5), transparent),
        url('overlay.png') center/cover,
        #333;
}
```

#### `linear-gradient()` & `radial-gradient()` — Gradien

```css
/* Linear Gradient — arah garis lurus */
.grad-1 { background: linear-gradient(red, blue); }
.grad-2 { background: linear-gradient(to right, red, blue); }
.grad-3 { background: linear-gradient(to bottom right, red, yellow, blue); }
.grad-4 { background: linear-gradient(45deg, #ff0000, #00ff00, #0000ff); }

/* Dengan color stop */
.grad-5 { background: linear-gradient(red 0%, yellow 50%, blue 100%); }
.grad-6 { background: linear-gradient(red 30%, blue 30%); }  /* Hard stop */

/* Radial Gradient — lingkaran/elips */
.grad-7 { background: radial-gradient(red, blue); }
.grad-8 { background: radial-gradient(circle, red, yellow, green); }
.grad-9 { background: radial-gradient(ellipse at top, red, transparent); }

/* Conic Gradient — memutar (CSS4) */
.grad-10 { background: conic-gradient(red, yellow, green, blue, red); }

/* Repeating */
.grad-11 { background: repeating-linear-gradient(45deg, red 0px, red 10px, blue 10px, blue 20px); }
```

---

### B. Tipografi

#### `font-family`

```css
body {
    /* Font utama, lalu fallback, lalu generic family */
    font-family: 'Open Sans', Arial, Helvetica, sans-serif;
}

h1 {
    font-family: 'Georgia', 'Times New Roman', serif;
}

code {
    font-family: 'Fira Code', 'Courier New', Courier, monospace;
}

/* Generic families: */
/* serif — dengan kait (Times New Roman, Georgia) */
/* sans-serif — tanpa kait (Arial, Helvetica) */
/* monospace — lebar tetap (Courier New) */
/* cursive — seperti tulisan tangan (Comic Sans MS) */
/* fantasy — dekoratif (Impact) */
```

#### `font-size`

```css
/* Absolute sizes */
p { font-size: 16px; }           /* Pixel — tetap */
p { font-size: 12pt; }           /* Point — 1pt = 1/72 inch */
p { font-size: 1cm; }            /* Centimeter */

/* Relative sizes */
p { font-size: 1em; }            /* = ukuran font induk (default 16px) */
p { font-size: 1.5em; }          /* 1.5x ukuran font induk */
p { font-size: 1rem; }           /* Root em — relatif ke ukuran font root (<html>) */
p { font-size: 100%; }           /* 100% dari ukuran font induk */
p { font-size: 150%; }           /* 1.5x */

/* Viewport units */
p { font-size: 2vw; }            /* 2% dari lebar viewport */
p { font-size: 2vh; }            /* 2% dari tinggi viewport */
p { font-size: 2vmin; }          /* 2% dari sisi terkecil viewport */
p { font-size: 2vmax; }          /* 2% dari sisi terbesar viewport */

/* Keyword */
p { font-size: small; }
p { font-size: medium; }         /* Default (16px) */
p { font-size: large; }
p { font-size: x-large; }
p { font-size: xx-large; }

/* Clamp (CSS4 — responsif tanpa media query) */
p { font-size: clamp(1rem, 2.5vw, 2rem); }  /* min, preferred, max */
```

**⚠️ Pentingnya `rem` untuk aksesibilitas:**
- `px` mengabaikan pengaturan ukuran font browser user.
- `em` relatif ke induk — bisa menyebabkan masalah kumulatif (nested).
- `rem` relatif ke root — **direkomendasikan** untuk ukuran font karena menghormati pengaturan browser.

```css
html {
    font-size: 100%;  /* Default (16px) — user bisa ubah di pengaturan browser */
}

h1 { font-size: 2rem; }  /* 2 x 16px = 32px */
h2 { font-size: 1.5rem; } /* 1.5 x 16px = 24px */
p  { font-size: 1rem; }  /* = 16px */
small { font-size: 0.875rem; } /* = 14px */
```

#### `font-weight`

```css
p { font-weight: normal; }      /* 400 */
p { font-weight: bold; }        /* 700 */
p { font-weight: lighter; }     /* Lebih tipis dari induk */
p { font-weight: bolder; }      /* Lebih tebal dari induk */
p { font-weight: 100; }        /* Thin */
p { font-weight: 200; }        /* Extra Light */
p { font-weight: 300; }        /* Light */
p { font-weight: 400; }        /* Normal / Regular */
p { font-weight: 500; }        /* Medium */
p { font-weight: 600; }        /* Semi Bold */
p { font-weight: 700; }        /* Bold */
p { font-weight: 800; }        /* Extra Bold */
p { font-weight: 900; }        /* Black / Heavy */
```

**Catatan:** Tidak semua font memiliki semua weight. Biasanya hanya 400 (Regular) dan 700 (Bold) yang tersedia.

#### `font-style`

```css
p { font-style: normal; }     /* Default */
p { font-style: italic; }     /* Miring — font italic khusus */
p { font-style: oblique; }    /* Miring — dipaksakan (jarang digunakan) */
p { font-style: oblique 15deg; } /* CSS4 — sudut kemiringan */
```

#### `text-align`

```css
p { text-align: left; }        /* Rata kiri (default untuk LTR) */
p { text-align: right; }       /* Rata kanan */
p { text-align: center; }      /* Rata tengah */
p { text-align: justify; }     /* Rata kiri-kanan (seperti koran) */

/* CSS3 — parent-directed alignment */
p { text-align: start; }       /* Awal dari arah teks (kiri untuk LTR) */
p { text-align: end; }         /* Akhir dari arah teks (kanan untuk LTR) */
```

#### `text-decoration`

```css
p {
    text-decoration: underline;              /* Garis bawah */
    text-decoration: overline;               /* Garis di atas */
    text-decoration: line-through;           /* Coret tengah */
    text-decoration: none;                   /* Tanpa dekorasi (default) */

    /* CSS3 — shorthand dengan gaya dan warna */
    text-decoration: underline wavy red;     /* Garis bawah merah bergelombang */
    text-decoration: line-through 2px solid blue;

    /* Properti individu (CSS3) */
    text-decoration-line: underline;
    text-decoration-style: wavy;            /* solid, double, dotted, dashed, wavy */
    text-decoration-color: #e74c3c;
    text-decoration-thickness: 3px;          /* Ketebalan garis */
}
```

#### `text-transform`

```css
p { text-transform: none; }         /* Default — tidak berubah */
p { text-transform: capitalize; }   /* Huruf pertama setiap kata kapital */
p { text-transform: uppercase; }    /* SEMUA KAPITAL */
p { text-transform: lowercase; }    /* semua huruf kecil */
p { text-transform: full-width; }   /* Karakter lebar penuh (untuk CJK) */
```

#### `line-height`

```css
p {
    line-height: normal;           /* Default — sekitar 1.2 */
    line-height: 1.5;              /* 1.5x ukuran font — REKOMENDASI untuk readability */
    line-height: 1.6em;            /* 1.6x ukuran font */
    line-height: 24px;             /* Jarak tetap 24px antar baris */
    line-height: 150%;             /* 150% dari ukuran font */
}
```

**⚠️ Best Practice:** Gunakan **unitless** (`line-height: 1.5`) untuk line-height — ini akan diwariskan secara proporsional.

```css
/* ✅ Unitless — proporsional terhadap ukuran font */
body { line-height: 1.5; }

/* ❌ Fixed — tidak proporsional saat font-size berubah */
p { line-height: 24px; }
```

#### `letter-spacing` & `word-spacing`

```css
p {
    letter-spacing: normal;         /* Default */
    letter-spacing: 2px;            /* Jarak antar huruf 2px */
    letter-spacing: 0.05em;         /* 5% dari ukuran font */
    letter-spacing: -1px;           /* Rapat (negatif — hati-hati readability) */

    word-spacing: normal;           /* Default */
    word-spacing: 5px;              /* Jarak antar kata */
    word-spacing: 0.25em;           /* 25% dari ukuran font */
}
```

#### `white-space`

```css
p {
    white-space: normal;            /* Default — wrap otomatis, collapse spasi */
    white-space: nowrap;            /* Tidak wrap — satu baris (overflow) */
    white-space: pre;               /* Seperti <pre> — pertahankan spasi & baris baru */
    white-space: pre-wrap;          /* Pertahankan spasi, tapi wrap jika perlu */
    white-space: pre-line;          /* Collapse spasi, pertahankan baris baru */
    white-space: break-spaces;      /* Seperti pre-wrap, tapi break di spasi */
}
```

#### `word-break` & `overflow-wrap`

```css
p {
    /* word-break — KAPAN pemutusan kata terjadi */
    word-break: normal;             /* Default — putus sesuai aturan bahasa */
    word-break: break-all;          /* Paksa putus di mana saja (karakter) */
    word-break: keep-all;           /* Jangan putus CJK — untuk bahasa Cina/Jepang/Korea */

    /* overflow-wrap — apakah kata panjang boleh diputus */
    overflow-wrap: normal;          /* Default — tidak putus kata panjang */
    overflow-wrap: break-word;      /* Kata panjang diputus jika overflow */
    word-wrap: break-word;          /* Nama lama — alias dari overflow-wrap */
}
```

#### `text-shadow`

```css
p {
    /* offset-x offset-y blur-radius color */
    text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);          /* Bayangan standar */
    text-shadow: 1px 1px 0 #333;                            /* Bayangan tegas (tanpa blur) */
    text-shadow: 0 0 10px rgba(0, 0, 0, 0.5);               /* Glow / neon effect */
    text-shadow: none;                                       /* Default — tanpa bayangan */

    /* Multiple text shadows */
    text-shadow:
        1px 1px 2px black,
        0 0 25px blue,
        0 0 5px darkblue;
}
```

#### `font` — Shorthand

```css
p {
    /* font: font-style font-weight font-size/line-height font-family */
    font: italic bold 16px/1.5 'Arial', sans-serif;
    font: 1.2rem/1.4 'Georgia', serif;          /* Gaya dan weight opsional */
    font: bold 2rem/1.2 'Inter', sans-serif;
}
```

**⚠️ WAJIB:** Saat menggunakan shorthand `font`, properti `font-size` dan `font-family` WAJIB ada. Urutan: `style weight size/line-height family`.

---

### C. Box Model

#### `width` & `height`

```css
.element {
    width: 300px;               /* Lebar tetap */
    width: 50%;                 /* 50% dari lebar kontainer */
    width: auto;                /* Default — sesuai konten */
    width: max-content;         /* Lebar sesuai konten (tidak wrap) */
    width: min-content;         /* Lebar sesuai konten terpendek */
    width: fit-content;         /* Sebesar konten, tapi tidak lebih dari kontainer */
    width: 100vw;               /* 100% dari lebar viewport */

    height: 200px;              /* Tinggi tetap */
    height: 50%;                /* 50% dari tinggi kontainer (jika kontainer memiliki tinggi) */
    height: auto;               /* Default — sesuai konten */
    height: 100vh;              /* 100% dari tinggi viewport */
    height: 100dvh;             /* 100% dari dynamic viewport height (CSS4) */
    height: 100svh;             /* 100% dari small viewport height (CSS4) */
    height: 100lvh;             /* 100% dari large viewport height (CSS4) */
}
```

#### `min-width` / `max-width` / `min-height` / `max-height`

```css
.container {
    max-width: 1200px;          /* Lebar maksimum — tidak lebih dari 1200px */
    min-width: 320px;           /* Lebar minimum — tidak kurang dari 320px */
    width: 100%;                /* 100% sampai 1200px, lalu tetap di 1200px */
}

.element {
    max-height: 400px;          /* Tinggi maksimum — scroll jika lebih */
    min-height: 100px;          /* Tinggi minimum */
    overflow: auto;             /* Scroll jika konten overflow */
}
```

#### `margin` — Ruang Luar

```css
/* Properti individu */
.box {
    margin-top: 10px;
    margin-right: 20px;
    margin-bottom: 10px;
    margin-left: 20px;
}

/* Shorthand — 4 nilai (atas, kanan, bawah, kiri — searah jarum jam) */
.box { margin: 10px 20px 10px 20px; }

/* 3 nilai (atas, kiri-kanan, bawah) */
.box { margin: 10px 20px 15px; }

/* 2 nilai (atas-bawah, kiri-kanan) */
.box { margin: 10px 20px; }

/* 1 nilai — semua sisi sama */
.box { margin: 10px; }

/* Nilai spesial */
.box { margin: 0 auto; }        /* Auto — rata tengah horizontal */
.box { margin: auto; }          /* Semua sisi auto — useful di flex/grid */
.box { margin: 0; }            /* Reset margin */

/* Margin negatif */
.box { margin-left: -10px; }   /* Geser elemen ke kiri */
.box { margin-top: -20px; }    /* Elemen overlap dengan elemen di atasnya */
```

**⚠️ Margin Collapse:** Margin vertikal antar elemen block saling collapse (digabung). Margin terbesar yang menang.

```css
/* Jika dua elemen bersebelahan: */
.box1 { margin-bottom: 30px; }
.box2 { margin-top: 20px; }
/* Jarak antara box1 dan box2 = 30px (bukan 50px) — nilai terbesar menang */
```

#### `padding` — Ruang Dalam

```css
/* Properti individu */
.box {
    padding-top: 10px;
    padding-right: 20px;
    padding-bottom: 10px;
    padding-left: 20px;
}

/* Shorthand — sama dengan margin */
.box { padding: 10px 20px 10px 20px; }  /* Atas, kanan, bawah, kiri */
.box { padding: 10px 20px; }            /* Atas-bawah 10px, kiri-kanan 20px */
.box { padding: 10px; }                 /* Semua sisi 10px */
```

#### `border` — Garis Tepi

```css
/* ═══════════════════════════ */
/* Border-style */
/* ═══════════════════════════ */
.box { border-style: none; }         /* Tanpa border (default) */
.box { border-style: solid; }        /* Garis lurus */
.box { border-style: double; }       /* Garis ganda */
.box { border-style: dotted; }       /* Garis titik-titik */
.box { border-style: dashed; }       /* Garis putus-putus */
.box { border-style: groove; }       /* Efek 3D cekung */
.box { border-style: ridge; }        /* Efek 3D cembung */
.box { border-style: inset; }        /* Efek 3D masuk */
.box { border-style: outset; }       /* Efek 3D keluar */
.box { border-style: solid dotted dashed none; }  /* Per sisi berbeda */

/* ═══════════════════════════ */
/* Border-width */
/* ═══════════════════════════ */
.box { border-width: 1px; }
.box { border-width: 2px 4px; }
.box { border-width: thin; }          /* ≈ 1px */
.box { border-width: medium; }        /* ≈ 3px (default) */
.box { border-width: thick; }         /* ≈ 5px */

/* ═══════════════════════════ */
/* Border-color */
/* ═══════════════════════════ */
.box { border-color: #333; }
.box { border-color: red blue green yellow; }  /* Per sisi */

/* ═══════════════════════════ */
/* Shorthand border */
/* ═══════════════════════════ */
.box { border: 1px solid #333; }      /* width, style, color */
.box { border: 2px dashed red; }
.box { border: none; }                 /* Hapus border */

/* Per sisi */
.box { border-top: 3px solid blue; }
.box { border-right: 2px dotted green; }
.box { border-bottom: 1px solid red; }
.box { border-left: 4px double orange; }

/* Per properti per sisi */
.box {
    border-top-width: 2px;
    border-top-style: solid;
    border-top-color: #3498db;
}
```

#### `border-radius` — Sudut Melengkung

```css
.box {
    border-radius: 8px;              /* Semua sudut 8px */
    border-radius: 10px 20px;        /* Kiri-atas & kanan-bawah: 10px; Kanan-atas & kiri-bawah: 20px */
    border-radius: 10px 20px 30px 40px;  /* Atas-kiri, Atas-kanan, Bawah-kanan, Bawah-kiri */

    /* Lingkaran sempurna */
    border-radius: 50%;              /* Persegi jadi lingkaran */

    /* Border-radius dengan elips */
    border-radius: 10px / 20px;      /* Horizontal 10px, vertikal 20px */
    border-radius: 50% / 20%;        /* Elips */

    /* Per sudut */
    border-top-left-radius: 10px;
    border-top-right-radius: 20px;
    border-bottom-right-radius: 30px;
    border-bottom-left-radius: 40px;
}
```

#### `box-sizing`

```css
/* content-box (DEFAULT) — width/height hanya mencakup konten */
* { box-sizing: content-box; }
/* Lebar total = width + padding + border */

/* border-box — width/height mencakup konten + padding + border */
* { box-sizing: border-box; }
/* Lebar total = width (padding dan border dihitung di dalam) */
```

**Rekomendasi: Terapkan `border-box` ke SEMUA elemen:**
```css
*, *::before, *::after {
    box-sizing: border-box;
}
```

---

### D. Layout

#### `display`

```css
.display-examples {
    display: block;           /* Ditampilkan sebagai blok (baris baru, lebar penuh) */
    display: inline;          /* Dalam baris (selebar konten) */
    display: inline-block;    /* Inline tapi bisa diatur lebar/tinggi */
    display: none;            /* TIDAK DITAMPILKAN (dihilangkan dari layout) */
    display: flex;            /* Flexbox — layout fleksibel 1 dimensi */
    display: inline-flex;     /* Flexbox versi inline */
    display: grid;            /* Grid layout — 2 dimensi */
    display: inline-grid;     /* Grid versi inline */
    display: table;           /* Seperti tabel */
    display: table-cell;      /* Seperti td */
    display: table-row;       /* Seperti tr */
    display: list-item;       /* Seperti li */
    display: contents;        /* Hilangkan box-nya, anak-anaknya langsung ke induk */
    display: flow-root;       /* Membuat BFC (Block Formatting Context) — clearfix modern */
}
```

**Perbedaan `display: none` vs `visibility: hidden`:**
```css
/* Dihapus dari layout — tidak ada ruang */
.hidden { display: none; }

/* Masih di layout — hanya tidak terlihat */
.invisible { visibility: hidden; }
```

#### `position` — Posisi Elemen

```css
/* ═══════════════════════════ */
/* position: static (DEFAULT) */
/* ═══════════════════════════ */
.static {
    position: static;
    /* top, right, bottom, left, z-index TIDAK berfungsi */
}

/* ═══════════════════════════ */
/* position: relative */
/* ═══════════════════════════ */
.relative {
    position: relative;
    top: 10px;              /* Bergeser 10px ke BAWAH dari posisi aslinya */
    left: 20px;             /* Bergeser 20px ke KANAN dari posisi aslinya */
    z-index: 1;             /* Bisa di-z-index */
    /* Elemen tetap di dokumen flow — ruang aslinya masih ditempati */
}

/* ═══════════════════════════ */
/* position: absolute */
/* ═══════════════════════════ */
.absolute {
    position: absolute;
    top: 0;                 /* 0px dari tepi atas parent terdekat yang non-static */
    right: 0;               /* 0px dari tepi kanan */
    /* Elemen DIHAPUS dari dokumen flow — tidak mempengaruhi elemen lain */
    /* Posisi relatif ke parent terdekat yang position != static */
    /* Jika tidak ada, relatif ke <body> */
}

/* ═══════════════════════════ */
/* position: fixed */
/* ═══════════════════════════ */
.fixed {
    position: fixed;
    bottom: 20px;           /* 20px dari bawah viewport */
    right: 20px;            /* 20px dari kanan viewport */
    /* Tetap di posisi yang sama saat halaman di-scroll */
    /* Relatif ke viewport (jendela browser), bukan ke parent */
}

/* ═══════════════════════════ */
/* position: sticky */
/* ═══════════════════════════ */
.sticky {
    position: sticky;
    top: 0;                 /* Menempel di atas saat di-scroll */
    /* Campuran relative dan fixed */
    /* Normal mengikuti flow, tapi saat scroll mencapai threshold, jadi fixed */
}
```

**Visualisasi Position:**

```
┌───────────────────────────────────┐
│  STATIC / RELATIVE                │
│                                   │
│  ┌──────────┐                     │
│  │ ABSOLUTE │ (di dalam relative) │
│  └──────────┘                     │
│                                   │
│  Konten lain...                   │
│                                   │
├───────────────────────────────────┤
│  FIXED — Tetap di sini           │  ← Selalu terlihat
└───────────────────────────────────┘

Sticky — mengikuti scroll, lalu menempel:
┌───────────────────────────────────┐
│  STICKY HEADER (menjadi fixed)   │  ← Menempel di top saat discroll
│                                   │
│  Konten di bawahnya...            │
│                                   │
```

#### `z-index` — Urutan Tumpukan

```css
.element {
    z-index: auto;          /* Default — sesuai urutan di HTML */
    z-index: 0;             /* Lapisan dasar */
    z-index: 1;             /* Di atas lapisan 0 */
    z-index: 9999;          /* Lapisan sangat tinggi */
    z-index: -1;            /* Di belakang lapisan default */
}
```

**⚠️ Aturan `z-index`:**
- Hanya berfungsi pada elemen dengan `position` selain `static` (relative, absolute, fixed, sticky).
- Nilai lebih tinggi = lebih depan (dekat user).
- Jika nilai sama, elemen yang muncul belakangan di HTML yang menang.
- `z-index` relative terhadap **stacking context** — setiap elemen dengan position + z-index menciptakan stacking context baru.

#### `float` & `clear`

```css
/* Float — mengapung ke kiri/kanan */
.float-left {
    float: left;
    margin-right: 10px;
}

.float-right {
    float: right;
    margin-left: 10px;
}

/* Clear — menghentikan float */
.clear-left {
    clear: left;          /* Berhenti mengikuti float left */
}

.clear-right {
    clear: right;         /* Berhenti mengikuti float right */
}

.clear-both {
    clear: both;          /* Berhenti mengikuti kedua arah */
}

/* Clearfix — solusi untuk parent yang collapsed karena float */
.clearfix::after {
    content: "";
    display: table;
    clear: both;
}
```

**Contoh Float Layout (legacy):**

```html
<div class="clearfix">
    <div class="float-left" style="width: 30%;">Sidebar</div>
    <div class="float-right" style="width: 65%;">Konten utama</div>
</div>
```

> **Catatan:** Untuk layout modern, gunakan **Flexbox** atau **Grid** — `float` sekarang digunakan terutama untuk membungkus teks di sekitar gambar.

#### `visibility`

```css
.element {
    visibility: visible;      /* Default — terlihat */
    visibility: hidden;       /* Tidak terlihat, tapi tetap di layout */
    visibility: collapse;     /* Untuk tabel — kolom collapse */
}
```

#### `opacity`

```css
.element {
    opacity: 1;               /* Sepenuhnya terlihat (default) */
    opacity: 0.5;             /* 50% transparan */
    opacity: 0;               /* Sepenuhnya transparan (tidak terlihat) */
    opacity: 0.75;            /* 75% terlihat */
}
```

**⚠️ Perbedaan opacity vs rgba alpha:**
- `opacity: 0.5` → **Seluruh elemen** dan anak-anaknya jadi transparan.
- `background: rgba(0,0,0,0.5)` → Hanya **background** yang transparan, teks tetap jelas.

#### `overflow` — Kontrol Konten Berlebih

```css
.element {
    overflow: visible;        /* Default — konten overflow keluar */
    overflow: hidden;         /* Konten overflow dipotong */
    overflow: scroll;         /* Scrollbar SELALU muncul */
    overflow: auto;           /* Scrollbar hanya jika perlu */
    overflow: clip;           /* Seperti hidden, tapi mencegah scroll programatik */

    /* Per sumbu */
    overflow-x: hidden;       /* Horizontal */
    overflow-y: auto;         /* Vertikal */
}
```

**Visualisasi Overflow:**

```
overflow: hidden          overflow: scroll               overflow: auto
┌──────────────┐        ┌──────────────┐              ┌──────────────┐
│ Teks yang     │        │ Teks yang    │↕             │ Teks yang    │
│ panjang...    │        │ panjang...   │              │ panjang...   │↕
│ (terpotong)   │        │ lanjutan...  │              │ lanjutan...  │
└──────────────┘        └──────────────┘              └──────────────┘
```

#### `cursor`

```css
.element {
    cursor: auto;               /* Default browser */
    cursor: default;            /* Panah default */
    cursor: pointer;            /* Tangan (link, tombol) */
    cursor: text;               /* I-beam (teks bisa dipilih) */
    cursor: wait;               /* Loading / jam pasir */
    cursor: help;               /* Tanda tanya */
    cursor: not-allowed;        /* Lingkaran dengan garis miring */
    cursor: crosshair;          /* Crosshair / tanda + */
    cursor: move;               /* Tanda panah 4 arah */
    cursor: grab;               /* Tangan terbuka */
    cursor: grabbing;           /* Tangan mengepal */
    cursor: zoom-in;            /* Kaca pembesar + */
    cursor: zoom-out;           /* Kaca pembesar - */

    /* Custom cursor */
    cursor: url('cursor.svg'), auto;
    cursor: url('cursor.png') 10 10, auto;  /* hotspot: posisi 10,10 */
}
```

#### `resize`

```css
/* Membuat elemen bisa di-resize oleh user */
.element {
    resize: none;            /* Tidak bisa di-resize (default) */
    resize: both;            /* Bisa di-resize dua arah */
    resize: horizontal;      /* Bisa di-resize horizontal */
    resize: vertical;        /* Bisa di-resize vertikal */
}

/* Biasanya digunakan pada textarea atau div dengan overflow */
textarea {
    resize: vertical;        /* Hanya vertikal — mencegah layout rusak */
}
```

---

### E. Flexbox — Layout 1 Dimensi

**Flexbox** adalah model layout **satu dimensi** (baris ATAU kolom) yang sangat fleksibel untuk mendistribusikan ruang dan menyelaraskan elemen.

#### Container Properties (Parent)

```css
.container {
    /* ═══════════════════════════ */
    /* Membuat flex container */
    /* ═══════════════════════════ */
    display: flex;               /* Block-level flex container */
    display: inline-flex;        /* Inline-level flex container */

    /* ═══════════════════════════ */
    /* flex-direction — ARAH sumbu utama */
    /* ═══════════════════════════ */
    flex-direction: row;               /* Default — kiri ke kanan */
    flex-direction: row-reverse;       /* Kanan ke kiri */
    flex-direction: column;            /* Atas ke bawah */
    flex-direction: column-reverse;    /* Bawah ke atas */

    /* ═══════════════════════════ */
    /* flex-wrap — Apakah item boleh wrap ke baris baru */
    /* ═══════════════════════════ */
    flex-wrap: nowrap;           /* Default — tidak wrap (dipaksa dalam satu baris) */
    flex-wrap: wrap;             /* Wrap ke baris baru jika tidak muat */
    flex-wrap: wrap-reverse;     /* Wrap ke baris baru (dari bawah ke atas) */

    /* ═══════════════════════════ */
    /* flex-flow — Shorthand direction + wrap */
    /* ═══════════════════════════ */
    flex-flow: row nowrap;            /* Default */
    flex-flow: column wrap;           /* Kolom dengan wrapping */
    flex-flow: row-reverse wrap;      /* Baris terbalik dengan wrapping */

    /* ═══════════════════════════ */
    /* justify-content — SEJAJAR dengan sumbu utama (main axis) */
    /* ═══════════════════════════ */
    justify-content: flex-start;      /* Default — di awal */
    justify-content: flex-end;        /* Di akhir */
    justify-content: center;          /* Di tengah */
    justify-content: space-between;   /* Antar item: jarak sama; tepi: rapat */
    justify-content: space-around;    /* Antar item: jarak sama; tepi: setengah jarak */
    justify-content: space-evenly;    /* Semua jarak sama termasuk tepi */

    /* ═══════════════════════════ */
    /* align-items — TEGAK LURUS dengan sumbu utama (cross axis) */
    /* ═══════════════════════════ */
    align-items: stretch;        /* Default — regangkan setinggi container */
    align-items: flex-start;    /* Di awal cross axis */
    align-items: flex-end;      /* Di akhir cross axis */
    align-items: center;        /* Di tengah cross axis */
    align-items: baseline;      /* Sejajar berdasarkan baseline teks */

    /* ═══════════════════════════ */
    /* align-content — HANYA jika ada MULTIPLE BARIS (flex-wrap: wrap) */
    /* ═══════════════════════════ */
    align-content: stretch;         /* Default — regangkan baris */
    align-content: flex-start;     /* Baris di awal */
    align-content: flex-end;       /* Baris di akhir */
    align-content: center;         /* Baris di tengah */
    align-content: space-between;  /* Antar baris: jarak sama */
    align-content: space-around;   /* Antar baris: jarak sama termasuk tepi */
    align-content: space-evenly;   /* Semua jarak sama */

    /* ═══════════════════════════ */
    /* gap — Jarak antar item flex */
    /* ═══════════════════════════ */
    gap: 20px;                    /* Jarak 20px antar baris DAN kolom */
    row-gap: 10px;                /* Jarak antar baris */
    column-gap: 20px;             /* Jarak antar kolom */
    gap: 10px 20px;               /* row-gap: 10px; column-gap: 20px */
}
```

#### Item Properties (Children)

```css
.item {
    /* ═══════════════════════════ */
    /* order — URUTAN item */
    /* ═══════════════════════════ */
    order: 0;                    /* Default — urutan di HTML */
    order: -1;                   /* Pindah ke awal */
    order: 1;                    /* Pindah ke akhir */
    order: 2;                    /* Lebih akhir lagi */

    /* ═══════════════════════════ */
    /* flex-grow — Kemampuan MEMBESAR */
    /* ═══════════════════════════ */
    flex-grow: 0;                /* Default — tidak membesar */
    flex-grow: 1;                /* Bisa membesar (isi ruang kosong) */
    flex-grow: 2;                /* Membesar 2x lebih cepat dari flex-grow:1 */

    /* ═══════════════════════════ */
    /* flex-shrink — Kemampuan MENGECIL */
    /* ═══════════════════════════ */
    flex-shrink: 1;              /* Default — bisa mengecil jika perlu */
    flex-shrink: 0;              /* Tidak bisa mengecil */
    flex-shrink: 2;              /* Mengecil 2x lebih cepat */

    /* ═══════════════════════════ */
    /* flex-basis — UKURAN DASAR sebelum grow/shrink */
    /* ═══════════════════════════ */
    flex-basis: auto;            /* Default — sesuai konten/width */
    flex-basis: 200px;           /* Mulai dari 200px */
    flex-basis: 50%;             /* 50% dari container */
    flex-basis: 0;               /* Mulai dari 0 (ukuran dibagi rata) */

    /* ═══════════════════════════ */
    /* flex — Shorthand */
    /* ═══════════════════════════ */
    flex: 0 1 auto;              /* Default: grow=0, shrink=1, basis=auto */
    flex: 1;                     /* flex: 1 1 0 — item akan membesar secara proporsional */
    flex: 2;                     /* flex: 2 1 0 — lebih besar 2x */
    flex: 0 0 200px;             /* Tidak membesar/mengecil — tetap 200px */
    flex: 1 0 auto;              /* Bisa membesar, tapi tidak mengecil */
    flex: none;                  /* flex: 0 0 auto — ukuran tetap */

    /* ═══════════════════════════ */
    /* align-self — Override align-items untuk item ini */
    /* ═══════════════════════════ */
    align-self: auto;            /* Default — ikuti align-items container */
    align-self: flex-start;
    align-self: flex-end;
    align-self: center;
    align-self: stretch;
    align-self: baseline;
}
```

#### Visualisasi Flexbox

```
flex-direction: row (default)
═══════════════════════════════════════════
                       main axis →
┌─────────────────────────────────────────┐
│  justify-content: center                │
│  ┌────┐──────┌────┐──────┌────┐         │
│  │ 1  │      │ 2  │      │ 3  │         │
│  └────┘      └────┘      └────┘         │
│           align-items: center            │
└─────────────────────────────────────────┘
              ↑ cross axis

justify-content: space-between
┌─────────────────────────────────────────┐
│  ┌────┐              ┌────┐  ┌────┐     │
│  │ 1  │              │ 2  │  │ 3  │     │
│  └────┘              └────┘  └────┘     │
└─────────────────────────────────────────┘

flex-grow: 1 pada setiap item
┌─────────────────────────────────────────┐
│  ┌──────────┐  ┌──────────┐  ┌──────────┐
│  │    1     │  │    2     │  │    3     │
│  └──────────┘  └──────────┘  └──────────┘
└─────────────────────────────────────────┘
```

#### Contoh Layout Flexbox Sederhana

```css
/* ═══════════════════════════ */
/* Contoh: Card layout dengan flex */
/* ═══════════════════════════ */
.card-container {
    display: flex;
    flex-wrap: wrap;
    gap: 20px;
    justify-content: center;
}

.card {
    flex: 1 1 300px;        /* Min 300px, grow jika ada ruang */
    max-width: 400px;
    padding: 20px;
    border: 1px solid #ddd;
    border-radius: 8px;
}

/* ═══════════════════════════ */
/* Contoh: Navbar */
/* ═══════════════════════════ */
.navbar {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 1rem 2rem;
    background: #333;
    color: white;
}

.nav-links {
    display: flex;
    gap: 1rem;
    list-style: none;
}

/* ═══════════════════════════ */
/* Contoh: Centering sempurna (dulu susah!) */
/* ═══════════════════════════ */
.center-container {
    display: flex;
    justify-content: center;
    align-items: center;
    min-height: 100vh;
}

/* ═══════════════════════════ */
/* Contoh: Sticky footer */
/* ═══════════════════════════ */
body {
    display: flex;
    flex-direction: column;
    min-height: 100vh;
}

.content {
    flex: 1;  /* Isi sisa ruang, footer di bawah */
}

.footer {
    /* Footer selalu di bawah */
}
```

---

### F. Grid — Layout 2 Dimensi

**CSS Grid** adalah model layout **dua dimensi** (baris DAN kolom) — jauh lebih kuat dari Flexbox untuk layout halaman secara keseluruhan.

#### Container Properties

```css
.grid-container {
    /* ═══════════════════════════ */
    /* Membuat grid container */
    /* ═══════════════════════════ */
    display: grid;               /* Block-level grid */
    display: inline-grid;        /* Inline-level grid */

    /* ═══════════════════════════ */
    /* grid-template-columns — DEFINISI KOLOM */
    /* ═══════════════════════════ */
    /* 3 kolom dengan lebar tetap */
    grid-template-columns: 200px 300px 200px;

    /* 3 kolom dengan lebar proporsional (fr = fraction) */
    grid-template-columns: 1fr 2fr 1fr;  /* 1:2:1 */

    /* Auto + fixed */
    grid-template-columns: 200px 1fr 200px;  /* Sidebar fixed, konten sisa */

    /* Perataan */
    grid-template-columns: 200px auto 200px;

    /* repeat() function */
    grid-template-columns: repeat(3, 1fr);       /* 3 kolom sama */
    grid-template-columns: repeat(4, 100px);       /* 4 kolom 100px */
    grid-template-columns: repeat(2, 1fr 2fr);     /* 1fr 2fr 1fr 2fr */

    /* minmax() — ukuran minimal dan maksimal */
    grid-template-columns: repeat(3, minmax(200px, 1fr));

    /* auto-fill vs auto-fit */
    grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));   /* Isi dengan kolom */
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));    /* Regangkan jika kosong */

    /* ═══════════════════════════ */
    /* grid-template-rows — DEFINISI BARIS */
    /* ═══════════════════════════ */
    grid-template-rows: 100px auto 100px;      /* Header, konten, footer */

    /* Auto rows */
    grid-auto-rows: 200px;                     /* Baris otomatis = 200px */
    grid-auto-rows: minmax(100px, auto);       /* Minimal 100px, membesar sesuai konten */

    /* ═══════════════════════════ */
    /* grid-template-areas — DEFINISI AREA */
    /* ═══════════════════════════ */
    grid-template-areas:
        "header  header  header"
        "sidebar content content"
        "footer  footer  footer";

    /* ═══════════════════════════ */
    /* gap — Jarak antar grid item */
    /* ═══════════════════════════ */
    gap: 20px;                     /* Jarak antar baris DAN kolom */
    column-gap: 20px;              /* Jarak antar kolom */
    row-gap: 10px;                 /* Jarak antar baris */
    gap: 10px 20px;                /* row-gap: 10px; column-gap: 20px */

    /* ═══════════════════════════ */
    /* justify-items — Perataan HORIZONTAL item dalam cell-nya */
    /* ═══════════════════════════ */
    justify-items: stretch;        /* Default — regangkan selebar cell */
    justify-items: start;          /* Di kiri cell */
    justify-items: end;            /* Di kanan cell */
    justify-items: center;         /* Di tengah cell */

    /* ═══════════════════════════ */
    /* align-items — Perataan VERTIKAL item dalam cell-nya */
    /* ═══════════════════════════ */
    align-items: stretch;          /* Default — regangkan setinggi cell */
    align-items: start;            /* Di atas cell */
    align-items: end;              /* Di bawah cell */
    align-items: center;           /* Di tengah cell */

    /* ═══════════════════════════ */
    /* justify-content — Perataan GRID secara horizontal dalam container */
    /* ═══════════════════════════ */
    justify-content: start;         /* Default */
    justify-content: end;
    justify-content: center;
    justify-content: stretch;
    justify-content: space-between;
    justify-content: space-around;
    justify-content: space-evenly;

    /* ═══════════════════════════ */
    /* align-content — Perataan GRID secara vertikal dalam container */
    /* ═══════════════════════════ */
    align-content: start;
    align-content: end;
    align-content: center;
    align-content: stretch;
    align-content: space-between;
    align-content: space-around;
    align-content: space-evenly;

    /* ═══════════════════════════ */
    /* grid-auto-flow — Arah penempatan item otomatis */
    /* ═══════════════════════════ */
    grid-auto-flow: row;           /* Default — baris (kiri ke kanan, lalu ke bawah) */
    grid-auto-flow: column;        /* Kolom (atas ke bawah, lalu ke kanan) */
    grid-auto-flow: row dense;     /* Isi celah kosong (dense packing) */
    grid-auto-flow: column dense;
}
```

#### Item Properties

```css
.grid-item {
    /* ═══════════════════════════ */
    /* Posisi item secara eksplisit */
    /* ═══════════════════════════ */
    grid-column: 1 / 3;                  /* Mulai kolom 1, sampai 3 (gabung 2 kolom) */
    grid-column: 1 / span 2;             /* Mulai kolom 1, rentang 2 kolom */
    grid-column: 1 / -1;                 /* Dari kolom 1 sampai akhir */
    grid-column: 2;                      /* Hanya di kolom 2 */
    grid-column: 2 / 4;                  /* Kolom 2 sampai 4 */

    grid-row: 1 / 4;                     /* Baris 1 sampai 4 */
    grid-row: 1 / span 3;                /* Baris 1, rentang 3 baris */
    grid-row: 3;                         /* Hanya di baris 3 */

    /* Shorthand */
    grid-area: 1 / 1 / 3 / 3;            /* row-start / col-start / row-end / col-end */
    grid-area: header;                   /* Nama area (dari grid-template-areas) */

    /* ═══════════════════════════ */
    /* Override perataan untuk item ini */
    /* ═══════════════════════════ */
    justify-self: stretch;               /* Regangkan (default dari container) */
    justify-self: start;                 /* Ke kiri cell */
    justify-self: end;                   /* Ke kanan cell */
    justify-self: center;                /* Ke tengah cell */

    align-self: stretch;
    align-self: start;                   /* Ke atas cell */
    align-self: end;                     /* Ke bawah cell */
    align-self: center;                  /* Ke tengah cell */
}
```

#### Visualisasi Grid Layout

```
grid-template-columns: repeat(3, 1fr)
grid-template-rows: 100px auto 100px
grid-template-areas:
    "header  header  header"
    "sidebar content content"
    "footer  footer  footer"

┌────────────────────────────────────┐
│         HEADER          │          │
│  grid-area: header      │          │
├──────────┬──────────────┤          │
│ SIDEBAR  │   CONTENT    │          │
│ grid-area│  grid-area   │          │
│ :sidebar │  :content    │          │
│          │              │          │
│          │              │          │
├──────────┴──────────────┤          │
│         FOOTER          │          │
│  grid-area: footer      │          │
└────────────────────────────────────┘
```

#### Contoh Lengkap Grid Layout

```css
/* Layout halaman lengkap */
.site-layout {
    display: grid;
    grid-template-columns: 250px 1fr 250px;
    grid-template-rows: auto 1fr auto;
    grid-template-areas:
        "header  header  header"
        "sidebar content aside"
        "footer  footer  footer";
    min-height: 100vh;
    gap: 0;
}

.header  { grid-area: header;  background: #2c3e50; color: white; padding: 1rem; }
.sidebar { grid-area: sidebar; background: #f8f9fa; padding: 1rem; }
.content { grid-area: content; padding: 2rem; }
.aside   { grid-area: aside;   background: #f8f9fa; padding: 1rem; }
.footer  { grid-area: footer;  background: #2c3e50; color: white; padding: 1rem; }

/* Responsif — jadi satu kolom di mobile */
@media (max-width: 768px) {
    .site-layout {
        grid-template-columns: 1fr;
        grid-template-areas:
            "header"
            "sidebar"
            "content"
            "aside"
            "footer";
    }
}
```

---

### G. Efek Visual

#### `box-shadow` — Bayangan Kotak

```css
.box {
    /* offset-x | offset-y | color */
    box-shadow: 2px 2px black;

    /* offset-x | offset-y | blur | color */
    box-shadow: 2px 2px 5px rgba(0, 0, 0, 0.3);

    /* offset-x | offset-y | blur | spread | color */
    box-shadow: 2px 2px 5px 2px rgba(0, 0, 0, 0.3);

    /* Inset (bayangan di dalam) */
    box-shadow: inset 0 2px 5px rgba(0, 0, 0, 0.3);

    /* Multiple shadows */
    box-shadow:
        0 2px 5px rgba(0, 0, 0, 0.2),       /* Bayangan dekat */
        0 8px 20px rgba(0, 0, 0, 0.1);       /* Bayangan jauh */

    /* None (default) */
    box-shadow: none;
}
```

**Contoh efek bayangan umum:**

```css
/* Elevation/material design shadow */
.elevation-1 { box-shadow: 0 1px 3px rgba(0,0,0,0.12), 0 1px 2px rgba(0,0,0,0.24); }
.elevation-2 { box-shadow: 0 3px 6px rgba(0,0,0,0.16), 0 3px 6px rgba(0,0,0,0.23); }
.elevation-3 { box-shadow: 0 10px 20px rgba(0,0,0,0.19), 0 6px 6px rgba(0,0,0,0.23); }
.elevation-4 { box-shadow: 0 14px 28px rgba(0,0,0,0.25), 0 10px 10px rgba(0,0,0,0.22); }

/* Glow effect */
.glow { box-shadow: 0 0 15px rgba(52, 152, 219, 0.5); }

/* Border dengan shadow (inset) */
.inset-shadow { box-shadow: inset 0 2px 4px rgba(0,0,0,0.1); }
```

#### `filter` — Efek Filter

```css
.element {
    /* Filter dasar */
    filter: none;                              /* Default — tanpa filter */
    filter: blur(5px);                         /* Blur — keburaman */
    filter: brightness(0.5);                   /* Kecerahan — 0 = hitam, 1 = normal, >1 = lebih terang */
    filter: contrast(200%);                    /* Kontras — 0 = abu-abu, 1 = normal */
    filter: grayscale(100%);                   /* Hitam putih — 0 = normal, 1 = full grayscale */
    filter: hue-rotate(90deg);                 /* Putaran hue — 0-360deg */
    filter: invert(100%);                      /* Balik warna — 0 = normal, 1 = kebalikan */
    filter: opacity(50%);                      /* Opasitas — 0 = transparan, 1 = normal */
    filter: saturate(200%);                    /* Saturasi — 0 = desaturasi, 1 = normal */
    filter: sepia(100%);                       /* Efek sepia — 0 = normal, 1 = full sepia */
    filter: drop-shadow(2px 2px 5px rgba(0,0,0,0.5));  /* Bayangan pada bentuk (bukan box) */

    /* Multiple filters */
    filter: brightness(1.2) contrast(1.1) saturate(1.3);
    filter: grayscale(100%) blur(2px);

    /* URL filter (SVG filter) */
    filter: url(#custom-filter);
}
```

**Perbedaan `box-shadow` vs `filter: drop-shadow`:**

```css
/* box-shadow — bayangan dari BOX */
.box-shadow-example {
    box-shadow: 2px 2px 5px black;
}

/* drop-shadow — bayangan dari BENTUK (termasuk transparansi) */
.drop-shadow-example {
    filter: drop-shadow(2px 2px 5px black);
}
/* Contoh: gambar PNG dengan transparansi — drop-shadow akan mengikuti bentuk gambar, box-shadow mengikuti kotak */
```

#### `mix-blend-mode` & `background-blend-mode`

```css
/* ═══════════════════════════ */
/* mix-blend-mode — Campuran elemen dengan background di bawahnya */
/* ═══════════════════════════ */
.element {
    mix-blend-mode: normal;          /* Default */
    mix-blend-mode: multiply;        /* Efek seperti tinta di kertas */
    mix-blend-mode: screen;          /* Efek seperti slide proyektor */
    mix-blend-mode: overlay;         /* Kombinasi multiply + screen */
    mix-blend-mode: darken;          /* Ambil warna paling gelap */
    mix-blend-mode: lighten;         /* Ambil warna paling terang */
    mix-blend-mode: color-dodge;
    mix-blend-mode: color-burn;
    mix-blend-mode: hard-light;
    mix-blend-mode: soft-light;
    mix-blend-mode: difference;      /* Efek inversi */
    mix-blend-mode: exclusion;
    mix-blend-mode: hue;
    mix-blend-mode: saturation;
    mix-blend-mode: color;
    mix-blend-mode: luminosity;
}

/* ═══════════════════════════ */
/* background-blend-mode — Campuran multiple background layers */
/* ═══════════════════════════ */
.element {
    background: url('overlay.png'), url('bg.jpg');
    background-blend-mode: multiply;    /* Campur kedua background */
}
```

---

### H. Transformasi

#### `transform` — Transformasi 2D & 3D

```css
.element {
    /* ═══════════════════════════ */
    /* TRANSFORM 2D */
    /* ═══════════════════════════ */

    /* Translate — Pindah posisi */
    transform: translateX(50px);            /* Geser horizontal */
    transform: translateY(-20px);           /* Geser vertikal */
    transform: translate(50px, -20px);      /* Geser x dan y */
    transform: translate(50%, 50%);         /* Geser relatif ke ukuran sendiri (pusat) */

    /* Rotate — Putar */
    transform: rotate(45deg);               /* Putar 45° searah jarum jam */
    transform: rotate(-90deg);              /* Putar 90° berlawanan jarum jam */
    transform: rotate(1turn);               /* 1 putaran penuh (360deg) */

    /* Scale — Perbesar/perkecil */
    transform: scaleX(2);                   /* Lebar 2x */
    transform: scaleY(0.5);                 /* Tinggi setengah */
    transform: scale(1.5);                  /* Kedua arah 1.5x */
    transform: scale(2, 0.5);              /* Lebar 2x, tinggi 0.5x */

    /* Skew — Miringkan */
    transform: skewX(10deg);                /* Miring horizontal */
    transform: skewY(20deg);                /* Miring vertikal */
    transform: skew(10deg, 20deg);          /* Miring x dan y */

    /* Matrix — Transformasi gabungan */
    transform: matrix(1, 0.5, 0, 1, 50, 0); /* scaleX, skewY, skewX, scaleY, translateX, translateY */

    /* ═══════════════════════════ */
    /* TRANSFORM 3D */
    /* ═══════════════════════════ */

    /* Rotate 3D */
    transform: rotateX(45deg);              /* Putar sumbu X */
    transform: rotateY(45deg);              /* Putar sumbu Y */
    transform: rotateZ(45deg);              /* Putar sumbu Z (sama dengan rotate) */
    transform: rotate3d(1, 1, 0, 45deg);    /* Rotate pada sumbu diagonal */

    /* Translate 3D */
    transform: translateZ(50px);            /* Mendekat/menjauh */
    transform: translate3d(10px, 20px, 30px);

    /* Scale 3D */
    transform: scaleZ(2);                   /* Perbesar di sumbu Z */
    transform: scale3d(1.5, 1.5, 2);

    /* Perspective */
    transform: perspective(500px) rotateY(45deg);  /* Efek 3D dengan perspektif */

    /* ═══════════════════════════ */
    /* Multiple transforms */
    /* ═══════════════════════════ */
    transform: translate(50px, 20px) rotate(45deg) scale(1.2);
    /* Urutan penting! */
    /* translate dulu, baru rotate, baru scale */
}

/* ═══════════════════════════ */
/* transform-origin — Titik acuan transformasi */
/* ═══════════════════════════ */
.element {
    transform-origin: center;                /* Default — tengah */
    transform-origin: top left;              /* Pojok kiri atas */
    transform-origin: right bottom;          /* Pojok kanan bawah */
    transform-origin: 50% 50%;               /* Sama dengan center */
    transform-origin: 0 0;                   /* Pojok kiri atas dalam px */
    transform-origin: 20px 50px;              /* Koordinat spesifik */
}
```

**⚠️ Transformasi penting:**
- Transformasi TIDAK mempengaruhi layout (seperti `position: relative`).
- Elemen yang di-transform tetap di dokumen flow — hanya visual yang berubah.
- Multiple transform: Urutan **SANGAT PENTING** — `transform: translate() rotate()` ≠ `rotate() translate()`.

**Contoh Praktis:**

```css
/* Hover card dengan transform */
.card {
    transition: transform 0.3s ease;
}

.card:hover {
    transform: translateY(-10px) scale(1.02);
}

/* Tombol dengan efek tekan */
.button:active {
    transform: scale(0.95);
}

/* Animasi loading spinner */
.spinner {
    animation: spin 1s linear infinite;
}

@keyframes spin {
    from { transform: rotate(0deg); }
    to   { transform: rotate(360deg); }
}
```

---

### I. Transisi & Animasi

#### `transition` — Transisi

Transisi membuat perubahan properti menjadi **halus** (animasi dari state A ke state B).

```css
.element {
    /* Properti individu */
    transition-property: all;              /* Default — semua properti */
    transition-property: background-color; /* Hanya background-color */
    transition-property: transform, opacity; /* Beberapa properti */

    transition-duration: 0.3s;            /* Durasi transisi */
    transition-duration: 300ms;           /* Sama dengan 0.3s */
    transition-duration: 2s;              /* 2 detik */

    transition-timing-function: ease;          /* Default — mulai cepat, lambat di akhir */
    transition-timing-function: linear;        /* Kecepatan konstan */
    transition-timing-function: ease-in;       /* Mulai lambat, makin cepat */
    transition-timing-function: ease-out;      /* Mulai cepat, makin lambat */
    transition-timing-function: ease-in-out;   /* Lambat di awal dan akhir */
    transition-timing-function: cubic-bezier(0.25, 0.1, 0.25, 1); /* Kustom */
    transition-timing-function: steps(4, end); /* Animasi bertahap (step) */

    transition-delay: 0s;                  /* Default — tanpa delay */
    transition-delay: 0.1s;               /* Delay 100ms sebelum mulai */
    transition-delay: 2s;                 /* Delay 2 detik */

    /* ═══════════════════════════ */
    /* Shorthand */
    /* ═══════════════════════════ */
    /* property duration timing-function delay */
    transition: all 0.3s ease 0s;
    transition: background-color 0.3s ease;
    transition: transform 0.2s ease-in-out;

    /* Multiple transitions */
    transition:
        background-color 0.3s ease,
        transform 0.2s ease-in-out,
        opacity 0.5s ease 0.1s;
}
```

**⚠️ Properti yang BISA di-transition:**
- Warna: `color`, `background-color`, `border-color`
- Ukuran: `width`, `height`, `padding`, `margin`, `font-size`
- Posisi: `top`, `right`, `bottom`, `left`
- Transform: `transform`, `scale`, `rotate`, `translate`
- Opasitas: `opacity`
- Filter: `filter`, `blur`, `brightness`
- Bayangan: `box-shadow`, `text-shadow`
- Grid: `grid-template-columns`, `gap` (terbatas)

**Contoh Praktis:**

```css
/* ═══════════════════════════ */
/* Tombol dengan hover transisi */
/* ═══════════════════════════ */
.btn {
    background: #3498db;
    color: white;
    padding: 12px 24px;
    border: none;
    border-radius: 4px;
    cursor: pointer;
    transition: all 0.3s ease;
}

.btn:hover {
    background: #2980b9;
    transform: translateY(-2px);
    box-shadow: 0 4px 12px rgba(52, 152, 219, 0.4);
}

.btn:active {
    transform: translateY(0);
}

/* ═══════════════════════════ */
/* Card dengan hover scale */
/* ═══════════════════════════ */
.card {
    width: 300px;
    padding: 20px;
    background: white;
    border-radius: 8px;
    box-shadow: 0 2px 8px rgba(0,0,0,0.1);
    transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.card:hover {
    transform: translateY(-5px) scale(1.02);
    box-shadow: 0 8px 25px rgba(0,0,0,0.15);
}

/* ═══════════════════════════ */
/* Underline animasi pada link */
/* ═══════════════════════════ */
.link-animated {
    position: relative;
    text-decoration: none;
    color: #3498db;
}

.link-animated::after {
    content: '';
    position: absolute;
    bottom: -2px;
    left: 0;
    width: 0;
    height: 2px;
    background: #3498db;
    transition: width 0.3s ease;
}

.link-animated:hover::after {
    width: 100%;
}
```

#### `@keyframes` & `animation` — Animasi

Animasi memungkinkan pergerakan **multi-tahap** (lebih kompleks dari transisi).

```css
/* ═══════════════════════════ */
/* Definisi Keyframes */
/* ═══════════════════════════ */

/* Dua tahap (from-to) */
@keyframes fadeIn {
    from {
        opacity: 0;
        transform: translateY(20px);
    }
    to {
        opacity: 1;
        transform: translateY(0);
    }
}

/* Multi-tahap (persentase) */
@keyframes bounce {
    0% {
        transform: translateY(0);
        animation-timing-function: ease-out;
    }
    50% {
        transform: translateY(-30px);
        animation-timing-function: ease-in;
    }
    100% {
        transform: translateY(0);
        animation-timing-function: ease-in;
    }
}

@keyframes spin {
    0%   { transform: rotate(0deg); }
    25%  { transform: rotate(90deg); }
    50%  { transform: rotate(180deg); }
    75%  { transform: rotate(270deg); }
    100% { transform: rotate(360deg); }
}

/* Animasi dengan warna */
@keyframes colorCycle {
    0%   { background-color: #e74c3c; }
    25%  { background-color: #f39c12; }
    50%  { background-color: #2ecc71; }
    75%  { background-color: #3498db; }
    100% { background-color: #e74c3c; }
}

/* Animasi vibrate/shake */
@keyframes shake {
    0%, 100% { transform: translateX(0); }
    10%, 30%, 50%, 70%, 90% { transform: translateX(-5px); }
    20%, 40%, 60%, 80% { transform: translateX(5px); }
}

/* ═══════════════════════════ */
/* Menerapkan Animasi */
/* ═══════════════════════════ */
.element {
    /* animation-name — nama @keyframes */
    animation-name: fadeIn;

    /* animation-duration — lama animasi */
    animation-duration: 0.5s;
    animation-duration: 2s;

    /* animation-timing-function — kurva kecepatan */
    animation-timing-function: ease;
    animation-timing-function: linear;
    animation-timing-function: cubic-bezier(0.175, 0.885, 0.32, 1.275);  /* Spring effect */

    /* animation-delay — tunda sebelum mulai */
    animation-delay: 0s;
    animation-delay: 0.5s;
    animation-delay: -2s;  /* Mulai di tengah (lompat ke 2 detik) */

    /* animation-iteration-count — berapa kali */
    animation-iteration-count: 1;         /* Default — sekali */
    animation-iteration-count: 3;         /* Tiga kali */
    animation-iteration-count: infinite;  /* Terus menerus */

    /* animation-direction — arah */
    animation-direction: normal;          /* Default — 0% ke 100% */
    animation-direction: reverse;         /* 100% ke 0% */
    animation-direction: alternate;       /* 0% → 100% → 0% → 100% */
    animation-direction: alternate-reverse; /* 100% → 0% → 100% → 0% */

    /* animation-fill-mode — gaya sebelum/sesudah animasi */
    animation-fill-mode: none;     /* Default — kembali ke semula */
    animation-fill-mode: forwards; /* Tetap di state 100% */
    animation-fill-mode: backwards;/* Langsung ke state 0% (meski ada delay) */
    animation-fill-mode: both;     /* forwards + backwards */

    /* animation-play-state — pause/resume */
    animation-play-state: running; /* Default — berjalan */
    animation-play-state: paused;  /* Pause */

    /* ═══════════════════════════ */
    /* Shorthand */
    /* ═══════════════════════════ */
    /* name duration timing-function delay iteration-count direction fill-mode play-state */
    animation: fadeIn 0.5s ease 0s 1 normal both;
    animation: bounce 1s cubic-bezier(0.68, -0.55, 0.265, 1.55) infinite;
    animation: spin 1s linear infinite, fadeIn 0.5s ease;
}

/* ═══════════════════════════ */
/* Pause animasi saat hover */
/* ═══════════════════════════ */
.element:hover {
    animation-play-state: paused;
}
```

**Contoh Animasi Staggered (berurutan):**

```css
/* Setiap item muncul bergantian */
.item:nth-child(1) { animation: fadeIn 0.5s ease 0s both; }
.item:nth-child(2) { animation: fadeIn 0.5s ease 0.1s both; }
.item:nth-child(3) { animation: fadeIn 0.5s ease 0.2s both; }
.item:nth-child(4) { animation: fadeIn 0.5s ease 0.3s both; }
.item:nth-child(5) { animation: fadeIn 0.5s ease 0.4s both; }
```

---

### J. Properti Lainnya

#### `list-style` — Gaya Daftar

```css
ul {
    list-style-type: disc;           /* Default — bullet */
    list-style-type: circle;         /* Bullet lingkaran kosong */
    list-style-type: square;         /* Bullet kotak */
    list-style-type: none;           /* Tanpa bullet */
    list-style-type: decimal;        /* 1, 2, 3, ... */
    list-style-type: lower-alpha;    /* a, b, c, ... */
    list-style-type: upper-roman;    /* I, II, III, ... */

    list-style-position: outside;    /* Default — bullet di luar konten */
    list-style-position: inside;     /* Bullet di dalam konten */

    list-style-image: url('bullet.png'); /* Kustom bullet (gambar) */

    /* Shorthand */
    list-style: none;                /* Paling sering digunakan */
    list-style: square inside;
}
```

#### `vertical-align`

```css
.element {
    vertical-align: baseline;        /* Default — sejajar baseline teks */
    vertical-align: top;             /* Sejajar atas */
    vertical-align: middle;          /* Sejajar tengah */
    vertical-align: bottom;          /* Sejajar bawah */
    vertical-align: sub;             /* Posisi subscript */
    vertical-align: super;           /* Posisi superscript */
    vertical-align: text-top;        /* Sejajar dengan top teks */
    vertical-align: text-bottom;     /* Sejajar dengan bottom teks */
    vertical-align: -5px;            /* Offset dari baseline */
    vertical-align: 50%;             /* 50% dari line-height */
}
```

**⚠️ `vertical-align` HANYA berfungsi pada:**
- Elemen inline (span, img, a)
- Elemen inline-block
- Sel tabel (td, th)

**Tidak berfungsi** untuk elemen block seperti div, p, dll. Untuk memposisikan elemen block, gunakan flexbox atau grid.

#### `outline` — Garis Fokus

```css
.element {
    outline: 2px solid #4A90D9;      /* Lebar, gaya, warna */
    outline: 3px dashed red;
    outline: none;                    /* Hapus outline (HATI-HATI!) */

    outline-width: 2px;
    outline-style: solid;
    outline-color: #4A90D9;

    outline-offset: 2px;              /* Jarak outline dari elemen */
    outline-offset: -2px;             /* Outline di dalam elemen */
}
```

**⚠️ JANGAN hapus outline tanpa pengganti!**
```css
/* ❌ JANGAN lakukan ini — user keyboard kehilangan indikator fokus */
*:focus { outline: none; }

/* ✅ LAKUKAN ini — berikan style fokus alternatif */
*:focus {
    outline: none;
    box-shadow: 0 0 0 3px rgba(74, 144, 217, 0.5);
    /* Atau */
    outline: 2px solid #4A90D9;
    outline-offset: 2px;
}
```

#### `clip-path` — Memotong Bentuk

```css
.element {
    /* Bentuk dasar */
    clip-path: none;                            /* Default — tanpa potongan */
    clip-path: circle(50%);                     /* Lingkaran */
    clip-path: ellipse(50% 25%);                /* Elips */
    clip-path: inset(10px 20px 30px 40px);      /* Persegi panjang di dalam */
    clip-path: polygon(50% 0%, 100% 50%, 50% 100%, 0% 50%);  /* Belah ketupat */
    clip-path: polygon(50% 0%, 0% 100%, 100% 100%);         /* Segitiga */

    /* Dengan margin-box */
    clip-path: margin-box;

    /* SVG clip-path */
    clip-path: url(#myClip);

    /* Animasi clip-path */
    transition: clip-path 0.5s ease;
}

.element:hover {
    clip-path: polygon(0% 0%, 100% 0%, 100% 100%, 0% 100%);  /* Persegi penuh */
}
```

**Contoh kreatif clip-path:**

```css
/* Gambar lingkaran */
.avatar {
    width: 100px;
    height: 100px;
    clip-path: circle(50%);
}

/* Gambar segitiga */
.triangle-image {
    width: 200px;
    height: 200px;
    clip-path: polygon(50% 0%, 0% 100%, 100% 100%);
}

/* Efek reveal */
.reveal {
    clip-path: circle(0% at 50% 50%);
    transition: clip-path 1s ease;
}

.reveal:hover {
    clip-path: circle(75%);
}
```

#### `pointer-events`

```css
.element {
    pointer-events: auto;      /* Default — bisa diklik/interaksi */
    pointer-events: none;      /* Tidak bisa diklik — meneruskan klik ke bawah */
}

/* Contoh: Membuat overlay tidak menghalangi klik */
.overlay {
    pointer-events: none;
}

/* Contoh: Membuat parent tidak bisa diklik, tapi anaknya bisa */
.parent-no-click {
    pointer-events: none;
}

.parent-no-click > * {
    pointer-events: auto;
}
```

#### `user-select`

```css
.element {
    user-select: auto;        /* Default — bisa diseleksi */
    user-select: none;        /* Tidak bisa diseleksi (copy-paste dicegah) */
    user-select: text;        /* Hanya teks yang bisa diseleksi */
    user-select: all;         /* Sekali klik — seleksi semua konten */

    /* Vendor prefix */
    -webkit-user-select: none;
    -moz-user-select: none;
    -ms-user-select: none;
}
```

#### Vendor Prefix

Vendor prefix digunakan untuk properti CSS yang masih **eksperimental** atau **belum standarisasi penuh** di browser tertentu.

| Prefix | Browser |
|--------|---------|
| `-webkit-` | Chrome, Safari, Edge (Chromium), Opera |
| `-moz-` | Firefox |
| `-ms-` | Internet Explorer / Edge Legacy |
| `-o-` | Opera (versi lama — Presto engine) |

```css
/* Contoh penggunaan vendor prefix */

/* Transformasi (dulu butuh prefix) */
.example {
    -webkit-transform: rotate(45deg);
    -moz-transform: rotate(45deg);
    -ms-transform: rotate(45deg);
    -o-transform: rotate(45deg);
    transform: rotate(45deg);  /* Yang standar di paling bawah */
}

/* Animasi */
.example {
    -webkit-animation: fadeIn 0.5s;
    -moz-animation: fadeIn 0.5s;
    -o-animation: fadeIn 0.5s;
    animation: fadeIn 0.5s;  /* Standar */
}

/* Flexbox (versi lama) */
.example {
    display: -webkit-box;     /* Safari lama */
    display: -moz-box;        /* Firefox lama */
    display: -ms-flexbox;     /* IE10 */
    display: -webkit-flex;    /* Safari 6.1+ */
    display: flex;            /* Standar */
}

/* Properti yang masih sering butuh prefix */
.example {
    -webkit-appearance: none;     /* Untuk reset tampilan input */
    -moz-appearance: none;

    -webkit-background-clip: text;  /* Teks gradien */
    -webkit-text-fill-color: transparent;

    -webkit-font-smoothing: antialiased; /* Anti-aliasing font di Mac */

    -webkit-tap-highlight-color: transparent; /* Hapus highlight tap di mobile */
}
```

**Cara praktis: Gunakan Autoprefixer!**
- Alat otomatis (PostCSS plugin) yang menambahkan vendor prefix secara otomatis.
- Diintegrasikan ke build tools (Vite, Webpack, Gulp).
- Atau gunakan VS Code extension.

---

### Media Queries — Responsive Design

Media queries memungkinkan CSS diterapkan **secara kondisional** berdasarkan karakteristik perangkat pengguna.

```css
/* ═══════════════════════════ */
/* Syntax dasar */
/* ═══════════════════════════ */
@media media-type and (media-feature) {
    /* CSS rules */
}

/* ═══════════════════════════ */
/* Media types */
/* ═══════════════════════════ */
@media screen { /* Untuk layar */ }
@media print { /* Untuk cetak */ }
@media speech { /* Untuk screen reader */ }
@media all { /* Semua — default */ }

/* ═══════════════════════════ */
/* Width-based breakpoints */
/* ═══════════════════════════ */
/* Max-width — layar LEBIH KECIL dari */
@media (max-width: 768px) {
    .container { flex-direction: column; }
}

/* Min-width — layar LEBIH BESAR dari */
@media (min-width: 768px) {
    .sidebar { display: block; }
}

/* Range — antara dua ukuran */
@media (min-width: 768px) and (max-width: 1024px) {
    .container { max-width: 90%; }
}

/* ═══════════════════════════ */
/* Responsive breakpoints umum */
/* ═══════════════════════════ */
/* Mobile first (min-width) */
/* 0 - 575px:    Mobile kecil (default styles) */
/* 576px+:       Mobile besar */
/* 768px+:       Tablet */
/* 992px+:       Desktop */
/* 1200px+:      Desktop besar */
/* 1400px+:      Ultra-wide */

/* Contoh mobile-first: */
/* Default (mobile) */
.container {
    padding: 1rem;
}

/* Tablet (≥768px) */
@media (min-width: 768px) {
    .container {
        max-width: 720px;
        margin: 0 auto;
        padding: 2rem;
    }
}

/* Desktop (≥992px) */
@media (min-width: 992px) {
    .container {
        max-width: 960px;
    }
}

/* Desktop besar (≥1200px) */
@media (min-width: 1200px) {
    .container {
        max-width: 1140px;
    }
}

/* ═══════════════════════════ */
/* Fitur media query lainnya */
/* ═══════════════════════════ */
/* Prefers color scheme (dark mode) */
@media (prefers-color-scheme: dark) {
    body {
        background: #1a1a2e;
        color: #e0e0e0;
    }
}

@media (prefers-color-scheme: light) {
    body {
        background: #ffffff;
        color: #333;
    }
}

/* Prefers reduced motion (aksesibilitas) */
@media (prefers-reduced-motion: reduce) {
    *, *::before, *::after {
        animation-duration: 0.01ms !important;
        transition-duration: 0.01ms !important;
    }
}

/* Prefers contrast */
@media (prefers-contrast: high) {
    body {
        color: black;
        background: white;
    }
}

/* Orientation */
@media (orientation: portrait) {
    /* Mode tegak (hp vertikal) */
}

@media (orientation: landscape) {
    /* Mode tidur (hp horizontal) */
}

/* Resolution */
@media (min-resolution: 2dppx) {
    /* Retina / HiDPI displays */
    .logo { background-image: url('logo@2x.png'); }
}

/* Hover capability */
@media (hover: hover) {
    /* Device dengan hover (mouse) */
    .card:hover { transform: scale(1.02); }
}

@media (hover: none) {
    /* Touch device (tanpa hover) */
    .card:active { transform: scale(0.98); }
}

/* Pointer */
@media (pointer: fine) {
    /* Mouse/trackpad presisi */
}

@media (pointer: coarse) {
    /* Jari (touch) */
    .btn { min-height: 48px; } /* Ukuran minimum untuk touch */
}

/* ═══════════════════════════ */
/* Media query dengan not/only */
/* ═══════════════════════════ */
@media not screen and (color) {
    /* Bukan screen atau tidak berwarna */
}

@media only screen and (min-width: 768px) {
    /* Hanya untuk screen, bukan print/speech */
}
```

---

# 🚀 BAGIAN 3: Implementasi Praktis (Proyek Lengkap)

Sekarang kita akan membuat sebuah proyek website **lengkap** yang mengimplementasikan **lebih dari 80%** elemen, atribut, selektor, dan properti yang telah dijelaskan.

## 3.1 Deskripsi Proyek

**Nama Proyek**: Portal Belajar Koding — Website portofolio & blog sederhana untuk seorang developer pemula.

**Fitur**:
- Navigasi responsif dengan hamburger menu di mobile
- Hero section dengan animasi
- Cards portofolio dengan efek hover
- Blog section dengan grid layout
- Form kontak dengan validasi
- Footer dengan informasi lengkap
- Dark mode support
- A11y (aksesibilitas) friendly
- Animasi dan transisi halus

## 3.2 File Proyek

### File 1: `index.html`

```html
<!DOCTYPE html>
<html lang="id" dir="ltr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Portal Belajar Koding - Platform belajar HTML, CSS, dan JavaScript untuk pemula">
    <meta name="keywords" content="belajar coding, HTML, CSS, JavaScript, tutorial, pemula">
    <meta name="author" content="Belajar Koding">
    <meta property="og:title" content="Portal Belajar Koding">
    <meta property="og:description" content="Belajar HTML, CSS, dan JavaScript dari nol hingga mahir">
    <meta property="og:type" content="website">
    <meta name="theme-color" content="#2563eb">

    <title>Portal Belajar Koding — Belajar HTML & CSS</title>

    <!-- Google Fonts -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800&family=JetBrains+Mono:wght@400;700&display=swap" rel="stylesheet">

    <!-- CSS Eksternal -->
    <link rel="stylesheet" href="style.css">

    <!-- Favicon (SVG inline) -->
    <link rel="icon" type="image/svg+xml" href="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 100 100'%3E%3Ctext y='.9em' font-size='90'%3E💻%3C/text%3E%3C/svg%3E">
</head>
<body>

    <!-- ===================================================== -->
    <!-- HEADER & NAVIGASI                                    -->
    <!-- ===================================================== -->
    <header class="site-header" id="top">
        <div class="container">
            <nav class="navbar" aria-label="Navigasi utama">
                <a href="#" class="logo" aria-label="Beranda Portal Belajar Koding">
                    <span class="logo-icon" aria-hidden="true"></></span>
                    <span class="logo-text">Belajar<span class="text-accent">Koding</span></span>
                </a>

                <button class="hamburger" id="hamburger" aria-label="Buka menu navigasi" aria-expanded="false">
                    <span class="hamburger-line"></span>
                    <span class="hamburger-line"></span>
                    <span class="hamburger-line"></span>
                </button>

                <ul class="nav-links" id="navLinks" role="menubar">
                    <li role="none"><a href="#hero" role="menuitem" class="nav-link active">Beranda</a></li>
                    <li role="none"><a href="#tentang" role="menuitem" class="nav-link">Tentang</a></li>
                    <li role="none"><a href="#portofolio" role="menuitem" class="nav-link">Portofolio</a></li>
                    <li role="none"><a href="#blog" role="menuitem" class="nav-link">Blog</a></li>
                    <li role="none"><a href="#kontak" role="menuitem" class="nav-link">Kontak</a></li>
                </ul>
            </nav>
        </div>
    </header>

    <!-- ===================================================== -->
    <!-- HERO SECTION                                        -->
    <!-- ===================================================== -->
    <section class="hero" id="hero">
        <div class="container">
            <div class="hero-content">
                <p class="hero-badge" data-aos="fade-up">🔥 Selamat datang di portal belajar!</p>
                <h1 class="hero-title" data-aos="fade-up" data-aos-delay="100">
                    Belajar <span class="text-gradient">HTML & CSS</span><br>
                    Dari Nol Hingga Mahir
                </h1>
                <p class="hero-description" data-aos="fade-up" data-aos-delay="200">
                    Kuasai dasar-dasar pembuatan website dengan panduan lengkap,
                    contoh kode <mark>interaktif</mark>, dan proyek <strong>nyata</strong>.
                    Cocok untuk pemula <em>tanpa pengalaman</em> coding!
                </p>
                <div class="hero-actions" data-aos="fade-up" data-aos-delay="300">
                    <a href="#mulai" class="btn btn-primary">
                        Mulai Belajar
                        <svg width="20" height="20" viewBox="0 0 20 20" fill="none" aria-hidden="true">
                            <path d="M4.16663 10H15.8333M15.8333 10L10.8333 5M15.8333 10L10.8333 15" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                        </svg>
                    </a>
                    <a href="#portofolio" class="btn btn-outline">
                        Lihat Portofolio
                    </a>
                </div>
            </div>
            <div class="hero-visual" data-aos="fade-left" data-aos-delay="400">
                <figure class="hero-illustration">
                    <svg width="400" height="300" viewBox="0 0 400 300" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
                        <rect x="50" y="50" width="300" height="200" rx="12" fill="var(--color-surface)" stroke="var(--color-border)" stroke-width="2"/>
                        <rect x="70" y="70" width="120" height="30" rx="4" fill="var(--color-primary-light)"/>
                        <rect x="70" y="110" width="260" height="10" rx="2" fill="var(--color-muted)"/>
                        <rect x="70" y="130" width="240" height="10" rx="2" fill="var(--color-muted)"/>
                        <rect x="70" y="150" width="200" height="10" rx="2" fill="var(--color-muted)"/>
                        <rect x="70" y="180" width="80" height="30" rx="6" fill="var(--color-primary)"/>
                        <circle cx="210" cy="85" r="12" fill="var(--color-accent)"/>
                        <circle cx="240" cy="85" r="12" fill="var(--color-secondary)"/>
                    </svg>
                    <figcaption class="sr-only">Ilustrasi kode HTML dan CSS</figcaption>
                </figure>
            </div>
        </div>
    </section>

    <!-- ===================================================== -->
    <!-- TENTANG SECTION                                     -->
    <!-- ===================================================== -->
    <section class="section" id="tentang">
        <div class="container">
            <header class="section-header" data-aos="fade-up">
                <h2 class="section-title">Tentang <span class="text-gradient">Platform Ini</span></h2>
                <p class="section-description">
                    Portal belajar yang dirancang khusus untuk membantu pemula memahami
                    HTML dan CSS secara mendalam dan praktis.
                </p>
            </header>

            <div class="features-grid">
                <article class="feature-card" data-aos="fade-up" data-aos-delay="0">
                    <div class="feature-icon" aria-hidden="true">
                        <svg width="32" height="32" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                            <path d="M12 2L2 7l10 5 10-5-10-5zM2 17l10 5 10-5M2 12l10 5 10-5"/>
                        </svg>
                    </div>
                    <h3 class="feature-title">Struktur Lengkap</h3>
                    <p class="feature-text">Materi disusun secara sistematis dari dasar hingga mahir dengan contoh kode nyata.</p>
                </article>

                <article class="feature-card" data-aos="fade-up" data-aos-delay="100">
                    <div class="feature-icon" aria-hidden="true">
                        <svg width="32" height="32" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                            <rect x="3" y="3" width="18" height="18" rx="2"/><path d="M3 9h18M9 21V9"/>
                        </svg>
                    </div>
                    <h3 class="feature-title">Proyek Praktis</h3>
                    <p class="feature-text">Setiap materi dilengkapi proyek nyata yang bisa Anda <em>bangun sendiri</em>.</p>
                </article>

                <article class="feature-card" data-aos="fade-up" data-aos-delay="200">
                    <div class="feature-icon" aria-hidden="true">
                        <svg width="32" height="32" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                            <path d="M12 22s8-4 8-10V5l-8-3-8 3v7c0 6 8 10 8 10z"/>
                        </svg>
                    </div>
                    <h3 class="feature-title">Gratis & Terbuka</h3>
                    <p class="feature-text">Semua materi <strong>gratis</strong> dan bisa diakses kapan saja, di mana saja.</p>
                </article>

                <article class="feature-card" data-aos="fade-up" data-aos-delay="300">
                    <div class="feature-icon" aria-hidden="true">
                        <svg width="32" height="32" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                            <circle cx="12" cy="12" r="10"/><path d="M12 6v6l4 2"/>
                        </svg>
                    </div>
                    <h3 class="feature-title">Update Berkala</h3>
                    <p class="feature-text">Materi selalu diperbarui dengan <mark>teknologi terbaru</mark> dan best practices.</p>
                </article>
            </div>
        </div>
    </section>

    <!-- ===================================================== -->
    <!-- PORTOFOLIO SECTION                                  -->
    <!-- ===================================================== -->
    <section class="section section-dark" id="portofolio">
        <div class="container">
            <header class="section-header" data-aos="fade-up">
                <h2 class="section-title">Portofolio <span class="text-gradient">Proyek</span></h2>
                <p class="section-description">
                    Beberapa proyek yang telah saya buat menggunakan HTML dan CSS.
                </p>
            </header>

            <div class="portfolio-grid">
                <article class="portfolio-card" data-aos="zoom-in" data-aos-delay="0">
                    <figure class="portfolio-image">
                        <img src="https://placehold.co/600x400/2563eb/ffffff?text=Proyek+1" alt="Tampilan website landing page modern" loading="lazy">
                        <figcaption class="portfolio-overlay">
                            <h3>Landing Page Modern</h3>
                            <p>HTML5, CSS3, Flexbox, Animasi</p>
                        </figcaption>
                    </figure>
                    <div class="portfolio-body">
                        <span class="portfolio-tag">HTML & CSS</span>
                        <h3 class="portfolio-title">Landing Page Modern</h3>
                        <p class="portfolio-text">Landing page responsif dengan animasi dan grid layout.</p>
                        <a href="#" class="portfolio-link" aria-label="Lihat detail Landing Page Modern">
                            Lihat Detail <span aria-hidden="true">→</span>
                        </a>
                    </div>
                </article>

                <article class="portfolio-card" data-aos="zoom-in" data-aos-delay="100">
                    <figure class="portfolio-image">
                        <img src="https://placehold.co/600x400/7c3aed/ffffff?text=Dashboard" alt="Tampilan dashboard admin" loading="lazy">
                        <figcaption class="portfolio-overlay">
                            <h3>Dashboard Admin</h3>
                            <p>CSS Grid, Chart, Dark Mode</p>
                        </figcaption>
                    </figure>
                    <div class="portfolio-body">
                        <span class="portfolio-tag">CSS Grid</span>
                        <h3 class="portfolio-title">Dashboard Admin</h3>
                        <p class="portfolio-text">Dashboard dengan layout grid dan dark mode.</p>
                        <a href="#" class="portfolio-link">Lihat Detail <span aria-hidden="true">→</span></a>
                    </div>
                </article>

                <article class="portfolio-card" data-aos="zoom-in" data-aos-delay="200">
                    <figure class="portfolio-image">
                        <img src="https://placehold.co/600x400/059669/ffffff?text=E-Commerce" alt="Tampilan toko online" loading="lazy">
                        <figcaption class="portfolio-overlay">
                            <h3>Toko Online</h3>
                            <p>Responsive, Card, Filter</p>
                        </figcaption>
                    </figure>
                    <div class="portfolio-body">
                        <span class="portfolio-tag">Responsive</span>
                        <h3 class="portfolio-title">Toko Online</h3>
                        <p class="portfolio-text">Tampilan toko online dengan card produk dan filter.</p>
                        <a href="#" class="portfolio-link">Lihat Detail <span aria-hidden="true">→</span></a>
                    </div>
                </article>
            </div>
        </div>
    </section>

    <!-- ===================================================== -->
    <!-- BLOG SECTION                                        -->
    <!-- ===================================================== -->
    <section class="section" id="blog">
        <div class="container">
            <header class="section-header" data-aos="fade-up">
                <h2 class="section-title">Artikel <span class="text-gradient">Blog</span></h2>
                <p class="section-description">
                    Tips, tutorial, dan panduan seputar HTML, CSS, dan web development.
                </p>
            </header>

            <div class="blog-grid">
                <article class="blog-card" data-aos="fade-up" data-aos-delay="0">
                    <time class="blog-date" datetime="2026-06-01">
                        <span class="blog-day">01</span>
                        <span class="blog-month">Jun 2026</span>
                    </time>
                    <div class="blog-content">
                        <h3 class="blog-title">Cara Memulai Belajar HTML untuk Pemula</h3>
                        <p class="blog-excerpt">Panduan langkah demi langkah untuk memulai perjalanan Anda sebagai web developer.</p>
                        <div class="blog-meta">
                            <span class="blog-author">Oleh: <strong>Admin</strong></span>
                            <span class="blog-read-time">5 menit baca</span>
                        </div>
                        <a href="#" class="blog-read-more">Baca Selengkapnya <span aria-hidden="true">→</span></a>
                    </div>
                </article>

                <article class="blog-card" data-aos="fade-up" data-aos-delay="100">
                    <time class="blog-date" datetime="2026-05-28">
                        <span class="blog-day">28</span>
                        <span class="blog-month">Mei 2026</span>
                    </time>
                    <div class="blog-content">
                        <h3 class="blog-title">CSS Flexbox vs Grid: Kapan Menggunakannya?</h3>
                        <p class="blog-excerpt">Perbandingan lengkap Flexbox dan Grid beserta contoh kasus penggunaannya.</p>
                        <div class="blog-meta">
                            <span class="blog-author">Oleh: <strong>Admin</strong></span>
                            <span class="blog-read-time">8 menit baca</span>
                        </div>
                        <a href="#" class="blog-read-more">Baca Selengkapnya <span aria-hidden="true">→</span></a>
                    </div>
                </article>

                <article class="blog-card" data-aos="fade-up" data-aos-delay="200">
                    <time class="blog-date" datetime="2026-05-20">
                        <span class="blog-day">20</span>
                        <span class="blog-month">Mei 2026</span>
                    </time>
                    <div class="blog-content">
                        <h3 class="blog-title">10 Properti CSS yang Wajib Diketahui Pemula</h3>
                        <p class="blog-excerpt">Kumpulan properti CSS paling penting yang sering digunakan dalam proyek nyata.</p>
                        <div class="blog-meta">
                            <span class="blog-author">Oleh: <strong>Admin</strong></span>
                            <span class="blog-read-time">6 menit baca</span>
                        </div>
                        <a href="#" class="blog-read-more">Baca Selengkapnya <span aria-hidden="true">→</span></a>
                    </div>
                </article>

                <article class="blog-card" data-aos="fade-up" data-aos-delay="300">
                    <time class="blog-date" datetime="2026-05-15">
                        <span class="blog-day">15</span>
                        <span class="blog-month">Mei 2026</span>
                    </time>
                    <div class="blog-content">
                        <h3 class="blog-title">Membuat Form dengan Validasi HTML5</h3>
                        <p class="blog-excerpt">Tutorial lengkap membuat form interaktif dengan validasi native HTML5.</p>
                        <div class="blog-meta">
                            <span class="blog-author">Oleh: <strong>Admin</strong></span>
                            <span class="blog-read-time">10 menit baca</span>
                        </div>
                        <a href="#" class="blog-read-more">Baca Selengkapnya <span aria-hidden="true">→</span></a>
                    </div>
                </article>
            </div>

            <div class="blog-cta" data-aos="fade-up">
                <a href="#" class="btn btn-outline">Lihat Semua Artikel</a>
            </div>
        </div>
    </section>

    <!-- ===================================================== -->
    <!-- KONTAK SECTION                                      -->
    <!-- ===================================================== -->
    <section class="section section-dark" id="kontak">
        <div class="container">
            <header class="section-header" data-aos="fade-up">
                <h2 class="section-title">Hubungi <span class="text-gradient">Kami</span></h2>
                <p class="section-description">
                    Punya pertanyaan, saran, atau ingin berkolaborasi? Silakan isi form di bawah.
                </p>
            </header>

            <div class="contact-wrapper" data-aos="fade-up">
                <form class="contact-form" action="#" method="POST" novalidate>

                    <fieldset class="form-group">
                        <legend class="sr-only">Data diri</legend>

                        <div class="form-field">
                            <label for="nama-lengkap" class="form-label required-field">Nama Lengkap</label>
                            <input type="text" id="nama-lengkap" name="nama" class="form-input"
                                   placeholder="Masukkan nama lengkap" required
                                   minlength="3" maxlength="100"
                                   autocomplete="name"
                                   aria-describedby="nama-hint">
                            <span id="nama-hint" class="form-hint">Minimal 3 karakter</span>
                        </div>

                        <div class="form-field">
                            <label for="email-kontak" class="form-label required-field">Alamat Email</label>
                            <input type="email" id="email-kontak" name="email" class="form-input"
                                   placeholder="contoh@email.com" required
                                   autocomplete="email"
                                   aria-describedby="email-hint">
                            <span id="email-hint" class="form-hint">Kami tidak akan spam email Anda</span>
                        </div>

                        <div class="form-field">
                            <label for="telp" class="form-label">Nomor Telepon <small>(opsional)</small></label>
                            <input type="tel" id="telp" name="telepon" class="form-input"
                                   placeholder="0812-3456-7890"
                                   pattern="[0-9]{10,15}"
                                   autocomplete="tel">
                        </div>
                    </fieldset>

                    <fieldset class="form-group">
                        <legend class="sr-only">Pesan</legend>

                        <div class="form-field">
                            <label for="kategori" class="form-label required-field">Kategori Pesan</label>
                            <select id="kategori" name="kategori" class="form-input" required>
                                <option value="">— Pilih kategori —</option>
                                <option value="pertanyaan">Pertanyaan</option>
                                <option value="saran">Saran & Masukan</option>
                                <option value="kolaborasi">Kolaborasi</option>
                                <option value="lainnya" disabled>Lainnya (sementara nonaktif)</option>
                            </select>
                        </div>

                        <div class="form-field">
                            <label for="urgensi" class="form-label">Tingkat Urgensi</label>
                            <input type="range" id="urgensi" name="urgensi" class="form-range"
                                   min="1" max="5" value="3" step="1"
                                   aria-describedby="urgensi-value">
                            <output id="urgensi-value" class="range-value">3 (Sedang)</output>
                        </div>

                        <div class="form-field">
                            <label for="pesan" class="form-label required-field">Pesan</label>
                            <textarea id="pesan" name="pesan" class="form-input form-textarea"
                                      placeholder="Tulis pesan Anda di sini..."
                                      required minlength="10" maxlength="1000"
                                      rows="5"></textarea>
                            <span class="form-hint">Minimal 10 karakter, maksimal 1000 karakter</span>
                        </div>
                    </fieldset>

                    <fieldset class="form-group">
                        <legend class="sr-only">Lampiran & Persetujuan</legend>

                        <div class="form-field">
                            <label for="lampiran" class="form-label">Lampiran File</label>
                            <input type="file" id="lampiran" name="lampiran" class="form-file"
                                   accept=".pdf,.doc,.docx,.jpg,.png"
                                   multiple>
                            <span class="form-hint">Format: PDF, DOC, JPG, PNG. Maksimal 5MB</span>
                        </div>

                        <div class="form-field checkbox-field">
                            <input type="checkbox" id="setuju" name="setuju" required checked>
                            <label for="setuju" class="checkbox-label">
                                Saya setuju dengan <a href="#" target="_blank" rel="noopener noreferrer">syarat dan ketentuan</a> yang berlaku.
                                <span class="sr-only">(wajib)</span>
                            </label>
                        </div>

                        <div class="form-field radio-group">
                            <p class="form-label">Metode response yang diinginkan:</p>
                            <div class="radio-options">
                                <div class="radio-field">
                                    <input type="radio" id="resp-email" name="response" value="email" checked>
                                    <label for="resp-email">Email</label>
                                </div>
                                <div class="radio-field">
                                    <input type="radio" id="resp-telepon" name="response" value="telepon">
                                    <label for="resp-telepon">Telepon</label>
                                </div>
                                <div class="radio-field">
                                    <input type="radio" id="resp-keduanya" name="response" value="keduanya">
                                    <label for="resp-keduanya">Keduanya</label>
                                </div>
                            </div>
                        </div>
                    </fieldset>

                    <div class="form-actions">
                        <button type="submit" class="btn btn-primary btn-large">
                            <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" aria-hidden="true">
                                <path d="M22 2L11 13M22 2l-7 20-4-9-9-4 20-7z"/>
                            </svg>
                            Kirim Pesan
                        </button>
                        <button type="reset" class="btn btn-ghost">Reset</button>
                    </div>

                    <input type="hidden" name="token" value="csrf-token-123456">
                </form>
            </div>
        </div>
    </section>

    <!-- ===================================================== -->
    <!-- FOOTER                                              -->
    <!-- ===================================================== -->
    <footer class="site-footer" role="contentinfo">
        <div class="container">
            <div class="footer-grid">
                <div class="footer-brand">
                    <a href="#" class="logo" aria-label="Beranda">
                        <span class="logo-icon" aria-hidden="true"></></span>
                        <span class="logo-text">Belajar<span class="text-accent">Koding</span></span>
                    </a>
                    <p class="footer-desc">
                        Platform belajar HTML, CSS, dan JavaScript untuk pemula yang ingin
                        menguasai web development dari nol.
                    </p>
                    <address class="footer-contact">
                        <p>📧 <a href="mailto:admin@belajarkoding.com">admin@belajarkoding.com</a></p>
                        <p>📞 <a href="tel:+6281234567890">+62 812-3456-7890</a></p>
                        <p>📍 Jakarta, Indonesia</p>
                    </address>
                </div>

                <div class="footer-links">
                    <h3>Navigasi</h3>
                    <nav aria-label="Navigasi footer">
                        <ul>
                            <li><a href="#hero">Beranda</a></li>
                            <li><a href="#tentang">Tentang</a></li>
                            <li><a href="#portofolio">Portofolio</a></li>
                            <li><a href="#blog">Blog</a></li>
                            <li><a href="#kontak">Kontak</a></li>
                        </ul>
                    </nav>
                </div>

                <div class="footer-links">
                    <h3>Tutorial</h3>
                    <nav aria-label="Navigasi tutorial">
                        <ul>
                            <li><a href="#">HTML Dasar</a></li>
                            <li><a href="#">HTML Lanjutan</a></li>
                            <li><a href="#">CSS Dasar</a></li>
                            <li><a href="#">CSS Flexbox</a></li>
                            <li><a href="#">CSS Grid</a></li>
                        </ul>
                    </nav>
                </div>

                <div class="footer-newsletter">
                    <h3>Newsletter</h3>
                    <p>Dapatkan update tutorial terbaru langsung ke email Anda.</p>
                    <form class="newsletter-form" action="#" method="POST">
                        <label for="newsletter-email" class="sr-only">Email untuk newsletter</label>
                        <div class="newsletter-input-group">
                            <input type="email" id="newsletter-email" name="email"
                                   placeholder="Email Anda..." required
                                   autocomplete="email">
                            <button type="submit" class="btn btn-primary">Langganan</button>
                        </div>
                    </form>
                </div>
            </div>

            <hr class="footer-divider" aria-hidden="true">

            <div class="footer-bottom">
                <p class="footer-copyright">
                    &copy; 2026 <a href="#">BelajarKoding</a>. 
                    Dibuat dengan <span aria-label="cinta">❤️</span> untuk belajar.
                </p>
                <div class="footer-social">
                    <a href="#" target="_blank" rel="noopener noreferrer" aria-label="Ikuti kami di GitHub">
                        <svg width="24" height="24" viewBox="0 0 24 24" fill="currentColor" aria-hidden="true"><path d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"/></svg>
                    </a>
                    <a href="#" target="_blank" rel="noopener noreferrer" aria-label="Ikuti kami di Twitter">
                        <svg width="24" height="24" viewBox="0 0 24 24" fill="currentColor" aria-hidden="true"><path d="M18.244 2.25h3.308l-7.227 8.26 8.502 11.24H16.17l-5.214-6.817L4.99 21.75H1.68l7.73-8.835L1.254 2.25H8.08l4.713 6.231zm-1.161 17.52h1.833L7.084 4.126H5.117z"/></svg>
                    </a>
                    <a href="#" target="_blank" rel="noopener noreferrer" aria-label="Ikuti kami di LinkedIn">
                        <svg width="24" height="24" viewBox="0 0 24 24" fill="currentColor" aria-hidden="true"><path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433c-1.144 0-2.063-.926-2.063-2.065 0-1.138.92-2.063 2.063-2.063 1.14 0 2.064.925 2.064 2.063 0 1.139-.925 2.065-2.064 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/></svg>
                    </a>
                </div>
            </div>
        </div>
    </footer>

    <!-- ===================================================== -->
    <!-- SCRIPT — JavaScript ringan                           -->
    <!-- ===================================================== -->
    <script>
        // Hamburger menu toggle
        const hamburger = document.getElementById('hamburger');
        const navLinks = document.getElementById('navLinks');

        hamburger.addEventListener('click', () => {
            const isOpen = navLinks.classList.toggle('active');
            hamburger.setAttribute('aria-expanded', isOpen);
            hamburger.setAttribute('aria-label', isOpen ? 'Tutup menu navigasi' : 'Buka menu navigasi');
        });

        // Close menu saat link diklik (mobile)
        document.querySelectorAll('.nav-link').forEach(link => {
            link.addEventListener('click', () => {
                navLinks.classList.remove('active');
                hamburger.setAttribute('aria-expanded', 'false');
                hamburger.setAttribute('aria-label', 'Buka menu navigasi');
            });
        });

        // Update range output
        const rangeInput = document.getElementById('urgensi');
        const rangeOutput = document.getElementById('urgensi-value');

        if (rangeInput && rangeOutput) {
            const labels = {1: '1 (Rendah)', 2: '2', 3: '3 (Sedang)', 4: '4', 5: '5 (Tinggi)'};
            rangeInput.addEventListener('input', () => {
                rangeOutput.textContent = labels[rangeInput.value] || rangeInput.value;
            });
        }

        // Smooth scroll untuk semua anchor link
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function(e) {
                const href = this.getAttribute('href');
                if (href === '#') return;
                e.preventDefault();
                const target = document.querySelector(href);
                if (target) {
                    const headerOffset = 80;
                    const elementPosition = target.getBoundingClientRect().top;
                    const offsetPosition = elementPosition + window.pageYOffset - headerOffset;
                    window.scrollTo({
                        top: offsetPosition,
                        behavior: 'smooth'
                    });
                }
            });
        });
    </script>

</body>
</html>
```

### File 2: `style.css`

```css
/* ════════════════════════════════════════════════════ *
 *  STYLE.CSS — Portal Belajar Koding                  *
 *  Panduan Lengkap HTML & CSS                         *
 *  Mengimplementasikan 80%+ properti & selektor CSS   *
 * ════════════════════════════════════════════════════ */

/* ═══════════════════════════ */
/* VARIABEL CSS (CSS Custom Properties) */
/* ═══════════════════════════ */
:root {
    /* === Warna === */
    --color-primary: #2563eb;
    --color-primary-dark: #1d4ed8;
    --color-primary-light: #dbeafe;
    --color-secondary: #7c3aed;
    --color-accent: #f59e0b;
    --color-accent-light: #fef3c7;

    /* === Warna Teks === */
    --color-text: #1e293b;
    --color-text-light: #64748b;
    --color-text-inverse: #ffffff;

    /* === Warna Latar === */
    --color-bg: #ffffff;
    --color-bg-alt: #f8fafc;
    --color-bg-dark: #0f172a;
    --color-surface: #ffffff;
    --color-surface-alt: #f1f5f9;

    /* === Warna Border === */
    --color-border: #e2e8f0;
    --color-border-light: #f1f5f9;

    /* === Warna Status === */
    --color-success: #10b981;
    --color-error: #ef4444;
    --color-warning: #f59e0b;
    --color-info: #3b82f6;

    /* === Tipografi === */
    --font-sans: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', Arial, sans-serif;
    --font-mono: 'JetBrains Mono', 'Fira Code', 'Courier New', monospace;

    /* === Ukuran Font === */
    --fs-xs: 0.75rem;      /* 12px */
    --fs-sm: 0.875rem;     /* 14px */
    --fs-base: 1rem;       /* 16px */
    --fs-lg: 1.125rem;     /* 18px */
    --fs-xl: 1.25rem;      /* 20px */
    --fs-2xl: 1.5rem;      /* 24px */
    --fs-3xl: 1.875rem;    /* 30px */
    --fs-4xl: 2.25rem;     /* 36px */
    --fs-5xl: 3rem;        /* 48px */
    --fs-6xl: 3.75rem;     /* 60px */

    /* === Spacing === */
    --space-1: 0.25rem;    /* 4px */
    --space-2: 0.5rem;     /* 8px */
    --space-3: 0.75rem;    /* 12px */
    --space-4: 1rem;       /* 16px */
    --space-5: 1.25rem;    /* 20px */
    --space-6: 1.5rem;     /* 24px */
    --space-8: 2rem;       /* 32px */
    --space-10: 2.5rem;    /* 40px */
    --space-12: 3rem;      /* 48px */
    --space-16: 4rem;      /* 64px */
    --space-20: 5rem;      /* 80px */

    /* === Border Radius === */
    --radius-sm: 0.25rem;  /* 4px */
    --radius-md: 0.5rem;   /* 8px */
    --radius-lg: 0.75rem;  /* 12px */
    --radius-xl: 1rem;     /* 16px */
    --radius-full: 9999px;

    /* === Shadow === */
    --shadow-sm: 0 1px 2px 0 rgba(0, 0, 0, 0.05);
    --shadow-md: 0 4px 6px -1px rgba(0, 0, 0, 0.1), 0 2px 4px -2px rgba(0, 0, 0, 0.1);
    --shadow-lg: 0 10px 15px -3px rgba(0, 0, 0, 0.1), 0 4px 6px -4px rgba(0, 0, 0, 0.1);
    --shadow-xl: 0 20px 25px -5px rgba(0, 0, 0, 0.1), 0 8px 10px -6px rgba(0, 0, 0, 0.1);

    /* === Transisi === */
    --transition-fast: 150ms ease;
    --transition-base: 300ms ease;
    --transition-slow: 500ms ease;

    /* === Layout === */
    --container-max: 1200px;
    --header-height: 72px;
}

/* ═══════════════════════════ */
/* DARK MODE — prefers-color-scheme */
/* ═══════════════════════════ */
@media (prefers-color-scheme: dark) {
    :root {
        --color-primary: #3b82f6;
        --color-primary-dark: #2563eb;
        --color-primary-light: #1e3a5f;
        --color-text: #e2e8f0;
        --color-text-light: #94a3b8;
        --color-text-inverse: #0f172a;
        --color-bg: #0f172a;
        --color-bg-alt: #1e293b;
        --color-bg-dark: #020617;
        --color-surface: #1e293b;
        --color-surface-alt: #334155;
        --color-border: #334155;
        --color-border-light: #1e293b;

        --shadow-sm: 0 1px 2px 0 rgba(0, 0, 0, 0.3);
        --shadow-md: 0 4px 6px -1px rgba(0, 0, 0, 0.4);
        --shadow-lg: 0 10px 15px -3px rgba(0, 0, 0, 0.4);
        --shadow-xl: 0 20px 25px -5px rgba(0, 0, 0, 0.5);
    }
}

/* ═══════════════════════════ */
/* PREFERS REDUCED MOTION — Aksesibilitas */
/* ═══════════════════════════ */
@media (prefers-reduced-motion: reduce) {
    *, *::before, *::after {
        animation-duration: 0.01ms !important;
        animation-iteration-count: 1 !important;
        transition-duration: 0.01ms !important;
        scroll-behavior: auto !important;
    }
}

/* ═══════════════════════════ */
/* RESET & GLOBAL STYLES */
/* ═══════════════════════════ */
*, *::before, *::after {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
}

html {
    scroll-behavior: smooth;
    -webkit-text-size-adjust: 100%;
    -moz-text-size-adjust: 100%;
    text-size-adjust: 100%;
}

body {
    font-family: var(--font-sans);
    font-size: var(--fs-base);
    line-height: 1.6;
    color: var(--color-text);
    background-color: var(--color-bg);
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    min-height: 100vh;
    display: flex;
    flex-direction: column;
}

main {
    flex: 1;
}

img {
    max-width: 100%;
    height: auto;
    display: block;
}

a {
    color: var(--color-primary);
    text-decoration: none;
    transition: color var(--transition-fast);
}

a:hover {
    color: var(--color-primary-dark);
}

/* ═══════════════════════════ */
/* UTILITY CLASSES */
/* ═══════════════════════════ */

/* Screen reader only */
.sr-only {
    position: absolute;
    width: 1px;
    height: 1px;
    padding: 0;
    margin: -1px;
    overflow: hidden;
    clip: rect(0, 0, 0, 0);
    white-space: nowrap;
    border: 0;
}

/* Text gradient */
.text-gradient {
    background: linear-gradient(135deg, var(--color-primary), var(--color-secondary));
    background-clip: text;
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    color: transparent;
}

.text-accent {
    color: var(--color-accent);
}

/* ═══════════════════════════ */
/* CONTAINER */
/* ═══════════════════════════ */
.container {
    width: 100%;
    max-width: var(--container-max);
    margin: 0 auto;
    padding: 0 var(--space-6);
}

/* ═══════════════════════════ */
/* TYPOGRAPHY */
/* ═══════════════════════════ */
h1, h2, h3, h4, h5, h6 {
    font-weight: 700;
    line-height: 1.2;
    color: var(--color-text);
}

h1 { font-size: var(--fs-4xl); }
h2 { font-size: var(--fs-3xl); }
h3 { font-size: var(--fs-2xl); }
h4 { font-size: var(--fs-xl); }

p {
    margin-bottom: var(--space-4);
}

p:last-child {
    margin-bottom: 0;
}

mark {
    background-color: var(--color-accent-light);
    padding: 0.1em 0.2em;
    border-radius: var(--radius-sm);
    color: var(--color-text);
}

strong {
    font-weight: 600;
}

small {
    font-size: var(--fs-sm);
    color: var(--color-text-light);
}

/* ═══════════════════════════ */
/* HEADER / NAVIGATION */
/* ═══════════════════════════ */
.site-header {
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    z-index: 1000;
    background: var(--color-bg);
    border-bottom: 1px solid var(--color-border);
    height: var(--header-height);
    backdrop-filter: blur(12px);
    -webkit-backdrop-filter: blur(12px);
    background: rgba(255, 255, 255, 0.9);
}

@media (prefers-color-scheme: dark) {
    .site-header {
        background: rgba(15, 23, 42, 0.9);
    }
}

.navbar {
    display: flex;
    justify-content: space-between;
    align-items: center;
    height: var(--header-height);
}

/* Logo */
.logo {
    display: flex;
    align-items: center;
    gap: var(--space-2);
    font-weight: 800;
    font-size: var(--fs-xl);
    color: var(--color-text);
    text-decoration: none;
}

.logo:hover {
    color: var(--color-text);
}

.logo-icon {
    width: 40px;
    height: 40px;
    display: flex;
    align-items: center;
    justify-content: center;
    background: var(--color-primary);
    color: white;
    border-radius: var(--radius-md);
    font-family: var(--font-mono);
    font-weight: 700;
    font-size: var(--fs-sm);
}

/* Navigation Links */
.nav-links {
    display: flex;
    list-style: none;
    gap: var(--space-1);
}

.nav-link {
    display: block;
    padding: var(--space-2) var(--space-4);
    color: var(--color-text-light);
    font-weight: 500;
    font-size: var(--fs-sm);
    border-radius: var(--radius-md);
    transition: all var(--transition-fast);
    position: relative;
}

.nav-link:hover,
.nav-link.active {
    color: var(--color-primary);
    background: var(--color-primary-light);
}

/* Hamburger Menu */
.hamburger {
    display: none;
    flex-direction: column;
    gap: 5px;
    background: none;
    border: none;
    cursor: pointer;
    padding: var(--space-2);
    border-radius: var(--radius-md);
    transition: background var(--transition-fast);
}

.hamburger:hover {
    background: var(--color-surface-alt);
}

.hamburger-line {
    display: block;
    width: 24px;
    height: 2px;
    background: var(--color-text);
    border-radius: 2px;
    transition: all var(--transition-base);
    transform-origin: center;
}

/* Hamburger animation */
.hamburger[aria-expanded="true"] .hamburger-line:nth-child(1) {
    transform: rotate(45deg) translate(5px, 5px);
}

.hamburger[aria-expanded="true"] .hamburger-line:nth-child(2) {
    opacity: 0;
    transform: scaleX(0);
}

.hamburger[aria-expanded="true"] .hamburger-line:nth-child(3) {
    transform: rotate(-45deg) translate(5px, -5px);
}

/* ═══════════════════════════ */
/* HERO SECTION */
/* ═══════════════════════════ */
.hero {
    padding: calc(var(--header-height) + var(--space-16)) 0 var(--space-16);
    background: linear-gradient(180deg, var(--color-bg) 0%, var(--color-bg-alt) 100%);
    overflow: hidden;
}

.hero .container {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: var(--space-12);
    align-items: center;
}

.hero-content {
    display: flex;
    flex-direction: column;
    gap: var(--space-6);
}

.hero-badge {
    display: inline-flex;
    align-items: center;
    gap: var(--space-2);
    background: var(--color-primary-light);
    color: var(--color-primary);
    padding: var(--space-2) var(--space-4);
    border-radius: var(--radius-full);
    font-size: var(--fs-sm);
    font-weight: 600;
    width: fit-content;
}

.hero-title {
    font-size: clamp(2rem, 5vw, var(--fs-6xl));
    font-weight: 800;
    line-height: 1.1;
    letter-spacing: -0.02em;
}

.hero-description {
    font-size: var(--fs-lg);
    color: var(--color-text-light);
    max-width: 540px;
}

.hero-actions {
    display: flex;
    gap: var(--space-4);
    flex-wrap: wrap;
}

.hero-visual {
    display: flex;
    justify-content: center;
    align-items: center;
}

.hero-illustration {
    width: 100%;
    max-width: 400px;
}

.hero-illustration svg {
    width: 100%;
    height: auto;
}

/* ═══════════════════════════ */
/* BUTTONS */
/* ═══════════════════════════ */
.btn {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    gap: var(--space-2);
    padding: var(--space-3) var(--space-6);
    font-family: var(--font-sans);
    font-weight: 600;
    font-size: var(--fs-sm);
    border: 2px solid transparent;
    border-radius: var(--radius-md);
    cursor: pointer;
    transition: all var(--transition-base);
    text-decoration: none;
    line-height: 1.4;
}

.btn:focus-visible {
    outline: 2px solid var(--color-primary);
    outline-offset: 2px;
}

.btn-primary {
    background: var(--color-primary);
    color: white;
    border-color: var(--color-primary);
}

.btn-primary:hover {
    background: var(--color-primary-dark);
    border-color: var(--color-primary-dark);
    color: white;
    transform: translateY(-1px);
    box-shadow: var(--shadow-md);
}

.btn-primary:active {
    transform: translateY(0);
}

.btn-outline {
    background: transparent;
    color: var(--color-primary);
    border-color: var(--color-primary);
}

.btn-outline:hover {
    background: var(--color-primary);
    color: white;
    transform: translateY(-1px);
}

.btn-ghost {
    background: transparent;
    color: var(--color-text-light);
    border-color: transparent;
    padding: var(--space-3) var(--space-4);
}

.btn-ghost:hover {
    background: var(--color-surface-alt);
    color: var(--color-text);
}

.btn-large {
    padding: var(--space-4) var(--space-8);
    font-size: var(--fs-base);
}

/* ═══════════════════════════ */
/* SECTION COMMON STYLES */
/* ═══════════════════════════ */
.section {
    padding: var(--space-20) 0;
}

.section-dark {
    background: var(--color-bg-alt);
}

.section-header {
    text-align: center;
    max-width: 640px;
    margin: 0 auto var(--space-12);
}

.section-title {
    font-size: var(--fs-4xl);
    font-weight: 800;
    margin-bottom: var(--space-4);
    letter-spacing: -0.02em;
}

.section-description {
    font-size: var(--fs-lg);
    color: var(--color-text-light);
}

/* ═══════════════════════════ */
/* FEATURES GRID (TENTANG) */
/* ═══════════════════════════ */
.features-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: var(--space-6);
}

.feature-card {
    background: var(--color-surface);
    border: 1px solid var(--color-border);
    border-radius: var(--radius-lg);
    padding: var(--space-8);
    transition: all var(--transition-base);
}

.feature-card:hover {
    transform: translateY(-4px);
    box-shadow: var(--shadow-lg);
    border-color: var(--color-primary);
}

.feature-icon {
    width: 56px;
    height: 56px;
    display: flex;
    align-items: center;
    justify-content: center;
    background: var(--color-primary-light);
    color: var(--color-primary);
    border-radius: var(--radius-md);
    margin-bottom: var(--space-6);
}

.feature-title {
    font-size: var(--fs-xl);
    margin-bottom: var(--space-3);
}

.feature-text {
    color: var(--color-text-light);
    font-size: var(--fs-sm);
}

/* ═══════════════════════════ */
/* PORTFOLIO GRID */
/* ═══════════════════════════ */
.portfolio-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: var(--space-6);
}

.portfolio-card {
    background: var(--color-surface);
    border: 1px solid var(--color-border);
    border-radius: var(--radius-lg);
    overflow: hidden;
    transition: all var(--transition-base);
}

.portfolio-card:hover {
    transform: translateY(-6px);
    box-shadow: var(--shadow-xl);
}

.portfolio-image {
    position: relative;
    overflow: hidden;
    aspect-ratio: 3/2;
    margin: 0;
}

.portfolio-image img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    transition: transform var(--transition-slow);
}

.portfolio-card:hover .portfolio-image img {
    transform: scale(1.08);
}

.portfolio-overlay {
    position: absolute;
    inset: 0;
    background: linear-gradient(180deg, transparent 40%, rgba(0, 0, 0, 0.85));
    display: flex;
    flex-direction: column;
    justify-content: flex-end;
    padding: var(--space-6);
    color: white;
    opacity: 0;
    transition: opacity var(--transition-base);
}

.portfolio-card:hover .portfolio-overlay {
    opacity: 1;
}

.portfolio-overlay h3 {
    color: white;
    font-size: var(--fs-lg);
}

.portfolio-overlay p {
    font-size: var(--fs-sm);
    opacity: 0.8;
}

.portfolio-body {
    padding: var(--space-6);
}

.portfolio-tag {
    display: inline-block;
    background: var(--color-primary-light);
    color: var(--color-primary);
    font-size: var(--fs-xs);
    font-weight: 600;
    padding: var(--space-1) var(--space-3);
    border-radius: var(--radius-full);
    margin-bottom: var(--space-3);
}

.portfolio-title {
    font-size: var(--fs-xl);
    margin-bottom: var(--space-2);
}

.portfolio-text {
    font-size: var(--fs-sm);
    color: var(--color-text-light);
    margin-bottom: var(--space-4);
}

.portfolio-link {
    font-weight: 600;
    font-size: var(--fs-sm);
    display: inline-flex;
    align-items: center;
    gap: var(--space-1);
}

.portfolio-link:hover {
    gap: var(--space-2);
}

/* ═══════════════════════════ */
/* BLOG GRID */
/* ═══════════════════════════ */
.blog-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
    gap: var(--space-6);
}

.blog-card {
    display: flex;
    gap: var(--space-6);
    background: var(--color-surface);
    border: 1px solid var(--color-border);
    border-radius: var(--radius-lg);
    padding: var(--space-6);
    transition: all var(--transition-base);
}

.blog-card:hover {
    border-color: var(--color-primary);
    box-shadow: var(--shadow-md);
    transform: translateY(-2px);
}

.blog-date {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    min-width: 64px;
    height: 64px;
    background: var(--color-primary-light);
    border-radius: var(--radius-md);
    color: var(--color-primary);
    font-weight: 700;
    flex-shrink: 0;
}

.blog-day {
    font-size: var(--fs-2xl);
    line-height: 1;
}

.blog-month {
    font-size: var(--fs-xs);
    text-transform: uppercase;
    letter-spacing: 0.05em;
}

.blog-content {
    flex: 1;
}

.blog-title {
    font-size: var(--fs-lg);
    margin-bottom: var(--space-2);
    line-height: 1.3;
}

.blog-excerpt {
    font-size: var(--fs-sm);
    color: var(--color-text-light);
    margin-bottom: var(--space-4);
}

.blog-meta {
    display: flex;
    gap: var(--space-4);
    font-size: var(--fs-xs);
    color: var(--color-text-light);
    margin-bottom: var(--space-3);
}

.blog-read-more {
    font-size: var(--fs-sm);
    font-weight: 600;
    display: inline-flex;
    align-items: center;
    gap: var(--space-1);
}

.blog-read-more:hover {
    gap: var(--space-2);
}

.blog-cta {
    text-align: center;
    margin-top: var(--space-12);
}

/* ═══════════════════════════ */
/* CONTACT FORM */
/* ═══════════════════════════ */
.contact-wrapper {
    max-width: 640px;
    margin: 0 auto;
}

.contact-form {
    display: flex;
    flex-direction: column;
    gap: var(--space-8);
}

.form-group {
    border: none;
    padding: 0;
    margin: 0;
}

.form-field {
    margin-bottom: var(--space-5);
}

.form-label {
    display: block;
    font-weight: 600;
    font-size: var(--fs-sm);
    margin-bottom: var(--space-2);
    color: var(--color-text);
}

/* Required field indicator */
.required-field::after {
    content: " *";
    color: var(--color-error);
}

.form-input {
    width: 100%;
    padding: var(--space-3) var(--space-4);
    font-family: var(--font-sans);
    font-size: var(--fs-base);
    color: var(--color-text);
    background: var(--color-surface);
    border: 1px solid var(--color-border);
    border-radius: var(--radius-md);
    transition: all var(--transition-fast);
    outline: none;
}

.form-input::placeholder {
    color: var(--color-text-light);
    opacity: 0.7;
}

.form-input:focus {
    border-color: var(--color-primary);
    box-shadow: 0 0 0 3px rgba(37, 99, 235, 0.15);
}

.form-input:user-invalid {
    border-color: var(--color-error);
    box-shadow: 0 0 0 3px rgba(239, 68, 68, 0.15);
}

.form-input:user-valid {
    border-color: var(--color-success);
}

.form-textarea {
    resize: vertical;
    min-height: 120px;
}

.form-hint {
    display: block;
    font-size: var(--fs-xs);
    color: var(--color-text-light);
    margin-top: var(--space-1);
}

/* Range input styling */
.form-range {
    width: 100%;
    height: 6px;
    background: var(--color-border);
    border-radius: var(--radius-full);
    outline: none;
    -webkit-appearance: none;
    -moz-appearance: none;
    appearance: none;
    cursor: pointer;
}

.form-range::-webkit-slider-thumb {
    -webkit-appearance: none;
    appearance: none;
    width: 20px;
    height: 20px;
    border-radius: 50%;
    background: var(--color-primary);
    cursor: pointer;
    transition: transform var(--transition-fast);
}

.form-range::-webkit-slider-thumb:hover {
    transform: scale(1.2);
}

.form-range::-moz-range-thumb {
    width: 20px;
    height: 20px;
    border-radius: 50%;
    background: var(--color-primary);
    cursor: pointer;
    border: none;
}

.range-value {
    display: inline-block;
    font-size: var(--fs-sm);
    color: var(--color-text-light);
    margin-top: var(--space-1);
}

/* Checkbox */
.checkbox-field {
    display: flex;
    align-items: flex-start;
    gap: var(--space-3);
}

.checkbox-field input[type="checkbox"] {
    width: 18px;
    height: 18px;
    margin-top: 3px;
    accent-color: var(--color-primary);
    cursor: pointer;
    flex-shrink: 0;
}

.checkbox-label {
    font-size: var(--fs-sm);
    cursor: pointer;
    user-select: none;
}

.checkbox-label a {
    text-decoration: underline;
}

/* Radio buttons */
.radio-group {
    padding: var(--space-4);
    background: var(--color-bg-alt);
    border-radius: var(--radius-md);
}

.radio-options {
    display: flex;
    gap: var(--space-6);
    flex-wrap: wrap;
}

.radio-field {
    display: flex;
    align-items: center;
    gap: var(--space-2);
}

.radio-field input[type="radio"] {
    accent-color: var(--color-primary);
    width: 18px;
    height: 18px;
    cursor: pointer;
}

.radio-field label {
    font-size: var(--fs-sm);
    cursor: pointer;
    user-select: none;
}

/* File input */
.form-file::file-selector-button {
    padding: var(--space-2) var(--space-4);
    background: var(--color-surface-alt);
    border: 1px solid var(--color-border);
    border-radius: var(--radius-md);
    font-family: var(--font-sans);
    font-weight: 500;
    font-size: var(--fs-sm);
    color: var(--color-text);
    cursor: pointer;
    transition: all var(--transition-fast);
    margin-right: var(--space-3);
}

.form-file::file-selector-button:hover {
    background: var(--color-border);
}

/* Form actions */
.form-actions {
    display: flex;
    gap: var(--space-4);
    align-items: center;
    padding-top: var(--space-4);
    border-top: 1px solid var(--color-border);
}

/* Select styling */
select.form-input {
    -webkit-appearance: none;
    -moz-appearance: none;
    appearance: none;
    background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='12' height='12' viewBox='0 0 24 24' fill='none' stroke='%2364748b' stroke-width='2' stroke-linecap='round' stroke-linejoin='round'%3E%3Cpolyline points='6 9 12 15 18 9'%3E%3C/polyline%3E%3C/svg%3E");
    background-repeat: no-repeat;
    background-position: right 12px center;
    padding-right: 40px;
}

/* ═══════════════════════════ */
/* FOOTER */
/* ═══════════════════════════ */
.site-footer {
    background: var(--color-bg-dark);
    color: var(--color-text);
    padding: var(--space-16) 0 var(--space-8);
}

.site-footer .logo {
    color: white;
}

.site-footer .logo-icon {
    background: var(--color-accent);
    color: #0f172a;
}

.footer-grid {
    display: grid;
    grid-template-columns: 2fr 1fr 1fr 1.5fr;
    gap: var(--space-8);
}

.footer-desc {
    color: #94a3b8;
    font-size: var(--fs-sm);
    margin-top: var(--space-4);
    line-height: 1.7;
}

.footer-contact {
    font-style: normal;
    font-size: var(--fs-sm);
    color: #94a3b8;
    margin-top: var(--space-4);
}

.footer-contact a {
    color: #94a3b8;
}

.footer-contact a:hover {
    color: white;
}

.footer-links h3 {
    color: white;
    font-size: var(--fs-sm);
    font-weight: 700;
    text-transform: uppercase;
    letter-spacing: 0.05em;
    margin-bottom: var(--space-6);
}

.footer-links ul {
    list-style: none;
    display: flex;
    flex-direction: column;
    gap: var(--space-3);
}

.footer-links a {
    color: #94a3b8;
    font-size: var(--fs-sm);
    transition: color var(--transition-fast);
}

.footer-links a:hover {
    color: white;
    padding-left: var(--space-1);
}

/* Newsletter */
.footer-newsletter h3 {
    color: white;
    font-size: var(--fs-sm);
    font-weight: 700;
    text-transform: uppercase;
    letter-spacing: 0.05em;
    margin-bottom: var(--space-4);
}

.footer-newsletter p {
    font-size: var(--fs-sm);
    color: #94a3b8;
    margin-bottom: var(--space-4);
}

.newsletter-input-group {
    display: flex;
    gap: var(--space-2);
}

.newsletter-input-group input {
    flex: 1;
    padding: var(--space-3);
    background: rgba(255, 255, 255, 0.1);
    border: 1px solid rgba(255, 255, 255, 0.15);
    border-radius: var(--radius-md);
    color: white;
    font-family: var(--font-sans);
    font-size: var(--fs-sm);
    outline: none;
    transition: all var(--transition-fast);
}

.newsletter-input-group input::placeholder {
    color: #64748b;
}

.newsletter-input-group input:focus {
    border-color: var(--color-primary);
    background: rgba(255, 255, 255, 0.15);
}

.newsletter-input-group .btn {
    padding: var(--space-3) var(--space-5);
    font-size: var(--fs-sm);
    flex-shrink: 0;
}

/* Footer divider */
.footer-divider {
    border: none;
    border-top: 1px solid rgba(255, 255, 255, 0.1);
    margin: var(--space-10) 0 var(--space-6);
}

/* Footer bottom */
.footer-bottom {
    display: flex;
    justify-content: space-between;
    align-items: center;
    flex-wrap: wrap;
    gap: var(--space-4);
}

.footer-copyright {
    font-size: var(--fs-sm);
    color: #64748b;
}

.footer-copyright a {
    color: #94a3b8;
}

.footer-copyright a:hover {
    color: white;
}

.footer-social {
    display: flex;
    gap: var(--space-4);
}

.footer-social a {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 40px;
    height: 40px;
    background: rgba(255, 255, 255, 0.08);
    border-radius: var(--radius-md);
    color: #94a3b8;
    transition: all var(--transition-fast);
}

.footer-social a:hover {
    background: var(--color-primary);
    color: white;
    transform: translateY(-2px);
}

.footer-social svg {
    width: 20px;
    height: 20px;
}

/* ═══════════════════════════ */
/* ANIMATIONS — Keyframes */
/* ═══════════════════════════ */

/* Fade up */
@keyframes fadeUp {
    from {
        opacity: 0;
        transform: translateY(30px);
    }
    to {
        opacity: 1;
        transform: translateY(0);
    }
}

/* Fade in */
@keyframes fadeIn {
    from { opacity: 0; }
    to { opacity: 1; }
}

/* Scale in */
@keyframes scaleIn {
    from {
        opacity: 0;
        transform: scale(0.9);
    }
    to {
        opacity: 1;
        transform: scale(1);
    }
}

/* Animation utility classes */
[data-aos] {
    opacity: 0;
}

[data-aos="fade-up"] {
    animation: fadeUp 0.6s ease forwards;
}

[data-aos="fade-left"] {
    animation: fadeIn 0.8s ease forwards;
}

[data-aos="zoom-in"] {
    animation: scaleIn 0.5s ease forwards;
}

[data-aos-delay="0"]   { animation-delay: 0s; }
[data-aos-delay="100"] { animation-delay: 0.1s; }
[data-aos-delay="200"] { animation-delay: 0.2s; }
[data-aos-delay="300"] { animation-delay: 0.3s; }
[data-aos-delay="400"] { animation-delay: 0