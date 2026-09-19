Profile Card: Study Case Git & GitHub Workshop

Website sederhana berisi kartu profil interaktif untuk tiga anggota tim. Pengguna bisa berpindah antar anggota, memberi like, dan mengganti tema terang/gelap tanpa reload halaman. Project ini dibuat sebagai study case kolaborasi menggunakan Git & GitHub (branch, commit, merge) dengan pembagian kerja per file.

 Visualisasi 
 Tampilan

| Light Mode | Dark Mode |
| :---: | :---: |
| ![Light Mode](./screenshots/light-mode.png) | ![Dark Mode](./screenshots/dark-mode.png) |

 Tech stack

| Teknologi | Kegunaan |
| --- | --- |
| HTML5 | Struktur halaman (semantic tag: `header`, `nav`, `main`, `section`, `footer`) |
| CSS3 | Styling, CSS Variables, Flexbox, `backdrop-filter` (glassmorphism), media query |
| JavaScript (Vanilla) | Manipulasi DOM, event handling, render data secara dinamis |
| Git & GitHub | Version control dan kolaborasi tim lewat branch |

 Struktur folder
 index.html   → kerangka halaman
 style.css    → seluruh styling + dark mode + responsive
 script.js    → data anggota, render, like counter, toggle tema
 README.md
```

 Cara menjalankan

1. Clone repository ini
   ```bash
   git clone <url-repository>
   ```
2. Buka file `index.html` langsung di browser. Tidak perlu server.

 Fitur utama

- Kartu profil berubah saat tombol Anggota 1, 2, atau 3 di navbar diklik. Nama, role, foto, deskripsi, dan daftar skill ikut berganti tanpa reload.
- Setiap anggota punya hitungan like sendiri yang bertahan selama halaman terbuka.
- Tombol toggle mengganti tema terang dan gelap, lengkap dengan label dan ikon tombolnya (🌙 / ☀️).
- Layout menyesuaikan ukuran layar, dengan breakpoint khusus untuk layar ≤ 600px.
- Kartu dibuat semi-transparan dengan efek blur, latar gradient, dan animasi hover (glassmorphism).
- Aksesibilitas dasar: `aria-label` pada navigasi, `aria-pressed` pada tombol anggota aktif, dan `alt` foto yang ikut berubah sesuai anggota.

 Contribution
Christian A: Project Initiator (`index.html`) 
Kelvin Orlando: JavaScript Engineer & Styling Engineer

Alur kerja Git yang dipakai: setiap peran mengerjakan file miliknya di branch terpisah (`styling`, `scripting`), lalu di-merge ke `main`.

 What I learned

- Memisahkan pekerjaan ke beberapa branch mencegah file saling menimpa, lalu hasilnya digabung lewat merge. Komentar `TODO` di `index.html` menunjukkan ke setiap anggota bagian mana yang harus ditambahkan.
- HTML, CSS, dan JavaScript dipisah ke file masing-masing: HTML untuk struktur, CSS untuk tampilan, JavaScript untuk perilaku.
- Manipulasi DOM memakai `querySelector`, `getElementById`, `textContent`, `classList.toggle`, `dataset`, dan `addEventListener`.
- Satu array `members` menjadi sumber data untuk mengubah seluruh isi kartu.
- Array `likeCounts` dan variabel `activeMember` menyimpan hitungan like per anggota.
- Tema memakai CSS Variables dan class `dark-mode` pada `body`. Ukuran fleksibel memakai `clamp()`, dan tampilan responsif memakai media query.
- Dua hal masih kurang rapi. Data anggota pertama tertulis dua kali (di HTML dan di JS), dan `counterSpan` dideklarasikan setelah fungsi yang memakainya. Kode berjalan normal, tapi rawan error kalau diubah.

 Feature improvement

Simpan jumlah like dan pilihan tema dengan `localStorage`, karena keduanya hilang setiap halaman di-refresh.
Deteksi `prefers-color-scheme` untuk menentukan tema awal.
Ubah tombol like menjadi like/unlike, karena sekarang bisa ditekan tanpa batas.
Panggil `renderMember(0)` saat halaman dimuat dan kosongkan isi awal di HTML, supaya data hanya punya satu sumber.
Pindahkan data anggota ke file JSON, sehingga menambah anggota tidak perlu mengubah kode dan tombol navbar dibuat otomatis.
Tambahkan `onerror` pada avatar agar ada foto default jika link gambar mati.
Tambahkan link GitHub, LinkedIn, atau email di tiap kartu.
Tambahkan animasi transisi (fade atau slide) saat berpindah anggota.
Tambahkan `aria-live` pada counter dan style `:focus-visible` untuk navigasi keyboard.
Deploy ke GitHub Pages agar bisa diakses lewat link publik.
Ganti placeholder "Nama Anggota 1/2/3" dan foto sementara dengan data tim yang sebenarnya.
