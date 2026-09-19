# OverTheWire Bandit: Level 3 → Level 4

## 🎯 Tujuan
Tujuan dari level ini adalah menemukan password untuk mengakses Bandit 4. Password tersebut disimpan di dalam sebuah file tersembunyi (*hidden file*) yang berada di dalam direktori `inhere`.

## 🔐 Kredensial Login
- **Host:** `bandit.labs.overthewire.org`
- **Port:** `2220`
- **Username:** `bandit3`
- **Password:** `7ZZ2LFrykP2zEyvBl4m3clcL7tGYJPME` Password Dari Mesin Bandit Level 2

## 🛠️ Langkah Penyelesaian

1. **Membuat Koneksi SSH**
   Masuk ke server menggunakan kredensial `bandit3`.
   ```bash
   
   ssh bandit3@bandit.labs.overthewire.org -p 2220

2. **Melihat Isi Direktori Awal**

   Periksa apa yang ada di direktori saat ini.
   ```bash
   bandit3@bandit:~$ ls
   inhere
   ```
   <img width="397" height="61" alt="1_qMGATs-LqA7b0btPki__-g" src="https://github.com/user-attachments/assets/4c2e4f24-0ef1-4e10-8625-cf0967b23c8c" />

   Terdapat sebuah folder/direktori bernama inhere.

3. **Berpindah ke dalam Direktori inhere**

   Gunakan perintah `cd` untuk masuk ke dalam folder tersebut.
   ```bash
   bandit3@bandit:~$ cd inhere
   ```
   <img width="397" height="107" alt="1_WL3vUcUwGAAtjsX7NR64ow" src="https://github.com/user-attachments/assets/4e74adb6-7eba-401d-9c89-9291f385f328" />

4. **Mencari File Tersembunyi**

   Jika Anda hanya mengetik `ls`, terminal tidak akan menampilkan apa-apa karena filenya disembunyikan. Gunakan flag `-a` (all) untuk melihat semua file, termasuk yang tersembunyi.

   ```Bash
   bandit3@bandit:~/inhere$ ls -a
   .  ..  ...hidden
   ```
   <img width="442" height="66" alt="1_puN8TByCc_Lg1Xa-1j-1VQ" src="https://github.com/user-attachments/assets/84282940-a8f8-40fb-92a8-a8347bc54009" />

5. **Membaca File Tersembunyi**

   Di Linux, file yang namanya diawali dengan tanda titik (`.`) adalah file tersembunyi. Gunakan `cat` untuk membaca file `...hidden` tersebut.

   ```bash
   bandit3@bandit:~/inhere$ cat ...hidden
   ```
   <img width="597" height="77" alt="1_hMjgUSO6X853oJi6mKgC7A" src="https://github.com/user-attachments/assets/08102163-0027-4728-bca7-b69e45e7702a" />

6. **Menutup Sesi**

   Salin password, lalu keluar dari server.

   ```bash
   bandit3@bandit:~/inhere$ exit
   ```
## 📖 Penjelasan Perintah

  - `cd` (Change Directory): Perintah dasar untuk berpindah dari satu folder ke folder lainnya.
  - `ls -a` (List All): Menambahkan parameter `-a` pada perintah `ls` akan memaksa sistem untuk menampilkan semua file, termasuk file atau folder sistem yang disembunyikan (yang selalu diawali dengan tanda titik `.`).

## 🚩 Flag / Password Level 4
  Password Untuk Login Ke Mesin Bandit Level 4
   - xzTXq1rDJQVVAzdv5cHq1TQytTWufAMq 
