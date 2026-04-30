# Laporan Pengembangan Layanan CRUD Produk (Laravel 11)

## 1. Deskripsi Singkat Layanan
Layanan ini adalah **Product Service** yang berfungsi untuk mengelola data produk dalam suatu sistem (misalnya sistem e-commerce atau inventaris). Layanan ini menyediakan operasi dasar CRUD (Create, Read, Update, Delete) melalui API yang dapat diakses secara publik. 

**Teknologi yang Digunakan:**
- **Framework:** Laravel 11
- **Database:** SQLite
- **Autentikasi:** Laravel Sanctum (opsional untuk pengembangan lebih lanjut)
- **Arsitektur:** RESTful API

## 2. Penjelasan Endpoint API (CRUD)

Berikut adalah daftar endpoint yang tersedia dalam layanan ini:

| Method | Endpoint | Deskripsi | Parameter Request (JSON) |
|--------|----------|-----------|-------------------------|
| **GET** | `/api/products` | Mengambil semua data produk | - |
| **POST** | `/api/products` | Menambahkan produk baru | `name`, `description`, `price`, `stock` |
| **GET** | `/api/products/{id}` | Mengambil detail produk berdasarkan ID | - |
| **PUT/PATCH** | `/api/products/{id}` | Memperbarui data produk berdasarkan ID | `name`, `description`, `price`, `stock` (opsional) |
| **DELETE** | `/api/products/{id}` | Menghapus produk berdasarkan ID | - |

### Struktur JSON Request (Contoh POST/PUT):
```json
{
    "name": "Kopi Susu Gula Aren",
    "description": "Kopi susu dengan gula aren pilihan",
    "price": 15000,
    "stock": 50
}
```

## 3. Instruksi Pengujian Postman

Untuk menguji layanan ini menggunakan Postman, ikuti langkah-langkah berikut:

1. **Jalankan Server Lokal:**
   Buka terminal di direktori proyek dan jalankan:
   ```bash
   php artisan serve
   ```
   Server biasanya akan berjalan di `http://127.0.0.1:8000`.

2. **Pengujian Get All Products:**
   - Method: `GET`
   - URL: `http://127.0.0.1:8000/api/products`
   - Klik `Send`.

3. **Pengujian Create Product:**
   - Method: `POST`
   - URL: `http://127.0.0.1:8000/api/products`
   - Tab `Body` -> Pilih `raw` -> Pilih format `JSON`.
   - Masukkan data JSON produk.
   - Klik `Send`.

4. **Pengujian Update Product:**
   Method: `PUT`
   URL: `http://127.0.0.1:8000/api/products/{id}`
   Tab `Body` -> Pilih `raw` -> Pilih format `JSON`.
   Masukkan data yang ingin diubah.
   Klik `Send`.

5. **Pengujian Delete Product:**
   Method: `DELETE`
   URL: `http://127.0.0.1:8000/api/products/{id}`
   Klik `Send`.

## 4. Screenshot Pengujian (Postman)
*Silakan lakukan pengujian mandiri dan ambil screenshot pada bagian berikut untuk dilampirkan dalam PDF:*
- Screenshot respons **GET** (Daftar Produk)
- Screenshot respons **POST** (Berhasil menambah produk)
- Screenshot respons **GET Detail** (Berdasarkan ID)
- Screenshot respons **PUT** (Update berhasil)
- Screenshot respons **DELETE** (Hapus berhasil)

---
**Catatan:** Proyek ini telah dikonfigurasi menggunakan Laravel 11 dengan SQLite sebagai database bawaan agar mudah dijalankan tanpa konfigurasi server database tambahan.
