Data Diri
Nama : Simon Dimas Pramudya
NIM : H1D023104
Shift Lama : G
Shift Baru : D

1. main.dart

File utama aplikasi yang pertama kali dijalankan.

Berisi:

Inisialisasi aplikasi Flutter (runApp)
Konfigurasi MaterialApp
Menentukan halaman awal aplikasi melalui home:
Routing dasar sesuai modul, contoh:

- RegistrasiPage()
- LoginPage()
- ProdukPage()

Fungsinya sebagai pusat konfigurasi awal aplikasi.

Folder model/

Folder ini berisi class–class model yang digunakan untuk menampung data dari API/Backend (JSON → Dart Object).

2. model/login.dart

Model data untuk response login.

Field umum:

- code
- status
- token
- userID
- userEmail

Disertai:

Login.fromJson() → mempermudah parsing JSON dari API.

3. model/produk.dart

Model data untuk entitas produk.
Memuat field:

- id
- kodeProduk
- namaProduk
- hargaProduk

Digunakan untuk mengirim atau menerima data produk di aplikasi.
Folder ui/
Berisi seluruh halaman (screens) aplikasi.

4. ui/login_page.dart

Halaman login untuk pengguna.
Fitur:

- Input username/email dan password
- Validasi input
- Menyimpan username ke SharedPreferences
- Navigasi ke halaman produk setelah login berhasil
- Tombol menuju halaman registrasi
- Fungsinya sebagai gerbang autentikasi user.

5. ui/registrasi_page.dart

Halaman pendaftaran akun baru.
Memuat:

Form:

- Nama
- Email
- Password
- Konfirmasi password

Validasi:

- Input wajib diisi
- Password harus sama
- Tombol “Daftar” untuk simpan atau kirim ke API
- Navigasi otomatis ke halaman login
- Fungsinya untuk membuat akun sebelum user melakukan login.

6. ui/produk_page.dart

Halaman beranda setelah login, menampilkan daftar produk.

Berisi:

- AppBar dengan tombol tambah produk
- Drawer dengan tombol Logout (hapus session dari SharedPreferences)
- List produk dalam bentuk card atau tile
- Navigasi ke halaman detail produk ketika item dipilih
- Fungsinya sebagai pusat aktivitas utama pengguna.

7. ui/produk_form.dart

Halaman untuk menambahkan produk baru.

Memuat:

Input:

- Kode produk
- Nama produk
- Harga produk
- Tombol “Simpan”

Menghasilkan objek Produk baru lalu kembali ke halaman produk
Digunakan untuk operasi Create pada fitur CRUD Produk.

8. ui/produk_detail.dart

Halaman untuk menampilkan detail produk.

Berisi:

- Informasi lengkap produk (nama, harga, kode, id)
- Tombol Edit atau Hapus (opsional, sesuai modul)
- Fungsinya sebagai detail view dari setiap item produk.