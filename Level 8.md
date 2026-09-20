# OverTheWire Bandit: Level 8 → Level 9

## 🎯 Tujuan
Tujuan dari level ini adalah menemukan password untuk mengakses Bandit 9. Password tersebut disimpan di dalam file `data.txt` dan merupakan **satu-satunya baris teks yang tidak memiliki duplikat** (hanya muncul tepat satu kali di dalam file tersebut).

## 🔐 Kredensial Login
- **Host:** `bandit.labs.overthewire.org`
- **Port:** `2220`
- **Username:** `bandit8`
- **Password:** `VR1ljMayciFxbnUokuQmJFw6QC9VKtub` Password Dari Mesin Bandit 7

## 🛠️ Langkah Penyelesaian

1. **Membuat Koneksi SSH**
   
   Masuk ke server menggunakan kredensial `bandit8`.
   ```bash
   ssh bandit8@bandit.labs.overthewire.org -p 2220

2. **Melihat Isi Direktori**
   
   Periksa file yang ada di direktori saat ini.
   ```bash
   bandit8@bandit:~$ ls
   data.txt
   ```
   <img width="302" height="77" alt="1_qPdniYY60QYlxXg6Ah7v6w" src="https://github.com/user-attachments/assets/01a32384-c797-4bae-93d0-3af142bf7ee1" />

3. **Mencari Baris Teks yang Unik**

   File `data.txt` berisi ribuan baris kata sandi acak yang diulang-ulang. Untuk mencari satu-satunya baris yang tidak memiliki duplikat, kita harus mengurutkan isi file tersebut terlebih dahulu, baru kemudian memfilternya. Kita akan menggunakan kombinasi perintah `sort` dan `uniq` yang dihubungkan dengan pipe (`|`).
   ```bash
   bandit8@bandit:~$ sort data.txt | uniq -u
   ```
   <img width="527" height="85" alt="1_Jwgt_UYd5ZSA93LC0glUGg" src="https://github.com/user-attachments/assets/a74372b0-def1-450d-bf0c-a6ae87d99d3e" />
   Terminal akan langsung menampilkan satu-satunya baris teks yang unik.

4. **Menutup Sesi**
   
   Salin password yang muncul, lalu keluar dari server.
   ```bash
   bandit8@bandit:~$ exit
   ```
## 📖 Penjelasan Perintah

   - `sort`: Perintah untuk mengurutkan baris teks di dalam file secara alfabetis. Ini adalah langkah wajib karena perintah `uniq` hanya bisa mendeteksi duplikat jika baris-baris yang sama letaknya bersebelahan.

   - `|` (Pipe) : Karakter garis vertikal ini berfungsi seperti pipa saluran. Ia mengambil output (hasil) dari perintah di sebelah kirinya (hasil dari `sort`), dan melemparnya sebagai input untuk perintah di sebelah kanannya (`uniq`).

   - `uniq` : Perintah untuk melaporkan atau menghapus baris yang berulang.

   - `-u` (Unique) : Parameter untuk perintah `uniq` yang menginstruksikan agar sistem hanya menampilkan baris yang benar-benar unik (tidak memiliki salinan/duplikat sama sekali).

## 🚩 Flag / Password Level 9     
  Password Untuk Login Ke Mesin Bandit 9
  - EjmOSvuAu7sGAHqHVcBDPirRe9T03kxl
