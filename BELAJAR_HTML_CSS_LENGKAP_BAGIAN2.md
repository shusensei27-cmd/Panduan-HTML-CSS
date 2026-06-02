# 📘 BELAJAR HTML & CSS DARI NOL HINGGA MAHIR — BAGIAN 2 (LANJUTAN)
### Kelanjutan dari Bagian 3 (Implementasi Praktis) & Bagian 4 (Bonus & Best Practices)

> **Catatan**: Bagian ini adalah **kelanjutan** dari file `BELAJAR_HTML_CSS_LENGKAP.md`. Silakan baca file utama terlebih dahulu.

---

# 🚀 BAGIAN 3: Implementasi Praktis (Lanjutan)

### File 2: `style.css` (Lanjutan — Bagian CSS yang terpotong)

Setelah bagian Animasi di atas, kita lanjutkan dengan **Media Queries** untuk responsivitas:

```css
/* ════════════════════════════════════════════════════ *
 *  Media Queries — Responsive Design                   *
 * ════════════════════════════════════════════════════ */

/* ═══════════════════════════ */
/* TABLET (max-width: 1024px) */
/* ═══════════════════════════ */
@media (max-width: 1024px) {
    .hero .container {
        grid-template-columns: 1fr;
        text-align: center;
    }

    .hero-content {
        align-items: center;
    }

    .hero-description {
        max-width: 100%;
    }

    .hero-actions {
        justify-content: center;
    }

    .hero-visual {
        display: none;
    }

    .footer-grid {
        grid-template-columns: 1fr 1fr;
        gap: var(--space-8);
    }
}

/* ═══════════════════════════ */
/* MOBILE (max-width: 768px) */
/* ═══════════════════════════ */
@media (max-width: 768px) {
    :root {
        --header-height: 64px;
    }

    /* Tampilkan hamburger, sembunyikan nav links */
    .hamburger {
        display: flex;
    }

    .nav-links {
        display: none;
        position: absolute;
        top: var(--header-height);
        left: 0;
        right: 0;
        flex-direction: column;
        background: var(--color-bg);
        border-bottom: 1px solid var(--color-border);
        padding: var(--space-4);
        gap: var(--space-2);
        box-shadow: var(--shadow-lg);
    }

    .nav-links.active {
        display: flex;
    }

    .nav-link {
        padding: var(--space-3) var(--space-4);
        font-size: var(--fs-base);
    }

    .hero {
        padding: calc(var(--header-height) + var(--space-10)) 0 var(--space-10);
    }

    .hero-title {
        font-size: var(--fs-4xl);
    }

    .section {
        padding: var(--space-12) 0;
    }

    .section-title {
        font-size: var(--fs-3xl);
    }

    .features-grid {
        grid-template-columns: 1fr;
    }

    .portfolio-grid {
        grid-template-columns: 1fr;
    }

    .blog-grid {
        grid-template-columns: 1fr;
    }

    .blog-card {
        flex-direction: column;
        gap: var(--space-4);
    }

    .blog-date {
        flex-direction: row;
        min-width: auto;
        width: fit-content;
        height: auto;
        padding: var(--space-1) var(--space-3);
        gap: var(--space-2);
    }

    .blog-day {
        font-size: var(--fs-base);
    }

    .footer-grid {
        grid-template-columns: 1fr;
        gap: var(--space-10);
    }

    .footer-bottom {
        flex-direction: column;
        text-align: center;
    }

    .form-actions {
        flex-direction: column;
    }

    .form-actions .btn {
        width: 100%;
    }

    .newsletter-input-group {
        flex-direction: column;
    }

    .radio-options {
        flex-direction: column;
        gap: var(--space-3);
    }
}

/* ═══════════════════════════ */
/* MOBILE KECIL (max-width: 480px) */
/* ═══════════════════════════ */
@media (max-width: 480px) {
    .container {
        padding: 0 var(--space-4);
    }

    .hero-title {
        font-size: var(--fs-3xl);
    }

    .hero-actions {
        flex-direction: column;
        width: 100%;
    }

    .hero-actions .btn {
        width: 100%;
    }

    .section-title {
        font-size: var(--fs-2xl);
    }

    .portfolio-card {
        max-width: 100%;
    }

    .portfolio-grid {
        grid-template-columns: 1fr;
    }
}

/* ═══════════════════════════ */
/* CETAK (Print stylesheet) */
/* ═══════════════════════════ */
@media print {
    .site-header,
    .site-footer,
    .hero-actions,
    .blog-cta,
    .form-actions,
    .hamburger,
    .footer-social,
    .newsletter-form {
        display: none !important;
    }

    body {
        font-size: 12pt;
        color: black;
        background: white;
    }

    .section {
        padding: 1cm 0;
        page-break-inside: avoid;
    }

    a {
        color: black;
        text-decoration: underline;
    }

    a::after {
        content: " (" attr(href) ")";
        font-size: 0.8em;
        color: #666;
    }

    img {
        max-width: 100% !important;
        page-break-inside: avoid;
    }

    h1, h2, h3, h4 {
        page-break-after: avoid;
    }
}

/* ═══════════════════════════ */
/* REDUCED MOTION — Aksesibilitas */
/* ═══════════════════════════ */
@media (prefers-reduced-motion: reduce) {
    .feature-card:hover,
    .portfolio-card:hover,
    .blog-card:hover,
    .btn:hover {
        transform: none !important;
    }

    .portfolio-image img:hover {
        transform: none !important;
    }

    [data-aos] {
        opacity: 1 !important;
        animation: none !important;
    }
}
```

### File 3: `script.js` (JavaScript Pendukung)

