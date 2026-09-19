# OverTheWire Bandit: Level 4 → Level 5

## 🎯 Tujuan
Tujuan dari level ini adalah menemukan password untuk mengakses Bandit 5. Password tersebut disimpan di dalam satu-satunya file yang *human-readable* (berupa teks yang dapat dibaca manusia) yang terletak di dalam direktori `inhere`.

## 🔐 Kredensial Login
- **Host:** `bandit.labs.overthewire.org`
- **Port:** `2220`
- **Username:** `bandit4`
- **Password:** `xzTXq1rDJQVVAzdv5cHq1TQytTWufAMq` Password Dari Mesin Bandit Level 3

## 🛠️ Langkah Penyelesaian

1. **Membuat Koneksi SSH**
   
   Masuk ke server menggunakan kredensial `bandit4`.
   ```bash
   ssh bandit4@bandit.labs.overthewire.org -p 2220

2. **Berpindah ke Direktori Target**
   
    Masuk ke dalam folder `inhere` dan periksa daftar filenya.
   ```bash
   bandit4@bandit:~$ cd inhere
    bandit4@bandit:~/inhere$ ls
    -file00  -file02  -file04  -file06  -file08
    -file01  -file03  -file05  -file07  -file09
   ```
   <img width="1100" height="156" alt="1_7RMqlrQzy79EJWXNj59yYg" src="https://github.com/user-attachments/assets/8a8580d8-523f-4831-8db9-8f1a4f80fb27" />

3. **Mencari File Teks (Human-Readable)**
   
   Terdapat banyak file yang namanya diawali dengan tanda strip (`-`). Daripada menebak dan membukanya satu per satu, kita bisa menggunakan perintah `file` untuk mengecek tipe data dari setiap file.

    Karena nama filenya diawali dengan`-`, kita harus menggunakan `./` seperti pelajaran di Level 1. Untuk mengecek semuanya sekaligus, gunakan tanda bintang (`*`).
   ```bash
   bandit4@bandit:~/inhere$ file ./*
    ./-file00: data
    ./-file01: data
    ./-file02: data
    ./-file03: data
    ./-file04: data
    ./-file05: data
    ./-file06: data
    ./-file07: ASCII text
    ./-file08: data
    ./-file09: data
   ```
   <img width="802" height="282" alt="1_K3rNRgyaMSWdroR2l7Wctg" src="https://github.com/user-attachments/assets/c6a40934-4798-4fab-9350-b8d9b5b31182" />

    Dari hasil di atas, terlihat bahwa file07 adalah satu-satunya file teks (ASCII text), sedangkan yang lainnya berisi data acak.

4. **Membaca File Teks**

   Gunakan perintah cat untuk membaca isi dari file yang benar.
   ```bash
   bandit4@bandit:~/inhere$ cat ./-file07
   ```
   <img width="502" height="81" alt="1_xmVIWDp97fe6DCQAFUpN1Q" src="https://github.com/user-attachments/assets/322abbfb-fa6c-43a3-9b1e-2b0393d199e0" />

5. **Menutup Sesi**

   Salin password, lalu keluar dari server.
   ```bash
   bandit4@bandit:~/inhere$ exit
   ```

## 📖 Penjelasan Perintah

  - `file` : Perintah krusial dalam cybersecurity dan administrasi sistem Linux untuk mendeteksi jenis atau tipe dari suatu file berdasarkan isi kontennya (biasanya membaca magic bytes atau header file), bukan berdasarkan ekstensinya.
  - `*` (Asterisk / Wildcard) : Karakter pengganti yang mewakili "semua karakter" atau "semua file". Perintah `file ./*` berarti "tolong periksa tipe file dari semua file yang ada di dalam direktori saat ini".

## 🚩 Flag / Password Level 5
  Password Untuk Login ke Mesin Bandit Level 5
  - 6C7h9GD8M6ai5nr7wo1RonrzFjj9yIrG
  
