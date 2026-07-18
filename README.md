# PANDUAN INTERNAL PROYEK

## Setup, Instalasi & Struktur Direktori Boilerplate

**Company Profile & E-Commerce — Laravel 11 + Inertia React + Tailwind**
_Fixed-version strategy — dikunci agar bebas dependency hell_

Dokumen ini adalah panduan baku (standard) yang wajib diikuti setiap kali memulai proyek baru dari boilerplate ini. Tujuannya: junior dev bisa langsung jalan tanpa nebak-nebak — mulai dari instalasi, penempatan file di folder yang benar, sampai cara menyambungkan API. Struktur di luar panduan ini (fitur, tambahan modul, dsb.) bebas dikembangkan mengikuti kebutuhan masing-masing proyek.

## Daftar Isi

1. Prasyarat Sistem
2. Langkah Instalasi (Terminal)
3. Menjalankan Aplikasi (Development)
4. Struktur Direktori Standar Proyek
5. Konvensi Routing
6. Panduan Integrasi API
7. Checklist Sebelum Mulai Development

## 1. Prasyarat Sistem

Pastikan environment berikut sudah terpasang sebelum instalasi. Versi dikunci agar seluruh tim memakai konfigurasi yang identik.

| Komponen      | Versi Minimum                    | Cek dengan          |
| ------------- | -------------------------------- | ------------------- |
| PHP           | 8.3 atau lebih baru              | `php -v`            |
| Composer      | 2.x                              | `composer -V`       |
| Node.js & npm | Node.js 20 (LTS) atau lebih baru | `node -v && npm -v` |
| Database      | MySQL 8.x atau MariaDB setara    | `mysql --version`   |

## 2. Langkah Instalasi (Terminal)

Jalankan berurutan dari atas ke bawah. Semua perintah dieksekusi dari root folder proyek kecuali disebutkan lain.

### Langkah 1 — Membuat Proyek Laravel 11

```bash
composer create-project laravel/laravel:^11.0 nama-project
cd nama-project
```

### Langkah 2 — Starter Kit Breeze (React + Inertia + Tailwind)

Breeze menyiapkan autentikasi dasar sekaligus mengonfigurasi React, Inertia.js, dan Tailwind CSS dalam satu perintah.

```bash
composer require laravel/breeze --dev
php artisan breeze:install react
```

### Langkah 3 — Package Wajib Standar Enterprise

| Package                     | Fungsi                                   |
| --------------------------- | ---------------------------------------- |
| `spatie/laravel-permission` | Role & permission (mis. admin, customer) |
| `owen-it/laravel-auditing`  | Audit trail / log perubahan data         |
| `maatwebsite/excel`         | Export & import Excel                    |

```bash
composer require spatie/laravel-permission
composer require owen-it/laravel-auditing
composer require maatwebsite/excel
```

### Langkah 4 — Konfigurasi File .env

Sesuaikan koneksi database, lalu ubah driver queue ke database supaya proses berat (export/import, kirim email) berjalan di background.

```env
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=db_nama_project
DB_USERNAME=root
DB_PASSWORD=

QUEUE_CONNECTION=database
```

### Langkah 5 — Publikasi Konfigurasi & Migrasi Database

```bash
php artisan vendor:publish --provider="Spatie\Permission\PermissionServiceProvider"
php artisan vendor:publish --provider="OwenIt\Auditing\AuditingServiceProvider"
php artisan migrate
```

Catatan: Di Laravel 11, tabel queue jobs umumnya sudah tersedia di migrasi default — tidak perlu publish tambahan.

### Langkah 6 — Symlink Storage & Setup Frontend

Menghubungkan folder storage agar file upload (gambar produk, dokumen) bisa diakses browser, lalu memasang dependency frontend.

```bash
php artisan storage:link
npm install
npm install react-select
```

## 3. Menjalankan Aplikasi (Development)

Buka 3 terminal terpisah di root proyek — ketiganya harus jalan bersamaan selama development.

| Terminal | Perintah                 | Fungsi                                                     |
| -------- | ------------------------ | ---------------------------------------------------------- |
| 1        | `php artisan serve`      | Server backend Laravel. Akses: `http://localhost:8000`     |
| 2        | `npm run dev`            | Build & hot-reload aset frontend (React/Tailwind) via Vite |
| 3        | `php artisan queue:work` | Worker background: export/import Excel, kirim email, dll   |

## 4. Struktur Direktori Standar Proyek

Ini adalah struktur baku yang wajib diikuti. Tiga area utama dipisah jelas — Public (halaman umum/company profile & katalog), Customer (area setelah login), Admin (dashboard pengelolaan) — plus Api untuk kebutuhan integrasi eksternal.

