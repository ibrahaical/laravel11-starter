# PANDUAN INTERNAL PROYEK [cite: 1]

## Setup, Instalasi & Struktur Direktori Boilerplate [cite: 1]

**Company Profile & E-Commerce — Laravel 11 + Inertia React + Tailwind** [cite: 1]
_Fixed-version strategy — dikunci agar bebas dependency hell_ [cite: 1]

Dokumen ini adalah panduan baku (standard) yang wajib diikuti setiap kali memulai proyek baru dari boilerplate ini. [cite: 1] Tujuannya: junior dev bisa langsung jalan tanpa nebak-nebak — mulai dari instalasi, penempatan file di folder yang benar, sampai cara menyambungkan API. [cite: 1] Struktur di luar panduan ini (fitur, tambahan modul, dsb.) bebas dikembangkan mengikuti kebutuhan masing-masing proyek. [cite: 1]

## Daftar Isi [cite: 1]

1. Prasyarat Sistem [cite: 1]
2. Langkah Instalasi (Terminal) [cite: 1]
3. Menjalankan Aplikasi (Development) [cite: 1]
4. Struktur Direktori Standar Proyek [cite: 1]
5. Konvensi Routing [cite: 1]
6. Panduan Integrasi API [cite: 1]
7. Checklist Sebelum Mulai Development [cite: 1]

## 1. Prasyarat Sistem [cite: 1]

Pastikan environment berikut sudah terpasang sebelum instalasi. [cite: 1] Versi dikunci agar seluruh tim memakai konfigurasi yang identik. [cite: 1]

| Komponen      | Versi Minimum                              | Cek dengan                    |
| ------------- | ------------------------------------------ | ----------------------------- |
| PHP           | 8.3 atau lebih baru [cite: 1]              | `php -v` [cite: 1]            |
| Composer      | 2.x [cite: 1]                              | `composer -V` [cite: 1]       |
| Node.js & npm | Node.js 20 (LTS) atau lebih baru [cite: 1] | `node -v && npm -v` [cite: 1] |
| Database      | MySQL 8.x atau MariaDB setara [cite: 1]    | `mysql --version` [cite: 1]   |

## 2. Langkah Instalasi (Terminal) [cite: 1]

Jalankan berurutan dari atas ke bawah. [cite: 1] Semua perintah dieksekusi dari root folder proyek kecuali disebutkan lain. [cite: 1]

### Langkah 1 — Membuat Proyek Laravel 11 [cite: 1]

```bash
composer create-project laravel/laravel:^11.0 nama-project
cd nama-project
```

### Langkah 2 — Starter Kit Breeze (React + Inertia + Tailwind) [cite: 1]

Breeze menyiapkan autentikasi dasar sekaligus mengonfigurasi React, Inertia.js, dan Tailwind CSS dalam satu perintah. [cite: 1]

```bash
composer require laravel/breeze --dev
php artisan breeze:install react
```

### Langkah 3 — Package Wajib Standar Enterprise [cite: 1]

| Package                               | Fungsi                                             |
| ------------------------------------- | -------------------------------------------------- |
| `spatie/laravel-permission` [cite: 1] | Role & permission (mis. admin, customer) [cite: 1] |
| `owen-it/laravel-auditing` [cite: 1]  | Audit trail / log perubahan data [cite: 1]         |
| `maatwebsite/excel` [cite: 1]         | Export & import Excel [cite: 1]                    |

```bash
composer require spatie/laravel-permission
composer require owen-it/laravel-auditing
composer require maatwebsite/excel
```

### Langkah 4 — Konfigurasi File .env [cite: 1]

Sesuaikan koneksi database, lalu ubah driver queue ke database supaya proses berat (export/import, kirim email) berjalan di background. [cite: 1]

```env
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=db_nama_project
DB_USERNAME=root
DB_PASSWORD=

QUEUE_CONNECTION=database
```

### Langkah 5 — Publikasi Konfigurasi & Migrasi Database [cite: 1]

```bash
php artisan vendor:publish --provider="Spatie\Permission\PermissionServiceProvider"
php artisan vendor:publish --provider="OwenIt\Auditing\AuditingServiceProvider"
php artisan migrate
```

Catatan: Di Laravel 11, tabel queue jobs umumnya sudah tersedia di migrasi default — tidak perlu publish tambahan. [cite: 1]

### Langkah 6 — Symlink Storage & Setup Frontend [cite: 1]

Menghubungkan folder storage agar file upload (gambar produk, dokumen) bisa diakses browser, lalu memasang dependency frontend. [cite: 1]

```bash
php artisan storage:link
npm install
npm install react-select
```

## 3. Menjalankan Aplikasi (Development) [cite: 1]

Buka 3 terminal terpisah di root proyek — ketiganya harus jalan bersamaan selama development. [cite: 1]

| Terminal    | Perintah                           | Fungsi                                                               |
| ----------- | ---------------------------------- | -------------------------------------------------------------------- |
| 1 [cite: 1] | `php artisan serve` [cite: 1]      | Server backend Laravel. Akses: `http://localhost:8000` [cite: 1]     |
| 2 [cite: 1] | `npm run dev` [cite: 1]            | Build & hot-reload aset frontend (React/Tailwind) via Vite [cite: 1] |
| 3 [cite: 1] | `php artisan queue:work` [cite: 1] | Worker background: export/import Excel, kirim email, dll [cite: 1]   |

## 4. Struktur Direktori Standar Proyek [cite: 1]

Ini adalah struktur baku yang wajib diikuti. [cite: 1] Tiga area utama dipisah jelas — Public (halaman umum/company profile & katalog), Customer (area setelah login), Admin (dashboard pengelolaan) — plus Api untuk kebutuhan integrasi eksternal. [cite: 1]

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