```javascript
/**
 * Script.js — Portal Belajar Koding
 * JavaScript minimal untuk interaktivitas
 */

// Hamburger menu toggle
const hamburger = document.getElementById('hamburger');
const navLinks = document.getElementById('navLinks');

if (hamburger && navLinks) {
    hamburger.addEventListener('click', () => {
        const isOpen = navLinks.classList.toggle('active');
        hamburger.setAttribute('aria-expanded', isOpen);
        hamburger.setAttribute(
            'aria-label',
            isOpen ? 'Tutup menu navigasi' : 'Buka menu navigasi'
        );
    });

    // Close menu ketika link diklik (mobile)
    document.querySelectorAll('.nav-link').forEach((link) => {
        link.addEventListener('click', () => {
            navLinks.classList.remove('active');
            hamburger.setAttribute('aria-expanded', 'false');
            hamburger.setAttribute('aria-label', 'Buka menu navigasi');
        });
    });
}

// Smooth scroll untuk anchor links
document.querySelectorAll('a[href^="#"]').forEach((anchor) => {
    anchor.addEventListener('click', function (e) {
        const href = this.getAttribute('href');
        if (href === '#') return;
        e.preventDefault();
        const target = document.querySelector(href);
        if (target) {
            const headerOffset = 80;
            const elementPosition = target.getBoundingClientRect().top;
            const offsetPosition =
                elementPosition + window.pageYOffset - headerOffset;
            window.scrollTo({
                top: offsetPosition,
                behavior: 'smooth',
            });
        }
    });
});

// Update range input display
const rangeInput = document.getElementById('urgensi');
const rangeOutput = document.getElementById('urgensi-value');

if (rangeInput && rangeOutput) {
    const labels = {
        1: '1 (Rendah)',
        2: '2',
        3: '3 (Sedang)',
        4: '4',
        5: '5 (Tinggi)',
    };

    rangeInput.addEventListener('input', () => {
        rangeOutput.textContent = labels[rangeInput.value] || rangeInput.value;
    });
}

// Form validation feedback
const contactForm = document.querySelector('.contact-form');
if (contactForm) {
    contactForm.addEventListener('submit', (e) => {
        e.preventDefault();
        const valid = contactForm.checkValidity();

        if (valid) {
            alert('✅ Pesan berhasil dikirim! (Simulasi)');
            contactForm.reset();
        } else {
            // Browser akan menampilkan pesan validasi bawaan
            contactForm.reportValidity();
        }
    });
}

// Pause animation pada elemen yang sedang tidak terlihat (performance)
const observerOptions = {
    threshold: 0.1,
    rootMargin: '50px',
};

const observer = new IntersectionObserver((entries) => {
    entries.forEach((entry) => {
        if (entry.isIntersecting) {
            entry.target.style.animationPlayState = 'running';
        } else {
            entry.target.style.animationPlayState = 'paused';
        }
    });
}, observerOptions);

document.querySelectorAll('[data-aos]').forEach((el) => {
    observer.observe(el);
});

// Inisialisasi — dark mode detection
if (window.matchMedia('(prefers-color-scheme: dark)').matches) {
    document.documentElement.classList.add('dark-mode');
}

console.log('🚀 Portal Belajar Koding siap digunakan!');
```

---

## 3.3 Langkah-Langkah Menjalankan Proyek

### Cara Menjalankan di Browser

1. **Buat folder proyek** — misal `belajar-koding`
2. **Buat file-file berikut** di dalam folder tersebut:
   - `index.html` — copy kode HTML dari Bagian 3.2
   - `style.css` — copy kode CSS dari Bagian 3.2
   - `script.js` — copy kode JavaScript dari Bagian 3.2 (opsional)
3. **Buka file `index.html`** di browser:
   - Klik kanan file → Open with → Browser pilihan Anda
   - Atau drag-and-drop file ke browser
   - Atau double-click file `index.html`

### Cara Menjalankan dengan Live Server (VS Code — REKOMENDASI)

1. Buka folder proyek di **VS Code**
2. Install ekstensi **Live Server** (oleh Ritwick Dey)
3. Klik kanan file `index.html` → **Open with Live Server**
4. Browser akan terbuka otomatis di `http://localhost:5500`
5. **Keuntungan**: Setiap perubahan di file akan otomatis me-reload halaman!

### Debugging Menggunakan DevTools

**Buka DevTools:**
- **Chrome/Edge**: `F12` atau `Ctrl + Shift + I` (Windows) / `Cmd + Option + I` (Mac)
- **Firefox**: `F12` atau `Ctrl + Shift + I`
- Atau klik kanan halaman → **Inspect**

**Tab-Tab Penting di DevTools:**

| Tab | Fungsi |
|-----|--------|
| **Elements** | Melihat dan mengedit HTML/CSS secara live. Klik elemen → lihat box model → edit CSS langsung. |
| **Console** | Melihat error JavaScript, log, dan menjalankan kode JS interaktif. |
| **Network** | Melihat request HTTP (gambar, CSS, JS), waktu loading, status. |
| **Sources** | Debug JavaScript (breakpoints, step through). |
| **Performance** | Menganalisis performa halaman (loading time, rendering). |
| **Application** | Melihat storage (Local Storage, Cookies), Cache. |
| **Accessibility** | Memeriksa aksesibilitas halaman. |
| **Lighthouse** | Audit performa, aksesibilitas, SEO, dan best practices. |

**Tips Debugging CSS:**

```css
/* 1. Gunakan border outline untuk melihat ukuran elemen */
.debug * {
    outline: 1px solid red !important;
}

/* 2. Beri background transparan untuk melihat area */
.debug-box {
    background: rgba(255, 0, 0, 0.1);
}

/* 3. Di DevTools Elements tab:
   - Klik element → lihat "Styles" panel
   - Checklist/unchecklist properti CSS
   - Tambah properti baru secara live
   - Lihat "Computed" tab untuk nilai final
   - Lihat "Box Model" diagram */

/* 4. !important untuk testing cepat */
.test {
    color: red !important;  /* Hanya untuk debugging */
}
```

### Screenshot Deskripsi (Visual Layout Proyek)

