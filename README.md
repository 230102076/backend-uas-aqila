# Sistem Informasi Rumah Sakit – Backend API (CodeIgniter 4)
## Deskripsi
Proyek ini merupakan bagian dari Ujian Akhir Semester mata kuliah Praktikum Pemrograman Berbasis Framework semester genap 2024/2025.
Backend ini dibangun menggunakan CodeIgniter 4 dan berfungsi sebagai RESTful API untuk mengelola data pasien dan obat.

 ## Fitur API
Setiap endpoint mengembalikan response dalam format JSON.
 ### Pasien
GET /pasien → Ambil semua data pasien

GET /pasien/{id} → Ambil detail satu pasien

POST /pasien → Tambah pasien baru

PUT /pasien/{id} → Ubah data pasien

DELETE /pasien/{id} → Hapus data pasien

### Obat
GET /obat → Ambil semua data obat

GET /obat/{id} → Ambil detail satu obat

POST /obat → Tambah obat baru

PUT /obat/{id} → Ubah data obat

DELETE /obat/{id} → Hapus data obat

## Struktur Folder Utama
app/Controllers/ → File controller Pasien.php dan Obat.php

app/Models/ → Model data untuk interaksi database

app/Config/Routes.php → Konfigurasi endpoint REST API

public/ → Root direktori untuk menjalankan server

app/Database/ → File migrasi & query builder


## Menggunakan Postman untuk menguji endpoint

Backend ini menggunakan CodeIgniter 4 sebagai framework utama, dengan pola RESTful API untuk menangani permintaan HTTP dari frontend.

a. Controller
1. Pasien.php
File ini menangani seluruh permintaan terkait data pasien, seperti:

Menampilkan semua data (index)

Menampilkan data berdasarkan ID (show)

Menambahkan data (create)

Memperbarui data (update)

Menghapus data (delete)

Contoh metode index():
public function index()
{
    $data = $this->pasienModel->findAll();
    return $this->respond(['data' => $data], 200);
}
Setiap respon dikirim dalam bentuk JSON, agar dapat dikonsumsi oleh frontend atau Postman dengan mudah.

## 2. Obat.php
Strukturnya serupa dengan Pasien.php, namun khusus menangani entitas obat.

Model
Model (PasienModel dan ObatModel) mengatur interaksi ke database.
Menggunakan Query Builder bawaan CodeIgniter untuk akses CRUD data secara aman dan efisien.

## Contoh konfigurasi model:
protected $table = 'pasien';
protected $allowedFields = ['nama', 'alamat', 'tanggal_lahir', 'jenis_kelamin'];

## Pengujian dengan Postman
Seluruh endpoint diuji menggunakan Postman, dalam dua grup koleksi:

1. uas_pasien

2. uas_obat

## Masing-masing memiliki 4 metode:
GET untuk menampilkan data
POST untuk menambah data
PUT untuk mengubah data
DELETE untuk menghapus data
Setiap request dikonfigurasi dengan URL sesuai endpoint dan dikirim dalam format JSON.
