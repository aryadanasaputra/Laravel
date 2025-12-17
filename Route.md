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
Ini disebut closure