```
┌─────────────────────────────────────────────────┐
│  [LOGO]  Beranda  Tentang  Portofolio  Blog  ☰  │ ← Header sticky
│                        Kontak                     │
├─────────────────────────────────────────────────┤
│  🔥 Selamat datang di portal belajar!           │
│  ┌─────────────────────┐  ┌──────────────────┐  │ ← Hero Section
│  │ Belajar HTML & CSS  │  │  ┌───── SVG ──┐  │  │   (Grid 2 kolom)
│  │ Dari Nol Hingga Mahir│  │  │ Ilustrasi  │  │  │
│  │                     │  │  │   Kode      │  │  │
│  │ [Mulai] [Portofolio]│  │  └────────────┘  │  │
│  └─────────────────────┘  └──────────────────┘  │
├─────────────────────────────────────────────────┤
│  Tentang Platform Ini                           │ ← Section
│  ┌──────┐  ┌──────┐  ┌──────┐  ┌──────┐       │   (4 column grid)
│  │ Card │  │ Card │  │ Card │  │ Card │       │
│  └──────┘  └──────┘  └──────┘  └──────┘       │
├─────────────────────────────────────────────────┤
│  Portofolio Proyek                              │ ← Section dark
│  ┌──────────┐  ┌──────────┐  ┌──────────┐     │   (3 column grid)
│  │  Card 1  │  │  Card 2  │  │  Card 3  │     │
│  │  Image   │  │  Image   │  │  Image   │     │
│  └──────────┘  └──────────┘  └──────────┘     │
├─────────────────────────────────────────────────┤
│  Artikel Blog                                   │ ← Section
│  ┌──────────────────────────────────────────┐  │   (Grid cards)
│  │ 📅 01 Jun │ Cara Memulai Belajar HTML... │  │
│  ├──────────────────────────────────────────┤  │
│  │ 📅 28 Mei │ CSS Flexbox vs Grid...       │  │
│  ├──────────────────────────────────────────┤  │
│  │ 📅 20 Mei │ 10 Properti CSS Wajib...     │  │
│  └──────────────────────────────────────────┘  │
├─────────────────────────────────────────────────┤
│  Hubungi Kami                                   │ ← Section dark
│  ┌──────────────────────────────────────────┐  │   (Form center)
│  │  Nama: [___________________________]     │  │
│  │  Email: [___________________________]    │  │
│  │  Kategori: [Dropdown ▼]                 │  │
│  │  Urgensi: [======o=================]     │  │
│  │  Pesan: [___________________________]    │  │
│  │  [✓] Setuju dengan syarat                │  │
│  │  ○ Email  ○ Telepon  ○ Keduanya          │  │
│  │  [Kirim Pesan] [Reset]                   │  │
│  └──────────────────────────────────────────┘  │
├─────────────────────────────────────────────────┤
│  ┌──────────────┐  ┌────────┐  ┌────────────┐ │ ← Footer (4 col)
│  │ Brand & Info │  │ Nav    │  │ Tutorial   │ │
│  │              │  │        │  │ & Newsletter│ │
│  └──────────────┘  └────────┘  └────────────┘ │
│  ─────────────────────────────────────────────  │
│  © 2026 BelajarKoding    [GitHub] [X] [LI]     │
└─────────────────────────────────────────────────┘
```

### Visual Mobile (≤768px):

```
┌─────────────────────┐
│ [LOGO]          [☰] │ ← Hamburger menu
├─────────────────────┤
│ 🔥 Selamat datang! │
│ Belajar HTML & CSS │ ← Hero jadi 1 kolom
│ Dari Nol Hingga Mahir│   (no illustration)
│ [Mulai Belajar]     │
│ [Lihat Portofolio]  │
├─────────────────────┤
│ Tentang Platform Ini│
│ ┌─────────────────┐ │ ← Card jadi 1 kolom
│ │     Card 1      │ │
│ ├─────────────────┤ │
│ │     Card 2      │ │
│ └─────────────────┘ │
├─────────────────────┤
│ Portofolio (1 kolom)│
│ Artikel (1 kolom)   │
│ Form (full width)   │
├─────────────────────┤
│ Footer (stacked)    │
│ © 2026 BelajarKoding│
└─────────────────────┘
```

---

## 3.4 Catatan Penting Tentang Proyek Ini

### Elemen HTML yang Diimplementasikan (80%+)

| Kategori | Elemen |
|----------|--------|
| **Semantik** | `<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<footer>`, `<figure>`, `<figcaption>`, `<address>` |
| **Heading** | `<h1>`, `<h2>`, `<h3>` |
| **Teks** | `<p>`, `<span>`, `<strong>`, `<em>`, `<mark>`, `<small>`, `<time>`, `<br>`, `<hr>`, `<blockquote>`, `<abbr>` |
| **Link** | `<a>` dengan atribut `href`, `target`, `rel`, `aria-label` |
| **Gambar** | `<img>` dengan `src`, `alt`, `loading`, `width`, `height` |
| **List** | `<ul>`, `<ol>`, `<li>` |
| **Tabel** | `<table>`, `<tr>`, `<th>`, `<td>` (dicontohkan di penjelasan) |
| **Form** | `<form>`, `<input>` (text, email, tel, range, checkbox, radio, file, hidden, submit), `<label>`, `<textarea>`, `<select>`, `<option>`, `<optgroup>`, `<button>`, `<fieldset>`, `<legend>`, `<output>` |
| **Multimedia** | `<svg>` inline, `<picture>` (dijelaskan) |
| **Embed** | `<iframe>` (dijelaskan) |
| **Interaktif** | `<details>`, `<summary>`, `<dialog>` (dijelaskan) |
| **Meta** | `<meta>`, `<link>`, `<title>`, `<style>`, `<script>` |

### Properti CSS yang Diimplementasikan (80%+)

| Kategori | Properti |
|----------|----------|
| **CSS Variables** | `--color-*`, `--font-*`, `--space-*`, `--radius-*`, `--shadow-*`, `--transition-*` |
| **Warna** | `color`, `background`, `background-color`, `background-image`, `background-clip`, `linear-gradient()` |
| **Tipografi** | `font-family`, `font-size`, `font-weight`, `font-style`, `line-height`, `text-align`, `text-decoration`, `text-transform`, `letter-spacing`, `text-shadow`, `-webkit-text-fill-color` |
| **Box Model** | `width`, `height`, `max-width`, `min-height`, `margin`, `padding`, `border`, `border-radius`, `box-sizing` |
| **Layout** | `display` (flex, grid, inline-flex, none, block), `position`, `top/right/bottom/left`, `z-index`, `overflow`, `float`, `clear` |
| **Flexbox** | `display: flex`, `flex-direction`, `flex-wrap`, `justify-content`, `align-items`, `align-content`, `gap`, `flex`, `order` |
| **Grid** | `display: grid`, `grid-template-columns` (repeat, auto-fit, minmax), `grid-template-areas`, `gap`, `align-items` |
| **Efek Visual** | `box-shadow`, `opacity`, `filter: blur()` (indirect), `backdrop-filter` |
| **Transform** | `transform: translateY`, `rotate`, `scale`, `transform-origin` |
| **Transisi** | `transition` (all, properti spesifik, timing, durasi) |
| **Animasi** | `@keyframes`, `animation-name`, `animation-duration`, `animation-delay`, `animation-fill-mode`, `animation-play-state` |
| **Selektor** | Type, Class, ID, Universal, Descendant, Child, Adjacent Sibling, Attribute, Pseudo-class (`:hover`, `:active`, `:focus-visible`, `:nth-child`, `:user-invalid`, `:user-valid`), Pseudo-element (`::after`, `::before`, `::placeholder`, `::file-selector-button`) |
| **Lain-lain** | `cursor`, `list-style`, `outline`, `resize`, `object-fit`, `visibility`, `white-space`, `accent-color`, `user-select`, `pointer-events` |
| **Responsive** | `@media (max-width)`, `@media (prefers-color-scheme)`, `@media (prefers-reduced-motion)`, `@media print`, `clamp()`, mobile-first |
| **Dark Mode** | `prefers-color-scheme: dark` dengan CSS variables override |

