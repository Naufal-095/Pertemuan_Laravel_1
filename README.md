Nama:Muhammad Naufal Dwiantomo
NPM:4523210076
# Pertemuan_Laravel_1
## Bagian 1: Teori Singkat (5 Menit)
Sebelum kita mengetik kode, mari pahami tiga alat utama yang akan kita gunakan hari ini:
Laravel: Framework PHP yang akan menjadi "kerangka rumah" untuk aplikasi kita. Ia menyediakan banyak alat siap pakai agar kita bisa membangun aplikasi dengan cepat dan terstruktur.
Composer: "Manajer Paket" untuk PHP. Tugasnya adalah mengunduh Laravel dan semua "pustaka" (library) lain yang dibutuhkan oleh Laravel agar bisa berjalan.
Artisan: "Asisten pribadi" atau pisau Swiss Army bawaan Laravel. Ini adalah alat baris perintah (command-line tool) yang akan kita gunakan untuk banyak hal, salah satunya adalah untuk menyalakan server development lokal (php artisan serve).

### Bagian 2: Langkah-Langkah Praktikum (75 Menit)

Langkah 1: Instalasi Proyek Laravel "LaraPress"
Buka Terminal: Jalankan terminal Kita. Jika menggunakan Laragon, cara termudah adalah klik tombol "Terminal" di jendela Laragon. Ini akan membuka terminal di direktori yang tepat.
Navigasi ke Direktori Web: Pastikan Kita berada di dalam document root server lokal Kita. Untuk Laragon, itu adalah C:\laragon\www. Untuk XAMPP, C:\xampp\htdocs.
Jalankan Perintah Instalasi: Ketik perintah berikut dan tekan Enter. Perintah ini akan menyuruh Composer untuk membuat proyek Laravel baru di dalam folder bernama LaraPress.
composer create-project laravel/laravel LaraPress
Proses ini akan memakan waktu beberapa menit karena Composer perlu mengunduh semua paket yang dibutuhkan. Pastikan koneksi internet Kita stabil.

Langkah 2: Menjalankan Aplikasi untuk Pertama Kali
Masuk ke Folder Proyek: Setelah instalasi selesai, masuk ke direktori proyek yang baru dibuat.
cd LaraPress

Jalankan Server Artisan: Gunakan Artisan untuk menyalakan server development bawaan Laravel.
php artisan serve

Lihat Hasilnya: Terminal akan menampilkan alamat server lokal Kita, biasanya seperti ini: Server running on [http://127.0.0.1:8000].
Buka web browser Kita, lalu kunjungi alamat http://127.0.0.1:8000. Kita akan disambut dengan halaman selamat datang Laravel. Selamat, aplikasi Laravel pertama Kita sudah berjalan!

Langkah 3: Memahami Alur Kerja Pertama (Route -> View)
Sekarang kita akan memodifikasi halaman selamat datang tersebut. Ini akan mengajarkan kita alur kerja paling dasar di Laravel.
Buka Proyek di Code Editor: Buka seluruh folder LaraPress menggunakan VS Code atau editor pilihan Kita.
Pahami Rute (The Map): Buka file routes/web.php. File ini adalah "peta" atau "daftar alamat" untuk aplikasi web kita. Kita akan melihat kode ini:
use Illuminate\Support\Facades\Route;

Route::get('/', function () {
    return view('welcome');
});

Artinya: "Ketika seseorang mengunjungi URL utama (/) menggunakan metode GET, carilah dan tampilkan file view yang bernama welcome."
Modifikasi Tampilan (The View):
Sekarang, buka file view tersebut di resources/views/welcome.blade.php.
Kita akan melihat banyak kode HTML. Untuk latihan, hapus semua isinya dan ganti dengan kode sederhana ini:
<!DOCTYPE html>
<html>
<head>
    <title>Selamat Datang di LaraPress</title>
</head>
<body>
    <h1>Selamat Datang di Blog LaraPress</h1>
    <p>Ini adalah halaman utama dari aplikasi blog kita.</p>
</body>
</html>

Simpan & Refresh: Simpan file welcome.blade.php tersebut. Kembali ke browser Kita dan refresh halaman http://127.0.0.1:8000. Tampilan halaman sekarang seharusnya sudah berubah sesuai dengan kode HTML yang baru Kita tulis.
Langkah 4: Membuat Halaman Statis Baru ("Tentang Kami")
Sekarang kita akan menerapkan apa yang baru saja kita pelajari untuk membuat halaman baru dari nol.
Buat Rute Baru:
Kembali ke file routes/web.php.
Di bawah rute yang sudah ada, tambahkan rute baru untuk halaman "Tentang Kami".
Route::get('/tentang-kami', function () {
    return view('about'); // Kita akan menampilkan view bernama 'about'
});

Buat File View Baru:
Di dalam folder resources/views/, buat sebuah file baru bernama about.blade.php.
Isi file tersebut dengan konten HTML sederhana:
<!DOCTYPE html>
<html>
<head>
    <title>Tentang Kami - LaraPress</title>
</head>
<body>
    <h1>Tentang LaraPress</h1>
    <p>LaraPress adalah sebuah proyek blog sederhana yang dibuat untuk mempelajari dasar-dasar framework Laravel 12.</p>
</body>
</html>

Uji Coba Halaman Baru: Simpan semua file. Buka browser Kita dan kunjungi URL baru: http://127.0.0.1:8000/tentang-kami. Halaman "Tentang Kami" seharusnya sudah muncul!
Menambahkan Link Navigasi:
Agar pengguna bisa berpindah halaman, tambahkan link di kedua file view Kita.
Di welcome.blade.php, tambahkan di bawah paragraf:
<a href="/tentang-kami">Lihat Halaman Tentang Kami</a>
Di about.blade.php, tambahkan di bawah paragraf:
<a href="/">Kembali ke Halaman Utama</a>
Simpan dan coba klik link tersebut di browser.

#### Bagian 3: Tugas Mandiri (10 Menit)
Untuk memastikan Kita memahami konsepnya, kerjakan tugas kecil berikut:
Buat satu halaman statis baru bernama "Kontak".
Halaman ini harus bisa diakses melalui URL /kontak.
Isi halaman tersebut dengan informasi kontak fiktif (misal: email dan nomor telepon).
Jangan lupa tambahkan link navigasi ke dan dari halaman "Kontak" di halaman lainnya.
VSCODE HOME
<img width="569" height="256" alt="Screenshot 2025-10-03 141039" src="https://github.com/user-attachments/assets/99a1c9b9-3f42-4026-a769-82b868497e54" />
VSCODE KONTAK
<img width="408" height="238" alt="Screenshot 2025-10-03 141050" src="https://github.com/user-attachments/assets/d752add3-4a4b-4645-b572-41b840b8eb0f" />
VSCODE routes web.php
<img width="621" height="268" alt="Screenshot 2025-10-03 141108" src="https://github.com/user-attachments/assets/8622ed1d-2a6f-4ae0-9a5a-63d85206cd6c" />


##### Bagian 4: Kesimpulan & Langkah Selanjutnya
Pada pertemuan ini, kita telah berhasil:
Menginstal proyek Laravel baru dari awal.
Menjalankan server development lokal.
Membuat halaman statis dengan mendefinisikan Route dan membuat file View.
