# Posttest 5 -  Aplikasi CRUD Koleksi Tanaman

Proyek ini adalah implementasi CRUD LENGKAP berbasis konsol Java yang terintegrasi dengan MySQL/MariaDB. Proyek ini dirancang untuk mendemonstrasikan koneksi database menggunakan JDBC murni dan pola ORM Sederhana di bawah konsep Pemrograman Berorientasi Objek (PBO).

## Fitur Aplikasi

Aplikasi ini menyediakan fungsionalitas dasar untuk mengelola koleksi tanaman, termasuk:

* **Tambah Tanaman (Create)**: Menambahkan data tanaman baru (nama, jenis, umur). Pengguna dapat memilih jenis tanaman (Hias atau Buah), dan data tambahan akan diminta sesuai jenis yang dipilih.

* **Lihat Tanaman (Read)**: Menampilkan seluruh koleksi tanaman.

* **Ubah Tanaman (Update)**: Mengubah detail data tanaman yang sudah ada.

* **Hapus Tanaman (Delete)**: Menghapus tanaman dari koleksi.

* **Cari Tanaman (Search)**: Mencari tanaman berdasarkan nama.

* **Keluar**: Mengakhiri program.

## Struktur Project

<img width="483" height="487" alt="image" src="https://github.com/user-attachments/assets/59c0532b-794e-4aae-a4cf-2db88fa39b7e" />

## Implementasi Koneksi Database

### **1. Letak Penerapan JDBC (Java Database Connectivity)**

* JDBC diterapkan di kelas `TampilanDataJDBC.java`.
* Kelas ini dibuat khusus untuk memenuhi persyaratan tugas, yaitu menampilkan data awal dari database menggunakan object Statement

### **2. Letak Penerapan ORM (Object-Relational Mapping)**

* ORM diterapkan di kelas `TanamanRepository.java`.
* Kelas ini berfungsi sebagai lapisan ORM, menerjemahkan Objek Java menjadi query SQL (INSERT, UPDATE, DELETE) dan mengambil hasil SQL untuk dijadikan objek Java.

## Alur Program

Berikut adalah alur program yang terdokumentasi, mencakup setiap kemungkinan:

### 1. Tampilan Menu Utama

* Ketika program dimulai, menu utama akan ditampilkan dengan 6 pilihan.

* Program akan meminta input angka dari pengguna.

* Jika input bukan angka atau tidak valid, program akan menampilkan pesan kesalahan dan kembali ke menu.

### 2. Tambah Tanaman (Create)

* **Skenario Sukses**:

    * Pengguna memilih `1. Tambah Tanaman`.

    * Program meminta pengguna untuk memilih jenis tanaman (Hias atau Buah).

    * Setelah jenis dipilih, pengguna diminta untuk memasukkan detail (nama, jenis, umur).

    * Untuk `TanamanHias`, diminta `warnaBunga`. Untuk `TanamanBuah`, diminta `musimPanen`.

    * Setelah semua input valid, data akan disimpan ke `ArrayList`.

* **Skenario Gagal**:

    * Jika pengguna memasukkan input non-angka untuk umur, program akan menampilkan pesan kesalahan dan melakukan *looping* hingga input yang benar diberikan.

### 3. Lihat Tanaman (Read)

* **Skenario Sukses**: Jika koleksi tidak kosong, program akan menampilkan daftar tanaman yang lengkap, termasuk informasi tambahan dari subclass (warna bunga atau musim panen).

* **Skenario Gagal**: Jika koleksi kosong, program akan menampilkan pesan bahwa belum ada data.

### 4. Ubah Tanaman (Update)

* **Skenario Sukses**:

    * Program menampilkan daftar tanaman dan meminta nomor urut yang akan diubah.

    * Setelah nomor valid, pengguna bisa menginput nilai baru.

    * Jika input valid, data tanaman akan diperbarui.

* **Skenario Gagal**:

    * Jika nomor urut tidak valid, program akan menampilkan pesan kesalahan.

    * Jika input umur tidak valid (bukan angka), program akan menampilkan pesan kesalahan dan tidak mengubah umur tanaman tersebut.

### 5. Hapus Tanaman (Delete)

* **Skenario Sukses**:

    * Program menampilkan daftar tanaman dan meminta nomor urut yang akan dihapus.

    * Jika nomor valid, tanaman akan dihapus dari `ArrayList`.

* **Skenario Gagal**: Jika nomor urut tidak valid, program akan menampilkan pesan kesalahan.

### 6. Cari Tanaman (Search)

* **Skenario Sukses**:

    * Pengguna memasukkan kata kunci nama tanaman.

    * Program akan menampilkan semua tanaman yang namanya mengandung kata kunci tersebut.

* **Skenario Gagal**: Jika tidak ada tanaman yang cocok dengan kata kunci, program akan menampilkan pesan bahwa tanaman tidak ditemukan.

## Contoh Output

Berikut adalah contoh interaksi pengguna dengan program:

**Contoh Input Tambah Tanaman:**

* Ketika `umur` diisi dengan angka:


* Ketika `umur` diisi dengan non-angka:


**Contoh Output Lihat Tanaman:**

* Jika daftar kosong:


* Jika daftar terisi:


**Contoh Output Ubah Tanaman:**

* Ketika nomor valid:


* Ketika nomor tidak valid:


**Contoh Output Hapus Tanaman:**

* Ketika nomor valid:


* Ketika nomor tidak valid:


**Contoh Output Cari Tanaman:**

* Ketika keyword ditemukan:


* Ketika keyword tidak ditemukan:


**Contoh Output Keluar Program:**

* Program akan menampilkan pesan terima kasih dan berhenti.