---

# 🎁 BAGIAN 4: Bonus & Best Practices

## 4.1 Aksesibilitas (A11y)

Aksesibilitas web memastikan website Anda bisa digunakan oleh **semua orang**, termasuk penyandang disabilitas.

### Prinsip Dasar Aksesibilitas (POUR)

| Prinsip | Penjelasan |
|---------|-----------|
| **Perceivable** | Konten harus bisa dirasakan oleh setidaknya satu indra. |
| **Operable** | Semua komponen bisa dioperasikan (mouse, keyboard, screen reader). |
| **Understandable** | Informasi dan interface harus mudah dipahami. |
| **Robust** | Konten harus bisa diinterpretasikan oleh berbagai alat bantu. |

### Praktik Aksesibilitas Penting

#### 1. Alt Text pada Gambar

```html
<!-- ✅ INFORMATIF: deskripsikan isi gambar -->
<img src="grafik.png" alt="Grafik penjualan Q1 2026: Rp 50jt, Q2: Rp 75jt">

<!-- ✅ DEKORATIF: alt kosong + role presentation -->
<img src="garis-pemisah.png" alt="" role="presentation">

<!-- ✅ FUNGSIONAL: deskripsikan fungsi/tujuan -->
<a href="/produk"><img src="tombol-beli.png" alt="Beli produk ini sekarang"></a>

<!-- ❌ JANGAN: alt tidak perlu dengan "gambar dari" atau "image of" -->
<img src="foto.jpg" alt="gambar dari pemandangan"> <!-- ❌ Redundan -->
<img src="foto.jpg" alt="Pemandangan gunung">     <!-- ✅ Langsung -->
```

#### 2. ARIA (Accessible Rich Internet Applications)

```html
<!-- aria-label — label tambahan untuk elemen yang tidak terlihat -->
<button aria-label="Tutup dialog">×</button>

<!-- aria-labelledby — menghubungkan ke elemen lain sebagai label -->
<div role="dialog" aria-labelledby="dialog-title">
    <h2 id="dialog-title">Konfirmasi Hapus</h2>
</div>

<!-- aria-describedby — deskripsi tambahan -->
<input type="text" aria-describedby="password-hint">
<span id="password-hint">Minimal 8 karakter, kombinasi huruf dan angka</span>

<!-- aria-expanded — status expand/collapse -->
<button aria-expanded="false" aria-controls="menu">Menu</button>
<div id="menu" hidden>...</div>

<!-- aria-current — halaman/item aktif -->
<a href="/" aria-current="page">Beranda</a>

<!-- role — mengubah peran elemen (gunakan semantic HTML jika memungkinkan) -->
<nav role="navigation">...</nav>
<button role="tab">Tab 1</button>

<!-- aria-live — region live update -->
<div aria-live="polite" id="notifikasi">Pesan baru muncul di sini</div>
<!-- aria-live="off" — default, jangan umumkan -->
<!-- aria-live="polite" — umumkan saat user idle -->
<!-- aria-live="assertive" — umumkan segera (interupsi) -->

<!-- aria-hidden — sembunyikan dari screen reader -->
<span aria-hidden="true">→</span>
```

**Peringkat Penggunaan ARIA:**

```
⚠️ FIRST RULE OF ARIA:
"Tidak ada ARIA yang lebih baik daripada ARIA yang salah."

Gunakan semantic HTML sebelum ARIA:
✅ <nav> lebih baik dari <div role="navigation">
✅ <button> lebih baik dari <div role="button" tabindex="0">
✅ <h1> lebih baik dari <div role="heading" aria-level="1">
```

#### 3. Fokus Visible

```css
/* JANGAN hapus outline tanpa pengganti! */
*:focus {
    outline: none; /* ❌ HAPUS INI */
}

/* ✅ GANTI DENGAN: */
*:focus-visible {
    outline: 2px solid #4A90D9;
    outline-offset: 2px;
    border-radius: 4px;
}

/* ✅ Atau dengan box-shadow */
*:focus-visible {
    outline: none;
    box-shadow: 0 0 0 3px rgba(74, 144, 217, 0.5);
}
```

#### 4. Kontras Warna

Rasio kontras minimal:
- **Teks normal** (<18px regular, <14px bold): **4.5:1**
- **Teks besar** (≥18px regular, ≥14px bold): **3:1**
- **Komponen UI** (ikon, border input): **3:1**

```css
/* Alat cek kontras: */
/* - WebAIM Contrast Checker: https://webaim.org/resources/contrastchecker/ */
/* - Chrome DevTools → Elements → Color Picker (tunjukkan rasio) */

/* Contoh kontras yang baik: */
.text-good {
    color: #1a1a1a;        /* Hampir hitam */
    background: #ffffff;   /* Putih */
    /* Rasio: 18.9:1 ✅ */
}

.text-warning {
    color: #666666;        /* Abu-abu */
    background: #ffffff;
    /* Rasio: 5.4:1 ✅ (masih OK untuk teks besar) */
}

.text-bad {
    color: #999999;        /* Abu-abu muda */
    background: #ffffff;
    /* Rasio: 2.8:1 ❌ GAGAL */
}
```

#### 5. Semantic HTML untuk Navigasi Screen Reader

```html
<!-- Skip link — lewati navigasi langsung ke konten -->
<body>
    <a href="#main-content" class="skip-link">Langsung ke konten utama</a>
    <header>...</header>
    <main id="main-content">...</main>
</body>
```

