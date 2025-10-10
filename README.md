# Manajemen Koleksi Tanaman

## Deskripsi Proyek
Proyek ini adalah aplikasi konsol sederhana berbasis **Java** yang berfungsi untuk mengelola koleksi tanaman.  
Pengguna dapat melakukan operasi dasar **CRUD** (Create, Read, Update, Delete) serta mencari data tanaman dalam koleksi.  

Aplikasi ini dibangun untuk mendemonstrasikan penerapan konsep-konsep dasar **Pemrograman Berorientasi Objek (PBO)**.  

---

## Konsep PBO yang Diterapkan

1. **Encapsulation (Enkapsulasi)**  
   Setiap kelas model (`TanamanModel`, `TanamanHias`, `TanamanBuah`) memiliki atribut `private`.  
   Akses dan modifikasi data hanya melalui **getter** dan **setter**, sehingga integritas data lebih terjaga.  

2. **Inheritance (Pewarisan)**  
   `TanamanModel` berfungsi sebagai **superclass** (kelas induk).  
   `TanamanHias` dan `TanamanBuah` adalah **subclass** yang mewarisi atribut dan metode dari `TanamanModel`.  
   Masing-masing subclass memiliki atribut tambahan, misalnya:  
   - `TanamanHias` → `warnaBunga`  
   - `TanamanBuah` → `musimPanen`  

3. **Overriding (Penimpaan)**  
   Metode `tampilkanInfo()` ditimpa (override) di `TanamanHias` dan `TanamanBuah`.  
   Dengan overriding, setiap subclass dapat menampilkan informasi unik sesuai jenis tanaman masing-masing.  

---

## Struktur Proyek

<img width="483" height="487" alt="image" src="https://github.com/user-attachments/assets/59c0532b-794e-4aae-a4cf-2db88fa39b7e" />


## Fitur & Contoh Input/Output

- **Tampilan Menu Utama**  
  User diberikan 6 pilihan menu: Tambah Tanaman, Lihat Tanaman, Ubah Tanaman, Hapus Tanaman, Cari Tanaman, atau Keluar.  

<img width="660" height="422" alt="image" src="https://github.com/user-attachments/assets/d0022fd9-41b8-4cef-96a8-6f8120d66257" />


- **Tambah Tanaman (Create)**
  Skenario Sukses:

   -Pengguna memilih 1. Tambah Tanaman.
   -Program meminta pengguna untuk memilih jenis tanaman (Hias atau Buah).
   -Setelah jenis dipilih, pengguna diminta untuk memasukkan detail (nama, jenis, umur).
   -Untuk TanamanHias, diminta warnaBunga. Untuk TanamanBuah, diminta musimPanen.
   -Setelah semua input valid, data akan disimpan ke ArrayList.

  
<img width="564" height="466" alt="image" src="https://github.com/user-attachments/assets/d0f2def6-a448-49c7-9b21-e6295e416d77" />


---

Skenario Gagal:

Jika pengguna memasukkan input non-angka untuk umur, program akan menampilkan pesan kesalahan dan melakukan looping hingga input yang benar diberikan.

<img width="621" height="221" alt="image" src="https://github.com/user-attachments/assets/09f62a80-0a05-4734-b3f5-ec2e670a90b0" />


- **Lihat Tanaman (Read)**  
  - Jika daftar kosong → tampil pesan *"Belum ada tanaman"*.
    
    <img width="431" height="462" alt="image" src="https://github.com/user-attachments/assets/d29d0b82-a2a0-4b65-bc32-daf507557c2b" />
    
  - Jika ada → tampil semua tanaman dengan format:

   <img width="459" height="670" alt="image" src="https://github.com/user-attachments/assets/a6da8373-f8a6-4235-923a-36597aa11e9a" />


- **Ubah Tanaman (Update)**  
  - Cari tanaman berdasarkan nomor urut.  
  - Jika ketemu → user bisa mengganti data tanaman di koleksi.
  - User bisa mengupdate data dari suatu tanaman yang sudah dimasuki dengan cara memasuki menginput Nama, Jenis, Umur baru, dll untuk tanaman tersebut
 
    <img width="557" height="675" alt="image" src="https://github.com/user-attachments/assets/6e5d18ba-92e5-4736-8fa1-ab4d1da47532" />
 
    ---

    <img width="340" height="138" alt="image" src="https://github.com/user-attachments/assets/1dd2c9ad-b8fe-4427-bcb6-6238ff2fe906" />


    
  - Jika tidak → tampil pesan *"Tanaman tidak ditemukan"*.
 
    <img width="589" height="443" alt="image" src="https://github.com/user-attachments/assets/ab18e1e8-a543-44b6-b440-530aa4cbc643" />

