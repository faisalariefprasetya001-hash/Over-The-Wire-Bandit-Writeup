# OverTheWire Bandit: Level 12 → Level 13

## 🎯 Tujuan
Tujuan dari level ini adalah menemukan password untuk mengakses Bandit 13. Ini adalah salah satu level yang paling menantang di awal! File `data.txt` yang berisi password telah diubah menjadi bentuk *hexdump*, lalu dikompresi berulang-ulang menggunakan berbagai program arsip (gzip, bzip2, tar). Anda harus merekonstruksi file tersebut dan mengekstraknya berkali-kali layaknya boneka Matryoshka.

## 🔐 Kredensial Login
- **Host:** `bandit.labs.overthewire.org`
- **Port:** `2220`
- **Username:** `bandit12`
- **Password:** `GROozWPO8QyN0mGrjUkID0WCYkZiQxrN` Password Dari Mesin Bandit Level 11

## 🛠️ Langkah Penyelesaian

1. **Membuat Direktori Kerja Sementara (Workspace)**
   
  Karena kita akan menghasilkan banyak file ekstraksi di level ini, aturan terbaiknya adalah membuat folder sementara di direktori /tmp agar tidak mengotori direktori utama, lalu salin file target ke sana.
  <img width="582" height="137" alt="1_yVoWyPVbcRVqDfaAj6agng" src="https://github.com/user-attachments/assets/694852ce-12cf-4bc3-b731-8887c042525f" />

2. **Mengubah Hex Dump Kembali ke File Biner**

   File `data.txt` saat ini masih berbentuk teks hex dump. Kita harus mengembalikannya menjadi file biner murni menggunakan perintah `xxd -r`:
   <img width="710" height="162" alt="1_meoiJNIQ_pr01RxaUnxjiQ" src="https://github.com/user-attachments/assets/f5aa3b0a-9f37-4c6e-bb1c-a3a605b082d0" />

3. **Melakukan Proses Dekompresi Bertingkat**
 
   Mulai dari sini, kita akan melakukan pola berulang: Cek tipe file dengan file ➡️ Ubah ekstensi dengan mv ➡️ Ekstrak file. Mari kita kupas tiap lapisannya:

4. **Lapisan 1: Gzip**

   Ketik `file data.bin` untuk mengecek tipenya. Karena terdeteksi sebagai `gzip`, kita ubah ekensinya dan ekstrak:
   
   <img width="1100" height="128" alt="1_JxAjeFc7gYh0q75sq3D0jQ" src="https://github.com/user-attachments/assets/7124f502-77b7-4be8-9c12-b326ac9cf9da" />

6. **Lapisan 2: Bzip2**

   Ketik file data. Terdeteksi sebagai `bzip2`:
   
   <img width="630" height="127" alt="1_yS3NjN8RdLIb1mJOewBKyg" src="https://github.com/user-attachments/assets/a56a2a49-3cbb-4845-94f5-6d11907ba928" />

8. **Lapisan 3: Gzip**

   Ketik `file data`. Terdeteksi sebagai `gzip`:
   
   <img width="927" height="152" alt="1_lL40Ao_mzPppnOapILs1Hw" src="https://github.com/user-attachments/assets/db0918ed-3176-462e-b988-00e0614f8e07" />

10. **Lapisan 4: Tar Archive**

   Ketik `file data`. Terdeteksi sebagai `POSIX tar archive`:
   
   <img width="605" height="162" alt="1_WDJm0j7agW-ddEnMihBm6Q" src="https://github.com/user-attachments/assets/f2687909-01a7-4586-a80d-1803c0c640dc" />
   
   (Setelah diekstrak, jalankan `ls` untuk melihat file baru yang muncul, yaitu `data5.bin`)

11. **Lapisan 5: Tar Archive**

   Ketik `file data5.bin`. Terdeteksi sebagai `POSIX tar archive`:
   
   <img width="682" height="127" alt="1_i55YFcvd170EAzO-wCcMkg" src="https://github.com/user-attachments/assets/3a5c7049-4e36-4d4d-b1f6-ba8122024d92" />
   
   (Akan muncul file baru bernama `data6.bin`)

11. **Lapisan 6: Bzip2**

   Ketik file `data6.bin`. Terdeteksi sebagai `bzip2`:
   
   <img width="667" height="117" alt="1_jlP_VPsYfgNZknVCovmJMQ" src="https://github.com/user-attachments/assets/ef72f448-cb4f-4bd3-8acf-45c47ebcf9ae" />

11. **Lapisan 7: Tar Archive**
    
    Ketik `file data6`. Terdeteksi sebagai `POSIX tar archive`:
    
    <img width="640" height="162" alt="1_D_Cc1Lv6l5s2M-s5nlpbUQ" src="https://github.com/user-attachments/assets/4c853eee-ef9b-49f8-ad40-a6ff8b374f5c" />

     (Akan muncul file baru bernama `data8.bin`)

13. **Lapisan 8: Gzip (Lapisan Terakhir)**
    
    Ketik `ile data8.bin`. Terdeteksi sebagai `gzip`:
    
    <img width="947" height="207" alt="1_FIjvJqBbvxQtUmAfk-cNcQ" src="https://github.com/user-attachments/assets/f8d276fe-f32b-4995-9b28-3edd15969a2f" />

15. **Membaca Password Level 13**
    
    Setelah melewati 8 lapisan kompresi, mari kita periksa tipe file hasil ekstraksi terakhir bernama data:
    
    <img width="545" height="77" alt="1_xgwxILRzZvZb85G8IQcTYg" src="https://github.com/user-attachments/assets/0d09c42b-eb9e-4e5f-a222-672ac8b159e1" />
    
    Akhirnya! File tersebut sudah kembali menjadi file teks biasa (`ASCII text`). Sekarang kita tinggal membacanya menggunakan perintah `cat`:
    
    <img width="596" height="82" alt="1_BvgA3BsQAWJaSfMT-Z3VlA" src="https://github.com/user-attachments/assets/1b316d7c-e166-4d6a-b219-9fa138ea109d" />

17. **Menutup Sesi**
    
    Salin password, lalu keluar dari server.
    ```bash
    bandit12@bandit:/tmp/workfaisal$ exit
    ```
## 📖 Penjelasan Perintah
  - `mktemp -d` : Membuat direktori (folder) sementara secara aman di dalam sistem dengan nama yang diacak.

  - `cp ~/data.txt .` : Menyalin file `data.txt` dari home directory (`~`) ke direktori saat ini (`.`).

  - `xxd -r` : xxd biasanya digunakan untuk mengubah file menjadi format hexdump (representasi heksadesimal). Parameter `-r` (reverse) membalikkan proses tersebut dari bentuk heksadesimal kembali ke bentuk biner asli.

  - `file` : Digunakan untuk mengecek jenis file yang tersembunyi.

  - `gzip -d` & `bzip2 -d` : Perintah dekompresi. `-d` berarti decompress. Program ini mewajibkan file memiliki ekstensi yang benar (`.gz` atau `.bz2`) agar mau bekerja.

  - `tar -xf` : Mengekstrak (extract file) dari arsip berformat tar.

## 🚩 Flag / Password Level 13
  Password Untuk Login Ke Mesin Bandit Level 13
  - qQYQiHOBPR8zR61qxYqX45quvihF2uzk