```css
.skip-link {
    position: absolute;
    top: -100%;
    left: 0;
    background: #333;
    color: white;
    padding: 10px;
    z-index: 10000;
}

.skip-link:focus {
    top: 0;
}
```

#### 6. Form Aksesibel

```html
<!-- Setiap input WAJIB punya label -->
<label for="email">Alamat Email</label>
<input type="email" id="email" name="email" required>

<!-- Error message yang terhubung -->
<label for="password">Password</label>
<input type="password" id="password" name="password"
       aria-describedby="password-error" aria-invalid="true">
<span id="password-error" role="alert">Password minimal 8 karakter</span>

<!-- Fieldset untuk grup -->
<fieldset>
    <legend>Metode Pembayaran</legend>
    <input type="radio" id="cc" name="payment" value="cc">
    <label for="cc">Kartu Kredit</label>
    <input type="radio" id="bank" name="payment" value="bank">
    <label for="bank">Transfer Bank</label>
</fieldset>
```

---

## 4.2 SEO (Search Engine Optimization) Dasar

### Meta Tags Esensial

```html
<!-- 1. Title — judul halaman (WAJIB unik per halaman) -->
<title>Belajar HTML & CSS - Panduan Lengkap Pemula | BelajarKoding</title>

<!-- 2. Meta Description — deskripsi di hasil pencarian -->
<meta name="description" content="Panduan lengkap belajar HTML dan CSS dari nol hingga mahir. Cocok untuk pemula yang ingin menguasai web development.">

<!-- 3. Canonical — cegah konten duplikat -->
<link rel="canonical" href="https://belajarkoding.com/belajar-html-css">

<!-- 4. Open Graph — untuk sharing di media sosial -->
<meta property="og:title" content="Belajar HTML & CSS">
<meta property="og:description" content="Panduan lengkap dari nol hingga mahir">
<meta property="og:image" content="https://belajarkoding.com/thumbnail.jpg">
<meta property="og:url" content="https://belajarkoding.com/belajar-html-css">
<meta property="og:type" content="article">

<!-- 5. Twitter Card -->
<meta name="twitter:card" content="summary_large_image">
<meta name="twitter:title" content="Belajar HTML & CSS">
<meta name="twitter:description" content="Panduan lengkap dari nol hingga mahir">

<!-- 6. Robots — kontrol indexing -->
<meta name="robots" content="index, follow">
<!-- index/noindex: apakah halaman di-index -->
<!-- follow/nofollow: apakah link diikuti -->

<!-- 7. hreflang — versi bahasa -->
<link rel="alternate" href="https://belajarkoding.com/en/learn-html-css" hreflang="en">
<link rel="alternate" href="https://belajarkoding.com/id/belajar-html-css" hreflang="id">

<!-- 8. JSON-LD Structured Data (Schema.org) -->
<script type="application/ld+json">
{
    "@context": "https://schema.org",
    "@type": "Article",
    "headline": "Belajar HTML & CSS - Panduan Lengkap",
    "description": "Panduan lengkap belajar HTML dan CSS dari nol hingga mahir.",
    "author": {
        "@type": "Person",
        "name": "Admin BelajarKoding"
    },
    "datePublished": "2026-06-01",
    "dateModified": "2026-06-01"
}
</script>
```

### Struktur Heading untuk SEO

```html
<!-- ✅ Struktur heading yang baik: -->
<h1>Belajar HTML & CSS Lengkap</h1>           <!-- Hanya 1 h1 -->
    <h2>Pengenalan HTML</h2>
        <h3>Apa itu HTML?</h3>
        <h3>Sejarah HTML</h3>
    <h2>Dasar-Dasar CSS</h2>
        <h3>Selektor CSS</h3>
        <h3>Box Model</h3>

<!-- ❌ Struktur heading yang buruk: -->
<h1>Judul</h1>
    <h3>Langsung h3 (lompat h2)</h3>           <!-- ❌ Lompat hierarki -->
    <h2>Sub judul</h2>
        <h2>Sub judul lain</h2>                  <!-- ❌ Dua h2 tanpa h1 di antara -->
```

### Tips SEO Lainnya

| Aspek | Praktik Baik |
|-------|-------------|
| **URL** | Gunakan slug deskriptif: `/belajar-html-css` bukan `/page?id=123` |
| **Alt text** | Deskripsikan gambar dengan kata kunci relevan |
| **Internal link** | Tautkan antar halaman di website Anda |
| **External link** | Gunakan `rel="noopener"` + `target="_blank"` untuk link luar |
| **Mobile friendly** | Responsive design (viewport meta tag) |
| **Page speed** | Optimasi gambar, minify CSS/JS, gunakan caching |
| **Sitemap** | Submit `sitemap.xml` ke Google Search Console |
| **robots.txt** | File di root yang mengontrol crawler |

---

## 4.3 Performa CSS

### Minify CSS

CSS minification menghapus spasi, komentar, baris baru yang tidak perlu.

```css
/* Sebelum minify: */
.container {
    max-width: 1200px;
    margin: 0 auto;
    padding: 0 20px;
}

/* Setelah minify: */
.container{max-width:1200px;margin:0 auto;padding:0 20px}
```

**Tools Minify:**
- Online: CSS Minifier (cssminifier.com)
- Build tools: Webpack (css-minimizer-webpack-plugin), Vite (built-in)
- VS Code Extension: Minify

### Critical CSS

Critical CSS adalah CSS yang dibutuhkan untuk merender **above-the-fold** (konten yang terlihat pertama kali).

```html
<!-- 1. Inline critical CSS di <head> -->
<head>
    <style>
        /* CSS untuk hero, navigasi, layout dasar */
        body { font-family: Arial, sans-serif; margin: 0; }
        header { background: #333; color: white; padding: 1rem; }
        .hero { min-height: 80vh; display: flex; align-items: center; }
    </style>
    <!-- 2. Load CSS lainnya secara async -->
    <link rel="stylesheet" href="style.css" media="print" onload="this.media='all'">
    <noscript><link rel="stylesheet" href="style.css"></noscript>
</head>
```

**Tools Critical CSS:**
- Critical (npm package): `npx critical index.html > critical.css`
- Online: CriticalCSS.com

### Hindari Layout Thrashing

Layout thrashing terjadi saat JavaScript membaca **dan** menulis properti layout secara bergantian, memaksa browser melakukan reflow berulang kali.

