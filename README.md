# Lab4Web — Praktikum 4: CSS Layout

Praktikum Pemrograman Web — CSS Layout: Box Element, CSS Float/Clear, HTML5 Semantics, dan Layout Web Sederhana.

## Identitas

| | |
|---|---|
| Nama | Alvin Al Aziz |
| NIM | 312510044 |
| Kelas |I252A |
| Mata Kuliah | Pemrograman Web |

## Struktur Folder

```text
Lab4Web/
  README.md
  lab4_box.html
  lab4_layout/
    home.html
    about.html      (tugas)
    kontak.html     (tugas)
    style.css
```

## Bagian A — `lab4_box.html`: Box + Float + Clearfix

### 1. Dokumen dasar

Buat `lab4_box.html`:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Box Element</title>
</head>
<body>
  <header>
    <h1>Box Element</h1>
  </header>
</body>
</html>
```
 2. Box Element

Tambahkan setelah `</header>`:

```html
<section>
  <div class="div1">Div 1</div>
  <div class="div2">Div 2</div>
  <div class="div3">Div 3</div>
</section>
```

Tanpa CSS, ketiga div menumpuk vertikal full-width.

### 3. CSS Float

Tambahkan di `<head>`:

```html
<style>
  div { float: left; padding: 10px; }
  .div1 { background: red; }
  .div2 { background: yellow; }
  .div3 { background: green; }
</style>
```

- `float: left` → ketiga box sejajar horizontal.
- `padding: 10px` → jarak dalam tiap box.

  <img width="689" height="346" alt="image" src="https://github.com/user-attachments/assets/0b2cafd4-d928-4307-8606-3478d812b32b" />

### 4. Clearfix

Tambahkan `div4`:

```html
<div class="div4">Div 4</div>
```

```css
.div4 {
  background-color: blue;
  clear: left;
  float: none;
}
```

- `clear: left` → Div 4 turun ke baris baru, tidak nempel float sebelumnya.
- Eksperimen: coba `left` / `right` / `both`, catat perbedaannya di laporan DOCX.

<img width="883" height="241" alt="image" src="https://github.com/user-attachments/assets/abd36848-c8b7-4cbd-8e2e-b8ad678f540d" />

## Bagian B — `lab4_layout`: Layout Sederhana

Target akhir: header → nav biru → hero abu-abu → 3 box lingkaran + sidebar widget → 2 artikel → footer hitam.

### 5. File awal

`lab4_layout/home.html`:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Layout Sederhana</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <div id="container">
  </div>
</body>
</html>
```

### 6. Kerangka semantics

Isi `#container` dengan:

```html
<header><h1>Layout Sederhana</h1></header>
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
<footer><p>&copy; 2021 - Universitas Pelita Bangsa</p></footer>
```

<img width="878" height="352" alt="image" src="https://github.com/user-attachments/assets/579ac0a1-218d-49e0-af83-f5608a38f382" />

### 7. CSS dasar

`style.css` tahap 1 — font, reset, container, header:

```css
@import url('https://fonts.googleapis.com/css2?family=Open+Sans:ital,wght@0,300;0,400;0,600;0,700;0,800;1,300;1,400;1,600;1,700;1,800&display=swap');
* { margin: 0; padding: 0; }
body { line-height: 1; font-size: 100%; font-family: 'Open Sans', sans-serif; color: #5a5a5a; }
#container { width: 980px; margin: 0 auto; box-shadow: 0 0 1em #cccccc; }
header { padding: 20px; }
header h1 { margin: 20px 10px; color: #b5b5b5; }
```
<img width="906" height="344" alt="image" src="https://github.com/user-attachments/assets/a7736acc-064c-4908-9607-b81341b1b667" />

### 8. Navigasi

```css
nav { display: block; background-color: #1f5faa; }
nav a { padding: 15px 30px; display: inline-block; color: #fff; font-size: 14px; text-decoration: none; font-weight: bold; }
nav a.active, nav a:hover { background-color: #2b83ea; }
```

<img width="909" height="455" alt="image" src="https://github.com/user-attachments/assets/98da61aa-af7f-461e-be21-66ba5bd0af7c" />

### 9. Hero Panel

```html
<section id="hero">
  <h1>Hello World!</h1>
  <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. ...</p>
  <a href="home.html" class="btn btn-large">Learn more &raquo;</a>
</section>
```

```css
#hero { background-color: #e4e4e5; padding: 50px 20px; margin-bottom: 20px; }
#hero h1 { margin-bottom: 20px; font-size: 35px; }
#hero p { margin-bottom: 20px; font-size: 18px; line-height: 25px; }
```

<img width="945" height="527" alt="image" src="https://github.com/user-attachments/assets/de8e334f-cc01-4e17-9d4e-fef19d56e05a" />

### 10. Main + Sidebar

```css
#wrapper { margin: 0; }
#main { float: left; width: 640px; padding: 20px; }
#sidebar { float: left; width: 260px; padding: 20px; }
```

### 11. Sidebar Widget

Lihat kode lengkap di laporan DOCX bagian 5.7. Intinya: `.widget-box` border `#eee`, judul biru `#428bca`, link hover abu-abu.

<img width="945" height="647" alt="image" src="https://github.com/user-attachments/assets/818b5971-8cc2-4bb0-8b14-01102ed6f42c" />

### 12. Footer

```css
footer { clear: both; background-color: #1d1d1d; padding: 20px; color: #eee; }
```

<img width="945" height="672" alt="image" src="https://github.com/user-attachments/assets/b6cb5486-08da-4e4c-bd3d-fbdd55f1b642" />

### 13. Box 3 kolom di Main

- `.box { float: left; width: 33.333333%; box-sizing: border-box; text-align: center; }`
- `.image-circle { border-radius: 50%; }`
- `.row:after { clear: both; }` sebagai clearfix.

<img width="945" height="494" alt="image" src="https://github.com/user-attachments/assets/00a81dce-d93d-48ae-bbef-c3acba246968" />

### 14. Artikel

```css
.divider { border: 0; border-top: 1px solid #eeeeee; margin: 40px 0; }
.entry img { float: left; border-radius: 5px; margin-right: 15px; }
.entry .right-img { float: right; }
```

<img width="945" height="749" alt="image" src="https://github.com/user-attachments/assets/56e2b3b9-83d0-4fc8-86df-a2f0e5e93aaf" />

## Tugas

### About (`about.html`)

Copy `home.html` → `about.html`, pindahkan `class="active"` ke link About. Isi `#main` dengan deskripsi + portfolio (reuse `.row` / `.box`).

<img width="945" height="606" alt="image" src="https://github.com/user-attachments/assets/9bb9584d-08d8-4cb5-8e89-34e523f7dead" />

### Kontak (`kontak.html`)

Copy `home.html` → `kontak.html`, `class="active"` ke link Kontak. Isi `#main` dengan form nama, email, message.

<img width="945" height="731" alt="image" src="https://github.com/user-attachments/assets/52d1cb13-7f7c-416d-b1fb-b615f436652a" />
