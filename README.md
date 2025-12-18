# MVC Laravel


## MVC
MVC (Model–View–Controller) adalah pola arsitektur yang digunakan Laravel untuk memisahkan bagian aplikasi menjadi tiga bagian utama:
- Model → bagian yang mengelola data & berhubungan dengan database.
- View → bagian tampilan (HTML/Blade) yang dilihat oleh pengguna.
- Controller → bagian yang menjembatani antara Model dan View, berisi logika aplikasi.


## Struktur MVC Laravel
```
app/
 ├── Models/
 │    └── Product.php                  <-- Model
 ├── Http/
 │    └── Controllers/
 │         └── ProductController.php   <-- Controller
resources/
 └── views/
      └── products/      
            └── index.blade.php        <-- View
routes/
 └── web.php                           <-- Route
```


## Model (Bagian Data)
Model adalah tempat:
- berinteraksi dengan database,
- menulis query (biasanya pakai Eloquent),
- menentukan tabel mana yang digunakan,
- mengatur kolom yang boleh diisi.


## View (Bagian Tampilan)
View adalah:
- file tampilan HTML/Blade,
- berfungsi menampilkan data yang diberikan dari controller.


## Controller (Bagian Logika)
Controller adalah:
- mengatur alur program,
- mengambil data dari Model,
- mengirim data ke View.


## Alur Kerja MVC
1. User membuka URL → misal /products.
2. Route mengarah ke Controller:
``
Route::get('/products', [ProductController::class, 'index']);
``
3. Controller memanggil Model untuk ambil data.
4. Controller mengirim data ke View.
5. View menampilkan hasil ke pengguna.


## Penjelasan Terminal
### Installasi
```
composer create-project laravel/Laravel Nama-Proyek
```
Perintah ini digunakan untuk membuat proyek Laravel baru menggunakan Composer. Mengunduh source code Laravel terbaru. Menginstall seluruh dependensi yang dibutuhkan. Membuat folder proyek Laravel siap pakai.

```
composer require laravel/breeze
```
Perintah ini digunakan untuk menginstall Laravel Breeze, yaitu paket starter kit sederhana untuk fitur:
- Login
- Register
- Logout
- Reset password
- Verifikasi email
- Dashboard dasar
Breeze menyediakan contoh implementasi otentikasi yang ringan dan mudah dipahami, cocok untuk pemula.

```
php artisan breeze:install
```
Perintah ini digunakan untuk menginstall scaffold (template) autentikasi Laravel Breeze ke dalam proyek Laravel.
Artinya, setelah menjalankan perintah ini, proyek akan otomatis memiliki:
- Halaman login
- Halaman register
- Halaman forgot password
- Halaman reset password
- Halaman email verification
- Layout dasar UI
- Route auth lengkap
- Controller auth
- View/komponen frontend
- Struktur folder siap pakai

### List
```
php artisan list
```
Perintah ini digunakan untuk menampilkan seluruh perintah Artisan yang tersedia di proyek Laravel.

### Membuat File
```
php artisan make:model NamaModel -m
```
Perintah ini digunakan untuk membuat sebuah Model baru di Laravel dan sekaligus membuat Migration untuk tabel database yang terkait dengan model tersebut.

```
php artisan make:controller NamaController --resource --model=Post
```
Perintah ini membuat sebuah Controller bernama NamaController yang otomatis memiliki 7 method dasar CRUD:
- index()	Menampilkan semua data
- create()	Menampilkan form tambah data
- store()	Menyimpan data baru ke database
- show()	Menampilkan detail data
- edit()	Menampilkan form edit
- update()	Update data
- destroy()	Hapus data

Dan Controller langsung terhubung dengan Model.

```
php artisan make:component NamaComponent
```
Perintah ini digunakan untuk membuat Laravel Blade Component baru. Blade Component adalah komponen UI yang bisa digunakan berulang-ulang di dalam view Laravel.

```
php artisan make:request NamaFileRequest
```
Perintah ini digunakan untuk membuat Form Request, Form Request adalah class khusus yang digunakan untuk validsi request dan otorisasi request.

### Migrate
```
php artisan migrate
```
Perintah ini digunakan untuk menjalankan semua file migration yang belum dieksekusi, sehingga Laravel akan membuat tabel-tabel di database sesuai definisi migration yang ada di folder. Ini adalah cara Laravel membangun struktur database secara otomatis tanpa harus menulis query SQL manual.

```
php artisan migrate:rollback --step=1
```
Perintah ini digunakan untuk membatalkan (undo) 1 migration terakhir yang sudah dijalankan. Artinya, Laravel akan menjalankan fungsi down() dari migration terbaru, sehingga tabel atau perubahan yang dibuat sebelumnya akan dikembalikan.

```
php artisan migrate:fresh
```
Perintah ini digunakan untuk menghapus semua tabel di database, lalu menjalankan seluruh migration dari awal.

```
php artisan migrate:fresh --seed
```
Perintah ini digunakan untuk menghapus semua tabel di database, lalu menjalankan seluruh migration dari awal, kemudian mengisi kembali database dengan data awal (dummy data).

### Database
```
php artisan db:show
```
Perintah ini digunakan untuk menampilkan informasi database yang sedang dikonfigurasi di Laravel.

```
php artisan db:seed 
```
Perintah ini digunakan untuk mengisi database dengan data awal (dummy data / sample data) menggunakan Seeder yang sudah kamu buat di Laravel. Biasanya digunakan untuk:
- Mengisi data awal tabel (contoh: user admin, kategori, produk, dll)
- Testing
- Development
- Demo project


### Vendor
```
php artisan vendor:publish
```
Perintah ini digunakan untuk menyalin (publish) file konfigurasi, view, asset, atau resource lain dari vendor package ke folder aplikasi (config, resources, public, dll).


### Config
```
php artisan config:publish
```
Perintah ini digunakan untuk mempublish (menyalin) file konfigurasi bawaan Laravel Framework ke folder config. dimana secara default, Laravel 11 tidak menyertakan semua file config secara fisik di folder config. Biasanya digunakan jika ingin:
- Mengubah default timezone
- Mengatur cache driver
- Mengatur session
- Mengatur filesystem
- Melihat config Laravel secara detail