```javascript
// ❌ BURUK — layout thrashing
const boxes = document.querySelectorAll('.box');
for (let i = 0; i < boxes.length; i++) {
    boxes[i].style.width = boxes[i].offsetWidth + 10 + 'px'; // Read + Write setiap iterasi
}

// ✅ BAIK — batch read, lalu batch write
const boxes = document.querySelectorAll('.box');
const widths = [];
for (let i = 0; i < boxes.length; i++) {
    widths.push(boxes[i].offsetWidth); // Batch read
}
for (let i = 0; i < boxes.length; i++) {
    boxes[i].style.width = widths[i] + 10 + 'px'; // Batch write
}
```

**Properti yang menyebabkan reflow (layout):**
`offsetHeight`, `offsetWidth`, `offsetTop`, `offsetLeft`, `scrollTop`, `scrollLeft`, `clientHeight`, `clientWidth`, `getComputedStyle()`, `getBoundingClientRect()`

### Tips Performa CSS Lainnya

```css
/* 1. Gunakan transform dan opacity untuk animasi (tidak trigger reflow) */
/* ✅ Efisien — hanya compositing */
.element {
    transform: translateX(100px);
    opacity: 0.5;
}

/* ❌ Tidak efisien — trigger layout + paint */
.element {
    left: 100px;
    top: 50px;
}

/* 2. Hindari @import — blocking */
/* ❌ */
@import url('style.css');

/* ✅ Gunakan <link> di HTML */
<link rel="stylesheet" href="style.css">

/* 3. Gunakan content-visibility untuk off-screen content */
.article-card {
    content-visibility: auto;    /* Render hanya saat mendekati viewport */
    contain-intrinsic-size: 200px; /* Perkiraan ukuran untuk scrollbar */
}

/* 4. Hindari selektor yang terlalu spesifik dan kompleks */
/* ❌ Lambat */
div > nav > ul > li > a[href^="https"]:hover { ... }

/* ✅ Lebih cepat */
.nav-link:hover { ... }

/* 5. Gunakan will-change dengan hati-hati */
.element {
    will-change: transform, opacity;  /* Beri tahu browser akan ada perubahan */
    /* Hanya gunakan jika benar-benar perlu! Jangan di sembarang elemen */
}
```

---

## 4.4 Kompatibilitas Browser

### Cek Dukungan Browser dengan Can I Use

