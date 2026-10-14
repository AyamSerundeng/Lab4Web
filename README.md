# Lab 4 - CSS Lanjutan (Box Model, Float, Clear & Layout Sederhana)

**Nama:** Khairi Ramadhan Yudhatama (312510099)  
**Kelas:** Pemrograman Web (I251A)  
**Dosen:** Agung Nugroho, S.Kom., M.Kom.

---

## 1. Persiapan Membuat Dokumen HTML

Buat file baru dengan nama `lab4_box.html` dan isi dengan struktur dasar HTML berikut:

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Box Element</title>
  </head>
  <body>
    <header>
      <h1>Box Element</h1>
    </header>
  </body>
</html>
```

**Hasil di browser:**

![Screenshot 1 - Persiapan dokumen](screenshots/01-persiapan-dokumen.png)

---

## 2. Membuat Box Element

Tambahkan tiga elemen `div` di dalam tag `<section>`:

```html
<section>
  <div class="div1">Div 1</div>
  <div class="div2">Div 2</div>
  <div class="div3">Div 3</div>
</section>
```

**Hasil di browser:**

![Screenshot 2 - Box Element](screenshots/02-box-element.png)

---

## 3. CSS Float Property

Tambahkan deklarasi CSS di dalam tag `<head>`:

```html
<style>
  div {
    float: left;
    padding: 10px;
  }
  .div1 {
    background: red;
  }
  .div2 {
    background: yellow;
  }
  .div3 {
    background: green;
  }
</style>
```

Property `float: left` membuat ketiga div berjejer secara horizontal.

**Hasil di browser:**

![Screenshot 3 - Float Property](screenshots/03-float-property.png)

---

## 4. Mengatur Clearfix Element

Tambahkan `div4` setelah `div3`:

```html
<section>
  <div class="div1">Div 1</div>
  <div class="div2">Div 2</div>
  <div class="div3">Div 3</div>
  <div class="div4">Div 4</div>
</section>
```

Lalu tambahkan CSS untuk `.div4`:

```css
.div4 {
  background-color: blue;
  clear: left;
  float: none;
}
```

Property `clear: left` membuat `div4` turun ke baris baru dan tidak dipengaruhi float sebelumnya.

**Hasil di browser:**

![Screenshot 4 - Clearfix](screenshots/04-clearfix.png)

---

## 5. Membuat Layout Sederhana

Buat folder baru bernama `lab4_layout`. Di dalamnya buat dua file:

- `home.html`
- `style.css`

### Struktur dasar `home.html`

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Layout Sederhana</title>
    <link rel="stylesheet" href="style.css" />
  </head>
  <body>
    <div id="container">
      <header>
        <h1>Layout Sederhana</h1>
      </header>
      <nav>
        <a href="home.html" class="active">Home</a>
        <a href="artikel.html">Artikel</a>
        <a href="about.html">About</a>
        <a href="kontak.html">Kontak</a>
      </nav>
      <section id="hero"></section>
      <section id="wrapper">
        <section id="main"></section>
        <aside id="sidebar"></aside>
      </section>
      <footer>
        <p>&copy; 2021 - Universitas Pelita Bangsa</p>
      </footer>
    </div>
  </body>
</html>
```

**Hasil kerangka di browser:**

![Screenshot 5 - Kerangka Layout](screenshots/05-kerangka-layout.png)

---

## 6. CSS Dasar (Reset, Font & Container)

Isi file `style.css` dengan kode berikut:

```css
/* import google font */
@import url("https://fonts.googleapis.com/css2?family=Open+Sans:ital,wght@0,300;0,400;0,600;0,700;0,800;1,300;1,400;1,600;1,700;1,800&display=swap");
@import url("https://fonts.googleapis.com/css2?family=Open+Sans+Condensed:ital,wght@0,300;0,700;1,300&display=swap");

/* Reset CSS */
* {
  margin: 0;
  padding: 0;
}

body {
  line-height: 1;
  font-size: 100%;
  font-family: "Open Sans", sans-serif;
  color: #5a5a5a;
}

#container {
  width: 980px;
  margin: 0 auto;
  box-shadow: 0 0 1em #cccccc;
}

/* header */
header {
  padding: 20px;
}

header h1 {
  margin: 20px 10px;
  color: #b5b5b5;
}
```

**Hasil setelah CSS dasar diterapkan:**

![Screenshot 6 - Header Layout](screenshots/06-header-layout.png)

---

## 7. Membuat Navigasi

Tambahkan CSS navigasi:

```css
/* navigasi */
nav {
  display: block;
  background-color: #1f5faa;
}

nav a {
  padding: 15px 30px;
  display: inline-block;
  color: #ffffff;
  font-size: 14px;
  text-decoration: none;
  font-weight: bold;
}

nav a.active,
nav a:hover {
  background-color: #2b83ea;
}
```

**Hasil navigasi:**

![Screenshot 7 - Navigasi](screenshots/07-navigasi.png)

---

## 8. Membuat Hero Panel

Isi section `#hero` di HTML:

```html
<section id="hero">
  <h1>Hello World!</h1>
  <p>
    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vestibulum lorem
    elit, iaculis innisi volutpat, malesuada tincidunt arcu. Proin in leo
    fringilla, vestibulum mi porta, faucibus felis. Integer pharetra est nunc,
    nec pretium nunc pretium ac.
  </p>
  <a href="home.html" class="btn btn-large">Learn more &raquo;</a>
</section>
```

Tambahkan CSS:

```css
/* Hero Panel */
#hero {
  background-color: #e4e4e5;
  padding: 50px 20px;
  margin-bottom: 20px;
}

#hero h1 {
  margin-bottom: 20px;
  font-size: 35px;
}

#hero p {
  margin-bottom: 20px;
  font-size: 18px;
  line-height: 25px;
}
```

**Hasil Hero Panel:**

![Screenshot 8 - Hero Panel](screenshots/08-hero-panel.png)

---

## 9. Mengatur Layout Main dan Sidebar

Tambahkan CSS float untuk main content dan sidebar:

```css
/* main content */
#wrapper {
  margin: 0;
}

#main {
  float: left;
  width: 640px;
  padding: 20px;
}

/* sidebar area */
#sidebar {
  float: left;
  width: 260px;
  padding: 20px;
}
```

---

## 10. Membuat Sidebar Widget

Isi `<aside id="sidebar">` dengan widget:

```html
<aside id="sidebar">
  <div class="widget-box">
    <h3 class="title">Widget Header</h3>
    <ul>
      <li><a href="#">Widget Link</a></li>
      <li><a href="#">Widget Link</a></li>
      <li><a href="#">Widget Link</a></li>
      <li><a href="#">Widget Link</a></li>
      <li><a href="#">Widget Link</a></li>
    </ul>
  </div>
  <div class="widget-box">
    <h3 class="title">Widget Text</h3>
    <p>
      Vestibulum lorem elit, iaculis in nisl volutpat, malesuada tincidunt arcu.
      Proin in leo fringilla, vestibulum mi porta, faucibus felis. Integer
      pharetra est nunc, nec pretium nunc pretium ac.
    </p>
  </div>
</aside>
```

Tambahkan CSS widget:

```css
/* widget */
.widget-box {
  border: 1px solid #eee;
  margin-bottom: 20px;
}

.widget-box .title {
  padding: 10px 16px;
  background-color: #428bca;
  color: #fff;
}

.widget-box ul {
  list-style-type: none;
}

.widget-box li {
  border-bottom: 1px solid #eee;
}

.widget-box li a {
  padding: 10px 16px;
  color: #333;
  display: block;
  text-decoration: none;
}

.widget-box li:hover a {
  background-color: #eee;
}

.widget-box p {
  padding: 15px;
  line-height: 25px;
}
```

**Hasil Sidebar Widget:**

![Screenshot 9 - Sidebar Widget](screenshots/09-sidebar-widget.png)

---

## 11. Mengatur Footer

Tambahkan CSS footer:

```css
/* footer */
footer {
  clear: both;
  background-color: #1d1d1d;
  padding: 20px;
  color: #eee;
}
```

Property `clear: both` sangat penting agar footer tidak naik ke samping elemen yang di-float.

**Hasil Footer:**

![Screenshot 10 - Footer](screenshots/10-footer.png)

---

## 12. Menambahkan Elemen Box pada Main Content

Isi section `#main` dengan tiga box (menggunakan float):

```html
<section id="main">
  <div class="row">
    <div class="box">
      <img
        src="https://dummyimage.com/120/db7d25/fff.png"
        alt=""
        class="image-circle"
      />
      <h3>Heading</h3>
      <p>Donec sed odio dui. Etiam porta sem malesuada magna mollis euismod.</p>
      <a href="#" class="btn btn-default">View detail</a>
    </div>
    <div class="box">
      <img
        src="https://dummyimage.com/120/3e73e6/fff.png"
        alt=""
        class="image-circle"
      />
      <h3>Heading</h3>
      <p>Donec sed odio dui. Etiam porta sem malesuada magna mollis euismod.</p>
      <a href="#" class="btn btn-default">View detail</a>
    </div>
    <div class="box">
      <img
        src="https://dummyimage.com/120/71e6d4/fff.png"
        alt=""
        class="image-circle"
      />
      <h3>Heading</h3>
      <p>Donec sed odio dui. Etiam porta sem malesuada magna mollis euismod.</p>
      <a href="#" class="btn btn-default">View detail</a>
    </div>
  </div>
</section>
```

Tambahkan CSS:

```css
/* box */
.box {
  display: block;
  float: left;
  width: 33.333333%;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  padding: 0 10px;
  text-align: center;
}

.box h3 {
  margin: 15px 0;
}

.box p {
  line-height: 20px;
  font-size: 14px;
  margin-bottom: 15px;
}

.box img {
  border: 0;
  vertical-align: middle;
}

.image-circle {
  border-radius: 50%;
}

.row {
  margin: 0 -10px;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
}

.row:after,
.row:before,
.entry:after,
.entry:before {
  content: "";
  display: table;
}

.row:after,
.entry:after {
  clear: both;
}
```

**Hasil tiga box di main content:**