### Aturan Penempatan File [cite: 1]

| Folder / File                              | Fungsi                                                                              |
| ------------------------------------------ | ----------------------------------------------------------------------------------- |
| `Http/Controllers/Admin` [cite: 1]         | Semua controller fitur dashboard: kelola produk, kategori, user, laporan. [cite: 1] |
| `Http/Controllers/Customer` [cite: 1]      | Controller area akun setelah login: profil, riwayat pesanan. [cite: 1]              |
| `Http/Controllers/Public` [cite: 1]        | Controller halaman tanpa login: beranda, katalog produk, kontak. [cite: 1]          |
| `Http/Controllers/Api/V1` [cite: 1]        | Controller API murni (JSON) untuk mobile app / pihak ketiga. [cite: 1]              |
| `resources/js/Pages/Admin` [cite: 1]       | Halaman React dashboard admin. [cite: 1]                                            |
| `resources/js/Pages/Public` [cite: 1]      | Halaman React untuk company profile & katalog publik. [cite: 1]                     |
| `resources/js/Pages/Customer` [cite: 1]    | Halaman React area akun customer. [cite: 1]                                         |
| `resources/js/Layouts` [cite: 1]           | Kerangka tampilan (sidebar/navbar/footer) per area — dipakai berulang. [cite: 1]    |
| `resources/js/Components/Shared` [cite: 1] | Komponen kecil reusable lintas area (tombol, input, modal). [cite: 1]               |

Catatan: Satu Controller hanya menangani satu area (Admin/Customer/Public/Api). [cite: 1] Jangan campur logic admin dan public dalam satu Controller — memudahkan tracking hak akses dan maintenance. [cite: 1]

## 5. Konvensi Routing [cite: 1]

Semua route halaman (Inertia) tetap satu file `routes/web.php`, dikelompokkan per area pakai prefix + name + middleware. [cite: 1] Route API murni dipisah ke `routes/api.php` (lihat Bab 6). [cite: 1]

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

### Middleware Role Admin (Laravel 11) [cite: 1]

Laravel 11 mendaftarkan middleware alias lewat `bootstrap/app.php`, bukan lagi `Kernel.php`. [cite: 1]

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

## 6. Panduan Integrasi API [cite: 1]

### 6.1 Kapan Perlu API Terpisah? [cite: 1]

Halaman yang di-render Inertia (`Pages/*`) sudah otomatis menerima data dari Controller lewat `Inertia::render()` — tidak perlu fetch API tambahan untuk load halaman. [cite: 1] `routes/api.php` baru dibutuhkan untuk: [cite: 1]

- Aplikasi mobile (Android/iOS) yang konsumsi data dari backend yang sama. [cite: 1]
- Integrasi pihak ketiga (mis. sistem gudang, marketplace). [cite: 1]
- Interaksi partial di halaman tanpa reload penuh — mis. live search, badge keranjang, notifikasi. [cite: 1]

### 6.2 Setup Sanctum (Autentikasi Token API) [cite: 1]

```bash
composer require laravel/sanctum
php artisan vendor:publish --provider="Laravel\Sanctum\SanctumServiceProvider"
php artisan migrate
```

### 6.3 Struktur `routes/api.php` [cite: 1]

Gunakan versioning (v1) sejak awal supaya perubahan struktur di masa depan tidak merusak konsumen API yang sudah berjalan. [cite: 1]

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

### 6.4 Controller API + API Resource [cite: 1]

Controller API hanya mengembalikan JSON — gunakan Resource agar format response konsisten dan tidak membocorkan kolom sensitif. [cite: 1]

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

### 6.5 Konsumsi API dari Frontend (React/axios) [cite: 1]

Dipakai untuk kasus di luar Inertia page-load biasa, misalnya live search di halaman katalog. [cite: 1]

```jsx
// resources/js/Pages/Public/Catalog/Index.jsx
import axios from "axios";

async function searchProducts(keyword) {
    const res = await axios.get("/api/v1/products", { params: { q: keyword } });
    return res.data.data; // hasil sudah lewat ProductResource
}
```

Catatan: axios sudah otomatis dikonfigurasi Breeze (baseURL & header) — tidak perlu setup ulang. [cite: 1]

### 6.6 CORS (Jika API Diakses dari Domain/App Lain) [cite: 1]

Jika API dikonsumsi dari luar (aplikasi mobile terpisah, domain frontend berbeda), atur `config/cors.php`: [cite: 1]

```php
// config/cors.php
'paths' => ['api/*', 'sanctum/csrf-cookie'],
'allowed_origins' => ['https://app-mobile-domain.com'],
'supports_credentials' => true,
```

## 7. Checklist Sebelum Mulai Development [cite: 1]

- `php artisan serve`, `npm run dev`, dan `php artisan queue:work` jalan tanpa error di 3 terminal. [cite: 1]
- Migrasi database sukses (`php artisan migrate`) — tabel Spatie & Auditing sudah ada. [cite: 1]
- `php artisan storage:link` sudah dijalankan (upload gambar bisa diakses via `/storage/...`). [cite: 1]
- Controller baru ditempatkan sesuai area: Admin / Customer / Public / `Api\V1` — tidak dicampur. [cite: 1]
- Halaman React baru ditaruh di `resources/js/Pages/<Area>/` sesuai controller yang memanggilnya. [cite: 1]
- Route baru didaftarkan dengan prefix + name + middleware yang sesuai area. [cite: 1]
- Role user (admin/customer) sudah di-assign lewat Spatie sebelum testing akses dashboard. [cite: 1]

Struktur di atas adalah kerangka baku. [cite: 1] Di luar itu — fitur, package tambahan, styling, dsb. — bebas dikembangkan mengikuti kebutuhan masing-masing proyek. [cite: 1]
