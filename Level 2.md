# OverTheWire Bandit: Level 2 → Level 3

## 🎯 Tujuan
Tujuan dari level ini adalah menemukan password untuk mengakses Bandit 3. Password tersebut disimpan di dalam sebuah file bernama `spaces in this filename` yang terletak di *home directory*.

## 🔐 Kredensial Login
- **Host:** `bandit.labs.overthewire.org`
- **Port:** `2220`
- **Username:** `bandit2`
- **Password:** `PK8fYLZg2hnHSz83plBL1iEPKdD3QToB` Password Dari Mesin Bandit Level 1

## 🛠️ Langkah Penyelesaian

1. **Membuat Koneksi SSH**
   
   Masuk ke server menggunakan kredensial `bandit2`.
   ```bash
   ssh bandit2@bandit.labs.overthewire.org -p 2220
2. **Melihat Isi Direktori**
   
   Periksa file yang ada di direktori saat ini.
   
   <img width="446" height="67" alt="1_nEPm4Ka3UmMx605vHKXLDw" src="https://github.com/user-attachments/assets/adb210fc-67bb-41b5-962c-512c5b811897" />

3. **Membaca File dengan Spasi**

   Di Linux, spasi digunakan untuk memisahkan antar perintah atau argumen. Jika Anda mengetik `cat --spaces in this filename--`, sistem akan mengira Anda menyuruhnya membaca empat file yang berbeda (file `--spaces`, file `in`, file `this`, dan file `filename--`).

   Untuk membaca file yang memiliki spasi pada namanya

    <img width="720" height="87" alt="1_cq3Ck7iaqcM7Vrv4N3tR7Q" src="https://github.com/user-attachments/assets/5493cbf6-6e47-46d1-b5c5-11d177048982" />

4. **Menutup Sesi**

   Salin password, lalu keluar dari server.
   ```bash
   bandit2@bandit:~$ exit
   ```

## 🚩 Flag / Password Level 3

    Password Untuk Login Mesin Bandit Level 3
 - 7ZZ2LFrykP2zEyvBl4m3clcL7tGYJPME
