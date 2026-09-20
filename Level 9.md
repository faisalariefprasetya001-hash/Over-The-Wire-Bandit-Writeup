# OverTheWire Bandit: Level 9 → Level 10

## 🎯 Tujuan
Tujuan dari level ini adalah menemukan password untuk mengakses Bandit 10. Password tersebut disembunyikan di dalam file `data.txt`. Berbeda dengan sebelumnya, file ini berisi data biner acak, dan passwordnya adalah salah satu dari sedikit teks yang bisa dibaca manusia (*human-readable string*) yang diawali dengan beberapa karakter sama dengan (`=`).

## 🔐 Kredensial Login
- **Host:** `bandit.labs.overthewire.org`
- **Port:** `2220`
- **Username:** `bandit9`
- **Password:** `EjmOSvuAu7sGAHqHVcBDPirRe9T03kxl` Password Dari Mesin Bandit 8

## 🛠️ Langkah Penyelesaian

1. **Membuat Koneksi SSH**
   
   Masuk ke server menggunakan kredensial `bandit9`.
   ```bash
   ssh bandit9@bandit.labs.overthewire.org -p 2220

2. **Memeriksa File di Direktori**

   kita pastikan file target ada di tempatnya menggunakan perintah ls
   ```bash
   bandit9@bandit:~$ ls
   data.txt
   ```
   <img width="419" height="91" alt="1_CD_0eKzz2epBqsVVq1Y1Dw" src="https://github.com/user-attachments/assets/3c2d41fa-6250-4c5a-a4cc-ef513ce4dafa" />

3. **Mengekstrak Teks yang Dapat Dibaca**

   Jika Anda menggunakan `cat data.txt`, terminal Anda akan berantakan karena mencoba mencetak karakter biner. Kita harus menggunakan perintah `strings` untuk hanya mengekstrak teks biasa, lalu mengirimkan hasilnya (menggunakan pipe `|`) ke `grep` untuk mencari baris yang mengandung tanda sama dengan (`=`).
   ```bash
   bandit9@bandit:~$ strings data.txt | grep "=="
   ```
   <img width="587" height="167" alt="1_ErfJHqb0_9ZYgjQwIiyCTg" src="https://github.com/user-attachments/assets/a046d5e2-71bd-4ede-a955-fb1865ca2eb6" />

4. **Menutup Sesi**

   Salin password yang ditemukan, lalu keluar dari server.
   ```bash
   bandit9@bandit:~$ exit
   ```

## 📖 Penjelasan Perintah
  - `strings` : Perintah yang digunakan untuk mencari dan mencetak urutan karakter yang bisa dibaca (ASCII) dari dalam sebuah file data/biner. Ini adalah salah satu alat investigasi dasar (forensic) yang sangat sering digunakan oleh analis keamanan untuk membedah file yang tidak diketahui jenisnya atau malware.

  - `|` (Pipe) : Meneruskan hasil teks dari perintah `strings` ke perintah `grep`.

  - `grep "=="` : Menyaring dan hanya menampilkan baris yang memiliki beberapa tanda sama dengan (`=`) berjejer, sesuai dengan petunjuk level ini.

## 🚩 Flag / Password Level 10
   Password Untuk Login Ke Mesin Bandit Level 10
   - B0s2khmbT9u0geKuOoVGW3JZKhndE3BG