```text
nama-project/
├── app/
│   ├── Http/
│   │   ├── Controllers/
│   │   │   ├── Admin/              -> Dashboard admin (CRUD produk, user, laporan)
│   │   │   │   ├── DashboardController.php
│   │   │   │   ├── ProductController.php
│   │   │   │   ├── CategoryController.php
│   │   │   │   └── UserController.php
│   │   │   ├── Customer/           -> Area akun customer (wajib login)
│   │   │   │   ├── ProfileController.php
│   │   │   │   └── OrderController.php
│   │   │   ├── Public/             -> Halaman umum (tanpa login)
│   │   │   │   ├── HomeController.php
│   │   │   │   ├── CatalogController.php
│   │   │   │   └── ContactController.php
│   │   │   ├── Api/V1/             -> Controller khusus API (return JSON)
│   │   │   │   ├── ProductApiController.php
│   │   │   │   └── AuthApiController.php
│   │   │   └── Auth/               -> Bawaan Breeze (login, register, dll)
│   │   ├── Middleware/
│   │   │   └── IsAdmin.php         -> Cek role sebelum masuk area admin
│   │   ├── Requests/               -> Form validation, dikelompokkan per area
│   │   │   ├── Admin/
│   │   │   ├── Customer/
│   │   │   └── Public/
│   │   └── Resources/              -> Transformer JSON untuk API
│   │       ├── ProductResource.php
│   │       └── UserResource.php
│   └── Models/
│       ├── Product.php
│       ├── Category.php
│       ├── Order.php
│       └── User.php
├── database/
│   ├── migrations/
│   ├── seeders/
│   └── factories/
├── resources/
│   ├── js/
│   │   ├── Pages/                  -> 1 file = 1 halaman (di-render Inertia)
│   │   │   ├── Admin/
│   │   │   │   ├── Dashboard.jsx
│   │   │   │   ├── Products/{Index,Create,Edit}.jsx
│   │   │   │   └── Users/Index.jsx
│   │   │   ├── Public/
│   │   │   │   ├── Home.jsx
│   │   │   │   ├── Catalog/{Index,Detail}.jsx
│   │   │   │   └── Contact.jsx
│   │   │   ├── Customer/
│   │   │   │   ├── Profile/Edit.jsx
│   │   │   │   └── Orders/Index.jsx
│   │   │   └── Auth/               -> Bawaan Breeze
│   │   ├── Layouts/
│   │   │   ├── AdminLayout.jsx     -> Sidebar + topbar dashboard
│   │   │   ├── PublicLayout.jsx    -> Navbar + footer situs umum
│   │   │   └── CustomerLayout.jsx  -> Layout area akun customer
│   │   ├── Components/
│   │   │   ├── Admin/
│   │   │   ├── Public/
│   │   │   └── Shared/             -> Button, Input, Modal (reusable lintas area)
│   │   └── app.jsx
│   └── css/app.css
├── routes/
│   ├── web.php                     -> Semua route Inertia (public+customer+admin)
│   ├── api.php                     -> Semua route API (mobile app/integrasi luar)
│   └── auth.php                    -> Bawaan Breeze
├── public/
│   └── storage -> symlink ke storage/app/public
└── .env
```

### Aturan Penempatan File

| Folder / File                    | Fungsi                                                                    |
| -------------------------------- | ------------------------------------------------------------------------- |
| `Http/Controllers/Admin`         | Semua controller fitur dashboard: kelola produk, kategori, user, laporan. |
| `Http/Controllers/Customer`      | Controller area akun setelah login: profil, riwayat pesanan.              |
| `Http/Controllers/Public`        | Controller halaman tanpa login: beranda, katalog produk, kontak.          |
| `Http/Controllers/Api/V1`        | Controller API murni (JSON) untuk mobile app / pihak ketiga.              |
| `resources/js/Pages/Admin`       | Halaman React dashboard admin.                                            |
| `resources/js/Pages/Public`      | Halaman React untuk company profile & katalog publik.                     |
| `resources/js/Pages/Customer`    | Halaman React area akun customer.                                         |
| `resources/js/Layouts`           | Kerangka tampilan (sidebar/navbar/footer) per area — dipakai berulang.    |
| `resources/js/Components/Shared` | Komponen kecil reusable lintas area (tombol, input, modal).               |

Catatan: Satu Controller hanya menangani satu area (Admin/Customer/Public/Api). Jangan campur logic admin dan public dalam satu Controller — memudahkan tracking hak akses dan maintenance.

## 5. Konvensi Routing

Semua route halaman (Inertia) tetap satu file `routes/web.php`, dikelompokkan per area pakai prefix + name + middleware. Route API murni dipisah ke `routes/api.php` (lihat Bab 6).

```php
// routes/web.php

// --- Public (tanpa login) ---
Route::get('/', [HomeController::class, 'index'])->name('home');
Route::get('/katalog', [CatalogController::class, 'index'])->name('catalog');
Route::get('/katalog/{slug}', [CatalogController::class, 'show'])->name('catalog.show');
Route::get('/kontak', [ContactController::class, 'index'])->name('contact');

// --- Customer (wajib login) ---
Route::middleware(['auth', 'verified'])->prefix('akun')->name('customer.')->group(function () {
    Route::get('/profil', [ProfileController::class, 'edit'])->name('profile.edit');
    Route::get('/pesanan', [OrderController::class, 'index'])->name('orders.index');
});

// --- Admin (wajib login + role admin) ---
Route::middleware(['auth', 'is_admin'])->prefix('admin')->name('admin.')->group(function () {
    Route::get('/dashboard', [DashboardController::class, 'index'])->name('dashboard');
    Route::resource('products', ProductController::class);
    Route::resource('categories', CategoryController::class);
});
```