**Website**: [caniuse.com](https://caniuse.com)

```css
/* Cari properti di caniuse.com untuk melihat dukungan browser */

/* Contoh: CSS Grid — 98.5% dukungan global */
.grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
}

/* Fallback untuk browser lama */
.grid {
    display: flex;
    flex-wrap: wrap;
}

@supports (display: grid) {
    .grid {
        display: grid;
        flex-wrap: unset;
    }
}
```

### Feature Query (`@supports`)

```css
/* Cek apakah browser mendukung properti tertentu */
@supports (display: grid) {
    .container {
        display: grid;
        grid-template-columns: repeat(3, 1fr);
    }
}

@supports not (display: grid) {
    .container {
        display: flex;
        flex-wrap: wrap;
    }
}

@supports (gap: 1rem) {
    .flex-layout {
        gap: 1rem;
    }
}

@supports (selector(:has(p))) {
    /* CSS4 :has() selector */
    .card:has(img) {
        grid-column: span 2;
    }
}
```

### Browser Fallback Strategies

```css
/* 1. Nilai fallback — deklarasikan properti lama sebelum baru */
.element {
    background: #333;                    /* Fallback */
    background: rgba(0, 0, 0, 0.8);      /* Modern */
}

.element {
    width: 100%;                         /* Fallback */
    width: calc(100% - 40px);            /* Modern */
}

/* 2. Vendor prefix untuk properti eksperimental */
.element {
    -webkit-backdrop-filter: blur(10px); /* Safari, Chrome < 76 */
    backdrop-filter: blur(10px);         /* Standar */
}

/* 3. Polyfill — JavaScript untuk menambahkan dukungan browser lama */
<!-- Modernizr — library deteksi fitur -->
<script src="https://cdnjs.cloudflare.com/ajax/libs/modernizr/2.8.3/modernizr.min.js"></script>
```

### Tabel Dukungan Properti Populer (per 2026)

| Properti | Chrome | Firefox | Safari | Edge | IE11 |
|----------|--------|---------|--------|------|------|
| CSS Grid | ✅ | ✅ | ✅ | ✅ | ❌ (prefix) |
| Flexbox | ✅ | ✅ | ✅ | ✅ | ⚠️ (partial) |
| CSS Variables | ✅ | ✅ | ✅ | ✅ | ❌ |
| CSS Grid Gap | ✅ | ✅ | ✅ | ✅ | ❌ |
| backdrop-filter | ✅ | ✅ | ✅ | ✅ | ❌ |
| :focus-visible | ✅ | ✅ | ✅ | ✅ | ❌ |
| clamp() | ✅ | ✅ | ✅ | ✅ | ❌ |
| prefers-color-scheme | ✅ | ✅ | ✅ | ✅ | ❌ |
| accent-color | ✅ | ✅ | ⚠️ (15+) | ✅ | ❌ |
| container queries | ✅ | ✅ | ⚠️ (16+) | ✅ | ❌ |

---

## 4.5 Tips Debugging CSS

### 1. Gunakan Border/Outline untuk Visualisasi

```css
/* Lihat area setiap elemen */
* {
    outline: 1px solid red;          /* Garis tipis */
    /* background: rgba(255, 0, 0, 0.05); */  /* Transparan */
}

/* Atau hanya elemen tertentu */
.suspect-element {
    outline: 2px dashed blue;
}
```

### 2. Gunakan DevTools Secara Efektif

**Elements Tab:**
- Klik **Select Element** (panah kiri atas) → klik elemen di halaman
- **Styles panel**: Lihat semua CSS yang mempengaruhi elemen
  - Checklist untuk menonaktifkan properti
  - Klik nilai untuk mengubah
  - Tambah properti baru
- **Computed tab**: Lihat nilai final setelah kaskade
  - Filter properti (misal cari "width")
- **Box Model diagram**: Lihat margin, border, padding, content
- **Layout tab**: Lihat grid/flexbox overlay

### 3. Combo CSS untuk Debugging

```css
/* ★ Classic debugging combo */
.debug {
    background: rgba(255, 0, 0, 0.1) !important;  /* Lihat area */
    outline: 2px solid red !important;             /* Lihat border */
}

/* ★ Lihat scroll overflow */
.debug-overflow {
    overflow: auto !important;
    max-height: 100vh;
}

/* ★ Lihat elemen tersembunyi */
.debug-hidden {
    visibility: visible !important;
    opacity: 1 !important;
    display: block !important;
    clip: auto !important;
    overflow: visible !important;
}
```

### 4. Tips Debugging Spesifik

| Masalah | Cara Debug |
|---------|-----------|
| Elemen hilang | Cek `display: none`, `visibility: hidden`, `opacity: 0`, `overflow: hidden` |
| Ukuran tidak sesuai | Cek `box-sizing`, `width`/`max-width`, padding, border |
| Posisi salah | Cek `position`, `top/left/right/bottom`, margin |
| z-index tidak berfungsi | Cek parent punya `position: static` (z-index tidak berfungsi), stacking context |
| Flexbox tidak sesuai | Cek `flex-basis`, `flex-grow`, `flex-shrink`, `min-width: 0` |
| Grid tidak rapi | Cek `grid-template-columns`, gap, `align-items` |
| Background tidak muncul | Cek ukuran elemen (mungkin 0), `background-size`, path gambar |
| Transisi tidak bekerja | Cek properti yang di-transition, pastikan ada perubahan state |
| Animasi tidak jalan | Cek `animation-name` cocok dengan `@keyframes`, durasi > 0 |

### 5. Console Commands Berguna

```javascript
// Di DevTools Console:

// Lihat semua event listener di elemen
getEventListeners(document.querySelector('button'));

// Monitor event tertentu
monitorEvents(document.querySelector('input'), 'focus');

// Cek class inheritance di prototype
dir(document.querySelector('div'));

// Ukur performa layout dengan performance API
performance.mark('start');
// ... action ...
performance.mark('end');
performance.measure('layout', 'start', 'end');
performance.getEntriesByType('measure');

// Cek selektor CSS — berapa elemen yang match
$$('.my-class');          // Semua elemen dengan class
$x('//div[@class="box"]'); // XPath query
```

### 6. Chrome Extensions untuk CSS

| Extension | Fungsi |
|-----------|--------|
| **Pesticide** | Tampilkan border di semua elemen (debug layout) |
| **CSS Peeper** | Extract CSS dari website |
| **ColorZilla** | Eyedropper, color picker, gradient generator |
| **WhatFont** | Identifikasi font yang digunakan |
| **Wappalyzer** | Lihat teknologi yang digunakan website |
| **Accessibility Insights** | Audit aksesibilitas |
| **Lighthouse** | Audit performa, SEO, aksesibilitas (bawaan Chrome) |

---

## 4.6 Sumber Belajar Lanjutan

### Dokumentasi Resmi

| Sumber | URL | Deskripsi |
|--------|-----|-----------|
| **MDN Web Docs** | developer.mozilla.org | Dokumentasi ** paling lengkap** dan terpercaya untuk HTML, CSS, JavaScript. |
| **W3C Specifications** | w3.org/TR | Spesifikasi resmi HTML dan CSS. |
| **CSS-Tricks** | css-tricks.com | Tutorial, panduan, dan artikel CSS praktis. |
| **WHATWG HTML Standard** | html.spec.whatwg.org | Spesifikasi HTML living standard. |
| **Can I Use** | caniuse.com | Cek kompatibilitas browser untuk properti CSS. |

### Platform Pembelajaran Interaktif

| Platform | URL | Deskripsi |
|----------|-----|-----------|
| **freeCodeCamp** | freecodecamp.org | Belajar coding gratis dengan proyek dan sertifikat. |
| **Codecademy** | codecademy.com | Kursus interaktif HTML/CSS (gratis & berbayar). |
| **Khan Academy** | khanacademy.org | Kursus HTML/CSS gratis untuk pemula. |
| **Sololearn** | sololearn.com | Belajar coding via mobile app. |
| **W3Schools** | w3schools.com | Tutorial dasar dengan "Try it Yourself" editor. |
| **Frontend Mentor** | frontendmentor.com | Tantangan proyek nyata dengan desain yang disediakan. |

### YouTube Channels (Indonesia)

| Channel | Fokus | Link |
|---------|-------|------|
| **Web Programming UNPAS** (Sandhika Galih) | HTML, CSS, JavaScript, PHP — playlist lengkap untuk pemula. | youtube.com/@sandhikagalih |
| **Dea Afrizal** | HTML, CSS, Tailwind, React. | youtube.com/@deaafrizal |
| **WPU - CSS Dasar** | Playlist CSS Dasar yang sangat terstruktur. | youtube.com/playlist?list=PLFIM0718LjIUBrbm6Gdh6k7ZUvPIAZm7p |
| **Kelas Terbuka** | HTML, CSS, JavaScript, Python. | youtube.com/@kelasterbuka |
| **Taman Kode** | Tutorial coding untuk pemula. | youtube.com/@tamankode |
| **Ngoding Pintar** | HTML, CSS, JavaScript, framework. | youtube.com/@ngodingpintar |

### YouTube Channels (English)

| Channel | Fokus |
|---------|-------|
| **Kevin Powell** | CSS expert — tips, trik, dan best practices CSS. |
| **Web Dev Simplified** | HTML, CSS, JavaScript — dijelaskan secara sederhana. |
| **The Net Ninja** | Playlist lengkap HTML, CSS, Flexbox, Grid. |
| **Traversy Media** | Tutorial crash course HTML/CSS. |
| **Fireship** | Ringkasan cepat konsep CSS dalam 100 detik. |
| **DesignCourse** | UI/UX design + frontend coding. |

### Buku Rekomendasi

| Judul | Penulis | Deskripsi |
|-------|---------|-----------|
| **HTML & CSS: Design and Build Websites** | Jon Duckett | Buku visual terbaik untuk pemula. |
| **CSS: The Definitive Guide** | Eric Meyer | Referensi CSS paling komprehensif. |
| **CSS Secrets** | Lea Verou | 47 teknik CSS lanjutan. |
| **The Book of CSS3** | Peter Gasston | Panduan lengkap CSS3. |

### Tools Gratis

| Tool | URL | Fungsi |
|------|-----|--------|
| **CodePen** | codepen.io | Editor CSS online, lihat hasil langsung. Preview & share. |
| **JSFiddle** | jsfiddle.net | Editor HTML/CSS/JS online. |
| **GitHub Pages** | pages.github.com | Hosting website statis gratis. |
| **Netlify** | netlify.com | Hosting + deploy otomatis dari GitHub. |
| **Vercel** | vercel.com | Hosting untuk frontend projects. |
| **Google Fonts** | fonts.google.com | Ribuan font gratis. |
| **Font Awesome** | fontawesome.com | Ikon vektor gratis. |
| **Heroicons** | heroicons.com | Ikon SVG gratis dari Tailwind CSS. |
| **Unsplash** | unsplash.com | Foto gratis untuk website. |
| **Placehold** | placehold.co | Placeholder image generator. |
| **Coolors** | coolors.co | Color palette generator. |
| **Gradient Generator** | cssgradient.io | Buat gradien CSS secara visual. |
| **Grid Generator** | cssgrid-generator.netlify.app | Buat grid CSS visual. |
| **Flexbox Froggy** | flexboxfroggy.com | Game belajar flexbox. |
| **Grid Garden** | cssgridgarden.com | Game belajar CSS Grid. |
| **CSS Diner** | flukeout.github.io | Game belajar CSS selector. |

---

## 4.7 Checklist: Apa yang Harus Dikuasai?

### Level Pemula ✅

- [ ] Memahami struktur dasar HTML (`<!DOCTYPE>`, `<html>`, `<head>`, `<body>`)
- [ ] Menguasai heading (`<h1>`-`<h6>`), paragraf (`<p>`), link (`<a>`), gambar (`<img>`)
- [ ] Membuat list (`<ul>`, `<ol>`, `<li>`)
- [ ] Membuat tabel sederhana (`<table>`, `<tr>`, `<th>`, `<td>`)
- [ ] Membuat form dasar (`<form>`, `<input>`, `<label>`, `<textarea>`, `<button>`)
- [ ] Mengerti perbedaan elemen block vs inline
- [ ] Memahami CSS dasar: color, font-size, background, margin, padding, border
- [ ] Menerapkan CSS dengan 3 cara (inline, internal, eksternal)
- [ ] Menggunakan class dan ID selector
- [ ] Membuat layout sederhana dengan `display: block/inline-block`
- [ ] Memahami Box Model

### Level Menengah ⭐

- [ ] Menguasai semantic HTML5 (`<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<aside>`, `<footer>`)
- [ ] Validasi form HTML5 (`required`, `pattern`, `minlength`, dll)
- [ ] Multimedia (`<audio>`, `<video>`, `<iframe>`, `<figure>`)
- [ ] CSS Flexbox (container + item properties)
- [ ] CSS Grid (template columns/rows, areas, gap)
- [ ] Position (relative, absolute, fixed, sticky)
- [ ] Pseudo-class (`:hover`, `:focus`, `:nth-child`, `:not`)
- [ ] Pseudo-element (`::before`, `::after`, `::selection`)
- [ ] Transisi CSS (`transition`)
- [ ] Transformasi (`transform: translate, rotate, scale`)
- [ ] Responsive Design dengan Media Queries
- [ ] CSS Variables (Custom Properties)
- [ ] Dark Mode dengan `prefers-color-scheme`

### Level Mahir ⭐⭐

- [ ] Animasi CSS (`@keyframes`, `animation`)
- [ ] Gradien (`linear-gradient`, `radial-gradient`, `conic-gradient`)
- [ ] Shadow (`box-shadow`, `text-shadow`, `filter: drop-shadow()`)
- [ ] Filter CSS (`filter: blur, brightness, grayscale, dll`)
- [ ] Clip-path untuk bentuk kustom
- [ ] CSS Grid advanced (auto-fill, auto-fit, minmax, grid-auto-flow)
- [ ] Container Queries (CSS4)
- [ ] CSS Nesting (CSS4 native)
- [ ] Aksesibilitas (ARIA, fokus, kontras, semantic HTML)
- [ ] SEO dasar (meta tag, structured data, heading structure)
- [ ] Performa CSS (minify, critical CSS, content-visibility)
- [ ] Custom Fonts (Google Fonts, @font-face)
- [ ] Advanced Selectors (`:has()`, `:is()`, `:where()`, `nth-of-type`)
- [ ] Vendor prefix dan fallback
- [ ] Debugging dengan DevTools level expert

---

## 4.8 Kutipan Inspiratif untuk Developer Pemula

> *"Any fool can write code that a computer can understand. Good programmers write code that humans can understand."* — Martin Fowler

> *"CSS is not just about making things look pretty. It's about making things work across different devices, screen sizes, and user needs."* — Tidak diketahui

> *"The best way to learn is to build. Start small, break things, fix them, and keep going."* — Tidak diketahui

> *"Web development is not about mastering everything. It's about solving problems one step at a time."* — Tidak diketahui

---

## 4.9 Penutup

Selamat! Anda telah menyelesaikan **panduan super lengkap** HTML & CSS ini. 🎉

**Apa yang telah Anda pelajari:**

1. ✅ **HTML** — Semua elemen, atribut, struktur, best practices dari dasar hingga mahir
2. ✅ **CSS** — Semua properti, selektor, layout (Flexbox + Grid), animasi, hingga responsive design
3. ✅ **Implementasi Praktis** — Proyek website lengkap dengan 3 file (HTML, CSS, JS)
4. ✅ **Bonus** — Aksesibilitas, SEO, performa, debugging, dan sumber belajar lanjutan

**Langkah Selanjutnya:**

1. **Praktik, praktik, praktik!** — Buat website sederhana sendiri
2. **Build proyek nyata** — Landing page, portofolio, blog
3. **Pelajari JavaScript** — Tambahkan interaktivitas
4. **Eksplorasi framework** — Bootstrap, Tailwind CSS
5. **Bergabung dengan komunitas** — Diskusi, tanya jawab, berbagi
6. **Jangan pernah berhenti belajar!**

> **Ingat**: Setiap developer ahli dulunya adalah pemula. Yang membedakan adalah **konsistensi** dan **kemauan untuk terus belajar**.

---

*📝 Panduan ini ditulis dengan ❤️ untuk membantu Anda menguasai HTML & CSS. Jika ada pertanyaan, jangan ragu untuk menghubungi kami.*

**Selamat coding! 🚀**