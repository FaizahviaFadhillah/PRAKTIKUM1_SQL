### SQL DDL (Data Definiton Language)

## TUGAS PRAKTIKUM 1

# 1. Buat sebuah database dengan nama latihan2!
untuk membuat sebuah databses gunakan query `CREATE DATABASE nama_database;`
```sql
CREATE DATABASE latihan2;
``` 

Contoh Dan Hasilnya:
![img.1](gambar/img%201.png)

# 2. Buat sebuah tabel dengan nama biodata (nama, alamat) didalam database latihan2!

* sebelum membuat sebuah tabel, pastikan dahulu kita sudah menggunakan perintah `USE latihan2;` untuk masuk kedalam database.

contoh Dan Hasilnya: 
![img.2](gambar/img%202.png)

* Selanjutnya membuat tabel dengan nama biodata (nama, alamat)
```sql
CREATE TABLE biodata (
    nama VARCHAR(50),
    alamat VARCHAR(100)
);
```

Contoh Dan Hasilnya:
![img.3](gambar/img%203.png)

# 3. Tambahkan sebuah kolom keterangan (varchar 15), sebagai kolom terakhir!
```sql
ALTER TABLE biodata ADD keterangan VARCHAR(15);
```

Contoh Dan Hasilnya: 
![img.4](gambar/img%204.png)

# 4. Tambahkan kolom id (int 11) di awal (sebagai kolom pertama)!
Terdapat tambahan query pada saat kita meletakan kolom baru di awal, dengan menggunakan query `FIRST`.
```sql 
ALTER TABLE biodata ADD id INT(11) FIRST;
```

Contoh Dan Hasilnya:
![img.5](gambar/img%205.png)

# 5. Sisipkan sebuah kolom dengan nama phone (varchar 15) setelah kolom alamat!
Jika menambahkan sebuah kolom di antara kolom lain kita dapat menggunakan query `AFTER`.
```sql 
ALTER TABLE biodata ADD phone VARCHAR(15) AFTER alamat;
```

Contoh Dan Hasilnya:
![img.6](gambar/img%206.png)

# 6. Ubah tipe data kolom id menjadi char(11)!
Jika mengubah tipe data, kita dapat menggunakan query `MODIFY`.
```sql
ALTER TABLE biodata MODIFY id CHAR(11);
```

Contoh Dan Hasilnya:
![img.7](gambar/img%207.png)

# 7. Ubah nama kolom phone menjadi hp (varchar 20)!
Jika mengubah nama pada sebuah kolom, kita dapat menggunakan query `CHANGE`.
```sql
ALTER TABLE biodata CHANGE phone hp VARCHAR(20);
```

Contoh Dan Hasilnya:
![img.8](gambar/img%208.png)

# 8. Tambahkan kolom email setelah kolom hp!
Jika menambahkan sebuah kolom di antara kolom lain kita dapat menggunakan query `AFTER`.
```sql
ALTER TABLE biodata ADD email VARCHAR(50) AFTER hp;
```

Contoh Dan Hasilnya:
![img.9](gambar/img%209.png)

# 9. Hapus kolom keterangan dari tabel!
Jika ingin menghapus kolom, kita dapat memasukan query `DROP`.
```sql
ALTER TABLE biodata DROP keterangan;
```

Contoh Dan Hasilnya:
![img.10](gambar/img%2010.png)

# 10. Ganti nama tabel menjadi data_mahasiswa!
Jika ingin mengganti nama sebuah tabel, kita dapat menggunakan query `RENAME`.
```sql
RENAME TABLE biodata TO data_mahasiswa;
```

Contoh Dan Hasilnya:
![img.11](gambar/img%2011.png)

# 11. Ganti nama field id menjadi nim
```sql
ALTER TABLE data_mahasiswa CHANGE id nim CHAR(11);
```

Contoh Dan Hasilnya:
![img.12](gambar/img%2012.png)

# 12. Jadikan nim sebagai PRIMARY KEY
Jika ingin menjadikan sebuah field sebagai primary key, kita dapat sertakan query `ADD PRIMARY KEY`.
```sql 
ALTER TABLE data_mahasiswa ADD PRIMARY KEY (nim);
``` 

Contoh Dan Hasilnya:
![img.13](gambar/img%2013.png)

# 13. Jadikan kolom email sebagai UNIQUE KEY
```sql
ALTER TABLE data_mahasiswa ADD UNIQUE (email);
```

Contoh Dan Hasilnya:
![img.14](gambar/img%2014.png)

## EVALUSI 

#  Menuliskan Semua Perintah-Perintah SQL Percobaan 

1. Membuat Database
`CREATE DATABASE latihan1;`
Contoh Dan Hasilnya:
![img.15](gambar/img%2015.png)

2. Membuat Table
`CREATE TABLE siswa (nama VARCHAR(100), alamat TEXT);`
Contoh Dan Hasilnya:
![img.16](gambar/img%2016.png)

3. Menambah Kolom
`ALTER TABLE siswa ADD COLUMN keterangan TEXT AFTER alamat;`
Contoh Dan Hasilnya:
![img.17](gambar/img%2017.png)

4. Menambah kolom diawal
`ALTER TABLE siswa ADD COLUMN id INT FIRST;`
Contoh dan Hasilnya:
![img.18](gambar/img%2018.png)

5. Mengubah nama kolom
`ALTER TABLE siswa CHANGE keterangan kelas VARCHAR(20);`
Contoh dan Hasilnya:
![img.19](gambar/img%2019.png)

6. Mengubah tipe data
`ALTER TABLE siswa MODIFY COLUMN kelas VARCHAR(20);`
Contoh Dan Hasilnya:
![img.20](gambar/img%2019.png)

7. Menghapus kolom
`ALTER TABLE siswa DROP COLUMN kelas;`
Contoh Dan Hasilnya:
![img.21](gambar/img%2020.png)

8. Menambah PRIMAY KEY id
`ALTER TABLE siswa ADD PRIMARY KEY(id);`
Contoh Dan Hasilnya:
![img.22](gambar/img%2022.png)

9. Menghapus Primary Key
`ALTER TABLE siswa DROP PRIMARY KEY;`
Contoh Dan Hasilnya:
![img.23](gambar/img%2023.png)

10. Menambahkan Constraint
`ALTER TABLE siswa ADD CONSTRAINT PK_siswa PRIMARY KEY(id);`
Contoh Dan Hasilnya:
![img.24](gambar/img%2024.png)

11. Menghapus Constraint Primary Key juga Bisa Seperti Ini:
`ALTER TABLE siswa DROP PRIMARY KEY;`
Contoh Dan Hasilnya:
![img.25](gambar/img%2025.png)

# Apa Maksud Dari int(11)?
int(11) adalah tipe data kolom dalam basis data MySQL yang menunjukkan bahwa kolom tersebut adalah tipe data bilangan bulat (integer) dengan panjang maksimum 11 digit.

# Ketika kita melihat struktur tabel dengan perintah desc, ada kolom Null yang berisi Yes dan No. Apa maksudnya ?
* Jika "Null" ditetapkan sebagai "YES", itu berarti kolom tersebut dapat memiliki nilai "NULL" atau kosong. Artinya, saat kita memasukkan data ke dalam tabel, kita dapat memasukkan nilai NULL ke dalam kolom tersebut jika perlu.
* Jika "Null" ditetapkan sebagai "NO", itu berarti kolom tersebut tidak dapat memiliki nilai "NULL" atau kosong. Oleh karena itu, setiap kali kita memasukkan data ke dalam tabel, kita harus memberikan nilai untuk kolom tersebut, tidak boleh kosong.