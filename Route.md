# Routing Laravel

Route adalah penghubung antara URL yang diakses user dengan aksi yang dijalankan aplikasi.
Contoh Route:
```
Route::get('/about', function () {
    return view('about');
});
```
### Penjelasan
#### 1. Route::get
```
Route::get
```
get adalah salah satu dari HTTP method yang berfungsi untuk mengambil data/halaman.

HTTP method lain : 
- get → mengambil data / halaman
- post → mengirim data (form)
- put / patch → update data
- delete → hapus data

#### 2. '/about'
```
'/about'
```
Merupakan URL path, jika route di terapkan maka route ini akan dijalankan.
```
http://localhost:8000/about
```

#### 3. function () { ... }
```
function () {
    return view('about');
}
```
Ini disebut closure, yang berisi aksi yang akan dijalankan saat route diakses.

Closure adalah function tanpa nama
- Bisa disimpan di variabel
- Bisa dikirim sebagai parameter
- Bisa akses variabel luar dengan "use"
- Banyak dipakai di Laravel (Route, Collection, Callback)

#### 4. return view('about')
```
return view('about')
```
Akan mengembalikan fungsi view yang mana akan menampilkan file view, Laravel secara otomatis akan mencari file about.blade.php yang berada di resources
```
resources/views/about.blade.php
```