![Screenshot 11 - Content Box](screenshots/11-content-box.png)

---

## 13. Menambahkan Content Artikel

Tambahkan dua artikel di bawah row box:

```html
<hr class="divider" />
<article class="entry">
  <h2>First featurette heading.</h2>
  <img src="https://dummyimage.com/150/7b8a70/fff.png" alt="" />
  <p>
    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vestibulum lorem
    elit, iaculis in nisl volutpat, malesuada tincidunt arcu. Proin in leo
    fringilla, vestibulum mi porta, faucibus felis. Integer pharetra est nunc,
    nec pretium nunc pretium ac.
  </p>
</article>

<hr class="divider" />
<article class="entry">
  <h2>First featurette heading.</h2>
  <img
    src="https://dummyimage.com/150/7b8a70/fff.png"
    alt=""
    class="right-img"
  />
  <p>
    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vestibulum lorem
    elit, iaculis in nisl volutpat, malesuada tincidunt arcu. Proin in leo
    fringilla, vestibulum mi porta, faucibus felis. Integer pharetra est nunc,
    nec pretium nunc pretium ac.
  </p>
</article>
```

CSS untuk artikel:

```css
.divider {
  border: 0;
  border-top: 1px solid #eeeeee;
  margin: 40px 0;
}

/* entry */
.entry {
  margin: 15px 0;
}

.entry h2 {
  margin-bottom: 20px;
}

.entry p {
  line-height: 25px;
}

.entry img {
  float: left;
  border-radius: 5px;
  margin-right: 15px;
}

.entry .right-img {
  float: right;
}
```

**Hasil tampilan artikel:**

![Screenshot 12 - Content Artikel](screenshots/12-content-artikel.png)

---

## 14. Tugas 1 – Halaman About (Single Layout)

Buat file `about.html`. Gunakan struktur yang sama, tetapi section `#main` dibuat full-width (single layout).

Tambahkan class `single-layout` pada `#main` dan isi konten deskripsi + portfolio:

```html
<section id="main" class="single-layout">
  <div class="about-section">
    <h2>Deskripsi Perusahaan</h2>
    <p>...</p>
  </div>

  <hr class="divider" />

  <div class="about-section">
    <h2>Portfolio Kami</h2>
    <div class="row">
      <!-- 3 box portfolio -->
    </div>
  </div>
</section>
```

CSS tambahan:

```css
/* Membuat main content jadi full width (single layout) */
#main.single-layout {
  width: 100%;
  float: none;
  box-sizing: border-box;
}

.about-section {
  margin-bottom: 40px;
}

.about-section h2 {
  margin-bottom: 20px;
  color: #1f5faa;
}
```

**Hasil halaman About:**

![Screenshot 13 - Halaman About](screenshots/13-about.png)

---

## 15. Tugas 2 – Halaman Contact (Form)

Buat file `kontak.html`. Isi section main dengan form:

```html
<section id="main">
  <h2>Formulir Kontak</h2>
  <form action="#" method="post" class="contact-form">
    <div class="form-group">
      <label for="nama">Nama Lengkap</label>
      <input
        type="text"
        id="nama"
        name="nama"
        placeholder="Masukkan nama Anda"
        required
      />
    </div>
    <div class="form-group">
      <label for="email">Alamat Email</label>
      <input
        type="email"
        id="email"
        name="email"
        placeholder="Masukkan email aktif Anda"
        required
      />
    </div>
    <div class="form-group">
      <label for="subjek">Subjek</label>
      <input
        type="text"
        id="subjek"
        name="subjek"
        placeholder="Judul pesan Anda"
      />
    </div>
    <div class="form-group">
      <label for="pesan">Pesan</label>
      <textarea
        id="pesan"
        name="pesan"
        rows="5"
        placeholder="Tulis pesan atau pertanyaan Anda di sini..."
        required
      ></textarea>
    </div>
    <button type="submit" class="btn-submit">Kirim Pesan</button>
  </form>
</section>
```

CSS form:

```css
/* Styling Kontak (Form) */
.contact-form {
  margin-top: 20px;
}

.form-group {
  margin-bottom: 20px;
}

.form-group label {
  display: block;
  margin-bottom: 8px;
  font-weight: bold;
  color: #333;
}

.form-group input,
.form-group textarea {
  width: 100%;
  padding: 12px;
  border: 1px solid #ccc;
  border-radius: 4px;
  box-sizing: border-box;
  font-family: "Open Sans", sans-serif;
  font-size: 14px;
  transition: border-color 0.3s;
}

.form-group input:focus,
.form-group textarea:focus {
  border-color: #1f5faa;
  outline: none;
  box-shadow: 0 0 5px rgba(31, 95, 170, 0.3);
}

.btn-submit {
  background-color: #1f5faa;
  color: white;
  padding: 12px 25px;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  font-size: 14px;
  font-weight: bold;
  font-family: "Open Sans", sans-serif;
}

.btn-submit:hover {
  background-color: #2b83ea;
}
```

**Hasil halaman Contact:**

![Screenshot 14 - Halaman Contact](screenshots/14-contact.png)

---
