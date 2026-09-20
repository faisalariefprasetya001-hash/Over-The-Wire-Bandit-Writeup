# OverTheWire Bandit: Level 11 → Level 12

## 🎯 Tujuan
Tujuan dari level ini adalah menemukan password untuk mengakses Bandit 12. Password tersebut disimpan di dalam file `data.txt`, di mana semua huruf kapital dan huruf kecilnya telah disandikan menggunakan **ROT13** (diputar/digeser sebanyak 13 posisi pada alfabet).

## 🔐 Kredensial Login
- **Host:** `bandit.labs.overthewire.org`
- **Port:** `2220`
- **Username:** `bandit11`
- **Password:** `pYfOY6HwUsDj5rL9UvyhU7MCmv8vN5Ro` Password Dari Mesin Bandit Level 10

## 🛠️ Langkah Penyelesaian

1. **Membuat Koneksi SSH**
   
   Masuk ke server menggunakan kredensial `bandit11`.
   ```bash
   ssh bandit11@bandit.labs.overthewire.org -p 2220

2. **Melihat Isi File**
   
   Jika Anda membaca file dengan `cat data.txt`, Anda akan melihat teks yang tidak masuk akal seperti `Gur cnffjbeq vf....` Ini adalah teks yang sudah dikenakan ROT13.
   <img width="597" height="132" alt="1_VA9kg-j6IKMGEJ7Y7g0PYA" src="https://github.com/user-attachments/assets/4862eaa3-2406-417f-b6ca-27ef684faa7c" />

3. **Mendekode ROT13**
   
   Untuk mengembalikan huruf-huruf tersebut ke aslinya, kita menggunakan perintah `tr` (translate) untuk memetakan setiap huruf agar digeser kembali sebanyak 13 posisi.
   ```bash
   bandit11@bandit:~$ cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'
   ```
   <img width="785" height="180" alt="1_3n16sofrbZXRZZcaI8lLvw" src="https://github.com/user-attachments/assets/23128601-b1a0-4d78-a054-ea3026afe041" />

4. **Menutup Sesi**
   
   Salin password yang telah terbaca, lalu keluar dari server.
   ```bash
   bandit11@bandit:~$ exit
   ```

## 📖 Penjelasan Perintah
   - `ROT13` (Rotate by 13 places): Sebuah teknik enkripsi substitusi klasik yang sangat sederhana. Karena abjad memiliki 26 huruf, menggeser 13 posisi ke depan (A menjadi N) dan menggesernya 13 posisi lagi akan mengembalikan huruf tersebut ke bentuk aslinya (N menjadi A).

   - `tr` (Translate): Perintah yang digunakan untuk mengganti atau menghapus karakter tertentu.

## 🚩 Flag / Password Level 12
   Password Untuk Login Ke Mesin Bandit Level 12
   - GROozWPO8QyN0mGrjUkID0WCYkZiQxrN
