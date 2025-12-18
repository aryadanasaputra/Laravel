# Routing Laravel

Route adalah penghubung antara URL yang diakses user dengan aksi yang dijalankan aplikasi.

---

## Contoh Route Sederhana

```php
Route::get('/about', function () {
    return view('about');
});
```

---

## Penjelasan

### 1. `Route::get`

```php
Route::get
```

* `get` adalah salah satu **HTTP Method**
* Digunakan untuk **mengambil data atau menampilkan halaman**
* Biasanya dipanggil langsung lewat browser

HTTP method lain:

* `get` → mengambil data / halaman
* `post` → mengirim data (form)
* `put / patch` → update data
* `delete` → hapus data

📌 **Catatan:**
Route akan dieksekusi berdasarkan HTTP method yang sesuai. Jika method tidak cocok, route tidak akan dijalankan.

---

### 2. `'/about'`

```php
'/about'
```

* Merupakan **URL path**
* Saat user mengakses URL berikut:

```text
http://localhost:8000/about
```

Laravel akan menjalankan route ini.

📌 **Catatan:**

* URL tidak harus sama dengan nama file view
* URL bebas ditentukan sesuai kebutuhan aplikasi

---

### 3. `function () { ... }`

```php
function () {
    return view('about');
}
```

* Ini disebut **closure**
* Berisi aksi yang dijalankan ketika route diakses

**Closure adalah function tanpa nama**:

* Bisa disimpan di variabel
* Bisa dikirim sebagai parameter
* Bisa mengakses variabel luar dengan keyword `use`
* Banyak digunakan di Laravel (Route, Collection, Callback)

📌 **Catatan:**
Penggunaan closure cocok untuk route sederhana. Untuk aplikasi besar, lebih disarankan menggunakan **Controller**.

---

### 4. `return view('about')`

```php
return view('about');
```

* Mengembalikan tampilan (view) ke browser
* Laravel otomatis mencari file:

```text
resources/views/about.blade.php
```

📌 **Catatan:**

* Tidak perlu menuliskan ekstensi `.blade.php`
* `view('folder.about')` berarti:

```text
resources/views/folder/about.blade.php
```

---

## Route ke Controller (Disarankan)

```php
Route::get('/about', [AboutController::class, 'index']);
```

📌 **Penjelasan:**

* Route memanggil method `index`
* Logic dipisahkan ke Controller agar kode lebih rapi

---

## Route dengan Parameter

```php
Route::get('/user/{id}', function ($id) {
    return 'User ID: ' . $id;
});
```

📌 **Penjelasan:**

* `{id}` adalah parameter
* Nilai parameter akan dikirim ke function

---

## Named Route

```php
Route::get('/profile', function () {
    return 'Profile';
})->name('profile');
```

Digunakan di Blade:

```blade
<a href="{{ route('profile') }}">Profile</a>
```

📌 **Keuntungan:**

* URL aman jika berubah
* Lebih rapi dan mudah dirawat

---

## Melihat Semua Route

Gunakan perintah terminal:

```bash
php artisan route:list
```

Menampilkan:

* HTTP Method
* URL
* Controller / Closure
* Middleware

---

## Ringkasan Singkat

* Route = URL → Aksi
* `Route::get()` untuk halaman
* Closure cocok untuk route kecil
* Controller untuk aplikasi besar
* View disimpan di `resources/views`
