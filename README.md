# 📚 APK Perpustakaan Digital

**Aplikasi Pengelolaan Perpustakaan Digital**

Sistem informasi perpustakaan untuk membantu pengelolaan buku, anggota, dan peminjaman secara terstruktur.

![Python](https://img.shields.io/badge/Python-3.12-blue?logo=python)
![MySQL](https://img.shields.io/badge/Database-MySQL-orange?logo=mysql)
![Tkinter](https://img.shields.io/badge/Interface-Tkinter-blue)
![Development](https://img.shields.io/badge/Status-Development-yellow)

## 📖 Tentang Proyek

**APK Perpustakaan Digital** merupakan aplikasi desktop yang dikembangkan untuk membantu proses pengelolaan perpustakaan, mulai dari pengelolaan data buku, data anggota, hingga proses peminjaman dan pengembalian buku.

Aplikasi ini memiliki sistem hak akses pengguna sehingga setiap pengguna dapat menjalankan fungsi sesuai dengan perannya masing-masing.

## ✨ Fitur Utama

- 🔐 **Login System** — Autentikasi pengguna berdasarkan hak akses.
- 📚 **Manajemen Buku** — Pengelolaan data dan informasi koleksi buku.
- 👥 **Manajemen Anggota** — Pengelolaan data anggota perpustakaan.
- 📋 **Peminjaman Buku** — Pengelolaan proses peminjaman buku.
- 📊 **Riwayat Peminjaman** — Melihat informasi riwayat peminjaman.

## 👤 Hak Akses Pengguna

Aplikasi memiliki tiga jenis pengguna dengan hak akses yang berbeda.

| Pengguna     | Hak Akses                                                                                               |
| ------------ | ------------------------------------------------------------------------------------------------------- |
| **Operator** | Mengelola data buku, petugas, dan anggota, serta melihat transaksi peminjaman dan laporan.              |
| **Petugas**  | Mengelola anggota, peminjaman, detail peminjaman, dan laporan serta melihat data petugas dan buku.      |
| **Anggota**  | Melihat katalog buku, detail buku, dan riwayat peminjaman.                                              |

## 🛠️ Teknologi yang Digunakan

| Teknologi          | Kegunaan                            |
| ------------------ | ----------------------------------- |
| Python             | Bahasa pemrograman utama            |
| Tkinter            | Pembuatan antarmuka aplikasi        |
| MySQL              | Pengelolaan basis data              |
| MySQL Connector    | Penghubung aplikasi dengan database |
| Visual Studio Code | Lingkungan pengembangan             |

## 🖥️ Preview Aplikasi

Dokumentasi tampilan aplikasi akan ditampilkan pada bagian ini.

### Halaman Login

👤 Halaman Login Operator
<img width="748" height="510" alt="operator-login" src="https://github.com/user-attachments/assets/1840c895-9559-4d9f-870a-af57ede4e4ae" />

👤 Halaman Login Petugas
<img width="748" height="507" alt="halama-login-petugas" src="https://github.com/user-attachments/assets/c0425f4f-ee2a-4607-81fb-a51bfc30d64b" />

👤 Halaman Login Anggota
<img width="745" height="509" alt="anggota-login-1" src="https://github.com/user-attachments/assets/1bf6b694-06be-44ab-8e20-66b23e257f83" />

### Dashboard Operator

<img width="1920" height="1080" alt="operator-dashboard" src="https://github.com/user-attachments/assets/e7727ef2-fd82-43b4-83e4-1fd3beb9b23c" />

### Dashboard Petugas

<img width="1920" height="1080" alt="petugas-dashboard" src="https://github.com/user-attachments/assets/b6cf0528-e6cd-48e4-b41d-8574a41f8900" />

### Dashboard Anggota

<img width="1920" height="1080" alt="Screenshot (474)" src="https://github.com/user-attachments/assets/de340d53-f0d1-472f-816b-5c1e87246132" />

## 📦 Build & Distribusi Aplikasi

Aplikasi dapat dikemas menjadi file `.exe` menggunakan PyInstaller dan dibuat menjadi installer Windows menggunakan Inno Setup.

### 1. Persiapan File

Pastikan file berikut tersedia di folder utama proyek:

- `.env` — Konfigurasi lingkungan aplikasi yang disimpan secara lokal.
- `Perpustakaan.spec` — Konfigurasi proses build PyInstaller.
- `Perpustakaan_Petugas.iss` — Script installer untuk petugas dan operator.
- `Perpustakaan_Anggota.iss` — Script installer untuk anggota.

**Catatan:** File `.env` yang berisi kredensial database jangan diunggah ke repository publik. Gunakan `.env.example` sebagai contoh konfigurasi.

### 2. Build Aplikasi dengan PyInstaller

Buka terminal di folder utama proyek, kemudian jalankan perintah berikut:

```bash
pyinstaller Perpustakaan.spec --clean --noconfirm
```

Setelah proses build selesai, hasil aplikasi akan tersedia di folder:

```text
dist/
└── Perpustakaan/
```

### 3. Instalasi Inno Setup

Unduh dan instal **Inno Setup** melalui situs resminya:

[https://jrsoftware.org/isinfo.php](https://jrsoftware.org/isinfo.php)

Inno Setup digunakan untuk mengemas aplikasi menjadi installer Windows.

### 4. Membuat Installer Petugas

1. Buka file `Perpustakaan_Petugas.iss` menggunakan Inno Setup.
2. Klik menu **Compile** atau tekan `Ctrl + F9`.
3. Tunggu hingga proses kompilasi selesai.

### 5. Membuat Installer Anggota

1. Buka file `Perpustakaan_Anggota.iss`.
2. Klik **Compile** atau tekan `Ctrl + F9`.
3. Tunggu hingga proses kompilasi selesai.

### 6. Hasil Build Installer

Setelah kedua proses kompilasi berhasil, file installer akan tersedia di folder `installer/`.

```text
installer/
├── Setup_Perpustakaan_Petugas.exe
└── Setup_Perpustakaan_Anggota.exe
```

### 7. Pengujian dan Distribusi

Sebelum dibagikan, lakukan pengujian installer pada komputer Windows lain yang belum memiliki Python untuk memastikan aplikasi dapat berjalan dengan baik.

Pembagian installer dilakukan berdasarkan hak akses pengguna:

| Installer                        | Pengguna             |
| -------------------------------- | -------------------- |
| `Setup_Perpustakaan_Petugas.exe` | Petugas dan Operator |
| `Setup_Perpustakaan_Anggota.exe` | Anggota              |

**Catatan:** Pastikan konfigurasi koneksi database tersedia dan server MySQL dapat diakses oleh komputer pengguna. Installer aplikasi tidak otomatis menyediakan server database MySQL.

## 🎯 Tujuan Pengembangan

Pengembangan aplikasi ini bertujuan untuk menerapkan konsep pemrograman berorientasi objek, pengelolaan basis data, serta sistem informasi dalam membangun aplikasi perpustakaan berbasis desktop.

---

<p align="center">
  <strong>APK Perpustakaan Digital</strong>
  <br>
  Developed with ❤️ using Python
</p>
