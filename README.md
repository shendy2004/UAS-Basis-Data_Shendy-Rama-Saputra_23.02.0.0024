# UAS-Basis-Data-Lanjutan_Shendy-Rama-Saputra_23.02.0.0024
Tugas ini dibuat untuk memenuhi tugas UAS

mata kuliah: Basis Data Lanjutan

Yang diampu oleh: Bapak M. Hafiz Hasbiyallah S.Kom

Ini adalah database sederhana untuk mengelola data restoran, mencakup informasi tentang pelanggan, karyawan, daftar menu, pesanan, dan detail setiap pesanan.

## Struktur Tabel
Database ini terdiri dari lima tabel utama:

### `pelanggan`
Menyimpan informasi tentang pelanggan restoran.
- `pelanggan_id`: Kunci utama, ID unik untuk setiap pelanggan.
- `nama`: Nama lengkap pelanggan.
- `no_meja`: No Meja Pelanggan.
- `no_telepon`: Nomor telepon pelanggan.

### `karyawan`
Menyimpan informasi tentang karyawan restoran.
- `karyawan_id`: Kunci utama, ID unik untuk setiap karyawan.
- `nama`: Nama lengkap karyawan.
- `posisi`: Jabatan atau posisi karyawan (contoh: Manager, Koki, Pelayan).
- `tanggal_bergabung`: Tanggal karyawan mulai bekerja.

### `menu`
Menyimpan daftar item menu yang tersedia di restoran.
- `menu_id`: Kunci utama, ID unik untuk setiap item menu.
- `nama_menu`: Nama item menu.
- `deskripsi`: Deskripsi singkat tentang item menu.
- `harga`: Harga item menu.
- `kategori`: Kategori item menu (contoh: Makanan Utama, Minuman, Dessert).

### `pesanan`
Mencatat setiap pesanan yang dibuat oleh pelanggan.
- `pesanan_id`: Kunci utama, ID unik untuk setiap pesanan.
- `pelanggan_id`: Kunci Sekunder, merujuk ke `pelanggan_id` di tabel `pelanggan`.
- `karyawan_id`: Kunci Sekunder, merujuk ke `karyawan_id` di tabel `karyawan` (karyawan yang menerima pesanan).
- `tanggal_pesanan`: Tanggal dan waktu pesanan dibuat (default waktu saat ini).
- `status_pesanan`: Status pesanan (contoh: Menunggu, Diproses, Selesai, Dibatalkan).
- `total_harga`: Total harga untuk seluruh pesanan.

### `detail_pesanan`
Berisi detail item yang termasuk dalam setiap pesanan.
- `detail_id`: Kunci utama, ID unik untuk setiap detail pesanan.
- `pesanan_id`: Kunci Sekunder, merujuk ke `pesanan_id` di tabel `pesanan`.
- `menu_id`: Kunci Sekunder, merujuk ke `menu_id` di tabel `menu`.
- `jumlah`: Jumlah item menu yang dipesan.
- `harga_satuan`: Harga per unit item menu pada saat pesanan dibuat.
- `subtotal`: Subtotal untuk item menu tersebut (jumlah * harga_satuan).


## Cara Mengimpor Database
Untuk mengimpor database ini ke sistem manajemen database, langkah-langkahnya adalah berikut:

1.  **Pastikan Anda memiliki database server:** Pastikan Anda memiliki MySQL terinstal dan berjalan di sistem Anda.
2.  **Buat database baru:** Buka klien SQL seperti MySQL dan buat database kosong. Contoh untuk MySQL:
    ```sql
    CREATE DATABASE restoran_db;
    USE restoran_db;
    ```
3.  **Impor file `database.sql`:**
    * **Melalui Command Line (Terminal):**
        Arahkan ke penyimpanan tempat Anda menyimpan file `database.sql`.
        ```bash
        mysql -u username -p nama_database < database.sql
        ```
        Ganti `username` dengan username databasenya, dan `nama_database` dengan nama database `restoran_db'.
    * **Melalui Alat GUI (Misalnya MySQL Workbench):**
        1.  Buka MySQL Workbench (atau alat GUI serupa).
        2.  Hubungkan ke server database Anda.
        3.  Pilih atau buat database baru (`restoran_db`).
        4.  Pergi ke `File > Open SQL Script` dan pilih `database.sql`.
        5.  Eksekusi script tersebut (biasanya dengan ikon petir atau `Ctrl + Shift + Enter`).



## Nama & NIM

**Nama:** [Shendy Rama Saputra]
**NIM:** [23.02.0.0024]
