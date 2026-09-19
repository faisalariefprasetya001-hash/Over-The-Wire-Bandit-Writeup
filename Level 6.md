# OverTheWire Bandit: Level 6 → Level 7

## 🎯 Tujuan
Tujuan dari level ini adalah menemukan password untuk mengakses Bandit 7. Berbeda dengan level-level sebelumnya, file password kali ini **tidak** berada di *home directory*, melainkan tersembunyi entah di mana di seluruh sistem server. 

Kita diberikan tiga petunjuk spesifik mengenai file tersebut:
1. Dimiliki oleh *user* `bandit7`
2. Dimiliki oleh *group* `bandit6`
3. Ukurannya tepat **33 bytes**

## 🔐 Kredensial Login
- **Host:** `bandit.labs.overthewire.org`
- **Port:** `2220`
- **Username:** `bandit6`
- **Password:** `pXa26xhMWaC2SvDotA4r9EgZkulOeSBW` Password Dari Mesin Bandit Level 5

## 🛠️ Langkah Penyelesaian

1. **Membuat Koneksi SSH**
   
   Masuk ke server menggunakan kredensial `bandit6`.
   ```bash
   ssh bandit6@bandit.labs.overthewire.org -p 2220

2. **Mencari File di Seluruh Sistem**

   Karena file bisa berada di mana saja, kita harus memulai pencarian dari root directory (direktori paling dasar di Linux, dilambangkan dengan `/`).

   Jika kita hanya menjalankan `find / -user bandit7 -group bandit6 -size 33c`, layar terminal kita akan dipenuhi oleh pesan Permission denied (Akses ditolak) karena kita mencoba membaca folder sistem milik administrator (root).

   Untuk menyembunyikan pesan error tersebut dan hanya menampilkan hasil pencarian yang berhasil, kita ta  mbahkan trik pengalihan error (`2>/dev/null`).
   ```bash
   bandit6@bandit:~$ find / -user bandit7 -group bandit6 -size 33c 2>/dev/null
   /var/lib/dpkg/info/bandit7.password
   ```
   <img width="947" height="150" alt="1_loX6pCj_SlWM0xa31MID7w" src="https://github.com/user-attachments/assets/843ea3db-7bbf-4e15-899a-b8f2d2336f32" />
   Terminal menunjukkan bahwa file tersebut berada di direktori `/var/lib/dpkg/info/`.

3. **Membaca File yang Ditemukan**

   Gunakan perintah `cat` untuk membaca file berdasarkan absolute path yang ditemukan.
   ```bash
   bandit6@bandit:~$ cat /var/lib/dpkg/info/bandit7.password
   ```
   <img width="707" height="102" alt="1_7TRDcAfCER2pjJCQrGnQHw" src="https://github.com/user-attachments/assets/925fe74f-9e4c-419b-916f-b6114466f62d" />

4. **Menutup Sesi**

   Salin password, lalu keluar dari server.
   ```bash
   bandit6@bandit:~$ exit
   ```

## 📖 Penjelasan Perintah

  - `find /` : Memulai pencarian secara menyeluruh dari direktori akar (root) sistem operasi.
  - `-user bandit7` : Kriteria pencarian untuk file yang pemiliknya (owner) adalah user `bandit7`.
  - `-group bandit6` : Kriteria pencarian untuk file yang grup pemiliknya adalah `bandit6`.
  - `-size 33c` : Kriteria pencarian untuk file berukuran tepat 33 bytes.
  - `2>/dev/null` : Ini adalah teknik redirection (pengalihan) di Linux.

## Flag / Password Level 7
  Password Untuk Login Ke Mesin Bandit 7
  - Bmnnvf82KzQlfxgAI2d1zYbr1u9pr3E3