### Middleware Role Admin (Laravel 11)

Laravel 11 mendaftarkan middleware alias lewat `bootstrap/app.php`, bukan lagi `Kernel.php`.

```bash
php artisan make:middleware IsAdmin
```

```php
// bootstrap/app.php
->withMiddleware(function (Middleware $middleware) {
    $middleware->alias([
        'is_admin' => \App\Http\Middleware\IsAdmin::class,
    ]);
})
```

```php
// Contoh assign role via Tinker / seeder (Spatie Permission)
$user->assignRole('admin');
```

## 6. Panduan Integrasi API

### 6.1 Kapan Perlu API Terpisah?

Halaman yang di-render Inertia (`Pages/*`) sudah otomatis menerima data dari Controller lewat `Inertia::render()` — tidak perlu fetch API tambahan untuk load halaman. `routes/api.php` baru dibutuhkan untuk:

- Aplikasi mobile (Android/iOS) yang konsumsi data dari backend yang sama.
- Integrasi pihak ketiga (mis. sistem gudang, marketplace).
- Interaksi partial di halaman tanpa reload penuh — mis. live search, badge keranjang, notifikasi.

### 6.2 Setup Sanctum (Autentikasi Token API)

```bash
composer require laravel/sanctum
php artisan vendor:publish --provider="Laravel\Sanctum\SanctumServiceProvider"
php artisan migrate
```

### 6.3 Struktur `routes/api.php`

Gunakan versioning (v1) sejak awal supaya perubahan struktur di masa depan tidak merusak konsumen API yang sudah berjalan.

```php
// routes/api.php
use App\Http\Controllers\Api\V1\ProductApiController;
use App\Http\Controllers\Api\V1\AuthApiController;

Route::prefix('v1')->group(function () {
    Route::post('/login', [AuthApiController::class, 'login']);

    Route::middleware('auth:sanctum')->group(function () {
        Route::get('/profile', [AuthApiController::class, 'profile']);
        Route::get('/products', [ProductApiController::class, 'index']);
        Route::get('/products/{id}', [ProductApiController::class, 'show']);
    });
});
```

### 6.4 Controller API + API Resource

Controller API hanya mengembalikan JSON — gunakan Resource agar format response konsisten dan tidak membocorkan kolom sensitif.

```bash
php artisan make:resource ProductResource
```

```php
// app/Http/Resources/ProductResource.php
public function toArray($request)
{
    return [
        'id'    => $this->id,
        'name'  => $this->name,
        'price' => $this->price,
        'image' => asset('storage/' . $this->image),
    ];
}
```

```php
// app/Http/Controllers/Api/V1/ProductApiController.php
public function index()
{
    $products = Product::latest()->paginate(12);
    return ProductResource::collection($products);
}
```

### 6.5 Konsumsi API dari Frontend (React/axios)

Dipakai untuk kasus di luar Inertia page-load biasa, misalnya live search di halaman katalog.

```jsx
// resources/js/Pages/Public/Catalog/Index.jsx
import axios from "axios";

async function searchProducts(keyword) {
    const res = await axios.get("/api/v1/products", { params: { q: keyword } });
    return res.data.data; // hasil sudah lewat ProductResource
}
```

Catatan: axios sudah otomatis dikonfigurasi Breeze (baseURL & header) — tidak perlu setup ulang.

### 6.6 CORS (Jika API Diakses dari Domain/App Lain)

Jika API dikonsumsi dari luar (aplikasi mobile terpisah, domain frontend berbeda), atur `config/cors.php`:

```php
// config/cors.php
'paths' => ['api/*', 'sanctum/csrf-cookie'],
'allowed_origins' => ['https://app-mobile-domain.com'],
'supports_credentials' => true,
```

## 7. Checklist Sebelum Mulai Development

- `php artisan serve`, `npm run dev`, dan `php artisan queue:work` jalan tanpa error di 3 terminal.
- Migrasi database sukses (`php artisan migrate`) — tabel Spatie & Auditing sudah ada.
- `php artisan storage:link` sudah dijalankan (upload gambar bisa diakses via `/storage/...`).
- Controller baru ditempatkan sesuai area: Admin / Customer / Public / `Api\V1` — tidak dicampur.
- Halaman React baru ditaruh di `resources/js/Pages/<Area>/` sesuai controller yang memanggilnya.
- Route baru didaftarkan dengan prefix + name + middleware yang sesuai area.
- Role user (admin/customer) sudah di-assign lewat Spatie sebelum testing akses dashboard.

Struktur di atas adalah kerangka baku. Di luar itu — fitur, package tambahan, styling, dsb. — bebas dikembangkan mengikuti kebutuhan masing-masing proyek.