- **Hapus Tanaman (Delete)**  
  - Cari tanaman berdasarkan nomor urut.  
  - Jika ketemu → tanaman dapat dihapus dari daftar.
  - Dengan user memasukan nomor tanaman yang ingin di hapus
 
   <img width="554" height="705" alt="image" src="https://github.com/user-attachments/assets/ab53d107-82cc-4ebe-a367-4baebc962552" />


  - Jika tidak ditemukan → tampil pesan *"Nomor tidak valid"*.
    
   <img width="472" height="224" alt="image" src="https://github.com/user-attachments/assets/ed9975e8-a2ad-4b1c-b2a9-dfd8a7fca1e3" />

- **Cari Tanaman (Search)**  
  - User memasukkan keyword nama.  
  - Jika ada → tampil data tanaman yang sesuai.
    
    <img width="393" height="289" alt="image" src="https://github.com/user-attachments/assets/bf05cde4-c9d4-4212-9877-3e72a373d74f" />


  - Jika tidak → tampil pesan *"Tanaman tidak ditemukan"*.
 
    <img width="402" height="216" alt="image" src="https://github.com/user-attachments/assets/c5f6504c-e78e-48ba-b968-f572c9900ee1" />

- **Keluar Program**  
  Program berhenti saat user memilih menu `6`.
  
   <img width="462" height="177" alt="image" src="https://github.com/user-attachments/assets/8b0c057c-e4c5-45a7-ad84-ef4c7f43f3d4" />



# Program Koleksi Tanaman 

Program ini adalah aplikasi konsol Java sederhana untuk mengelola koleksi tanaman. Program ini dirancang dengan menerapkan konsep Object-Oriented Programming  seperti Abstraksi dan Polimorfisme.

### Abstraction
Program ini menerapkan **Abstraksi** melalui penggunaan **Abstract Class**.

<img width="780" height="343" alt="image" src="https://github.com/user-attachments/assets/8eba7260-686f-4de4-844c-8f7a7393a9b3" />
<img width="610" height="77" alt="image" src="https://github.com/user-attachments/assets/fbba6a03-1626-4dd2-bfe5-f6b2a5b0da6b" />


* **`abstract class TanamanModel`**: Kelas ini berfungsi sebagai fondasi untuk semua jenis tanaman. Kelas ini tidak dapat diinstansiasi secara langsung karena merepresentasikan konsep umum "tanaman".
    * Method `tampilkanInfo()` dideklarasikan sebagai `abstract`, yang memaksa semua kelas turunannya (`TanamanHias` dan `TanamanBuah`) untuk menyediakan implementasi spesifik dari method ini.

### Polymorphism
Polymorphism diterapkan dalam program ini melalui **Method Overloading** dan **Method Overriding**.

<img width="1286" height="436" alt="image" src="https://github.com/user-attachments/assets/e6cd1a95-b1e9-4340-91a3-ab035c906a6e" />

* **Overloading**: Ditemukan pada method `setUmur()` di dalam `abstract class TanamanModel`.
    * `setUmur(int umur)`: Digunakan untuk mengubah umur tanaman dengan input angka.
    * `setUmur(String umurStr)`: Digunakan untuk mengubah umur tanaman dengan input string. Method ini akan memproses input string dan mengonversinya menjadi angka secara aman.

<img width="836" height="235" alt="image" src="https://github.com/user-attachments/assets/41bc0ae9-dda7-475e-a397-5ebe1a6632ba" />

<img width="897" height="247" alt="image" src="https://github.com/user-attachments/assets/7d6957b8-734e-411d-9ae5-d0904f6d2faf" />


* **Overriding**: Ditemukan pada dua kelas turunan dari `TanamanModel`.
    * **`tampilkanInfo()` di kelas `TanamanHias`**: Method ini meng-override `tampilkanInfo()` dari kelas induknya (`TanamanModel`). Implementasinya menambahkan detail spesifik tentang tanaman hias, yaitu `warnaBunga`.
    * **`tampilkanInfo()` di kelas `TanamanBuah`**: Sama seperti `TanamanHias`, method ini meng-override method dari kelas induknya untuk menampilkan informasi yang unik untuk tanaman buah, yaitu `musimPanen`.


## Implementasi Koneksi Database

### *1. Letak Penerapan JDBC (Java Database Connectivity)*

* JDBC diterapkan di kelas TampilanDataJDBC.java.
* Kelas ini dibuat khusus untuk memenuhi persyaratan tugas, yaitu menampilkan data awal dari database menggunakan object Statement

### *2. Letak Penerapan ORM (Object-Relational Mapping)*

* ORM diterapkan di kelas TanamanRepository.java.
* Kelas ini berfungsi sebagai lapisan ORM, menerjemahkan Objek Java menjadi query SQL (INSERT, UPDATE, DELETE) dan mengambil hasil SQL untuk dijadikan objek Java.

### *3. File SQL

* data pertama sql

  <img width="1919" height="970" alt="Screenshot 2025-10-10 220014" src="https://github.com/user-attachments/assets/c804c8ac-9d70-4a92-a9c0-971b0ad15e8b" />





   




