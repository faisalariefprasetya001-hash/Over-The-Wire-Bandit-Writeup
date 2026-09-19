# OverTheWire Bandit: Level 5 → Level 6

## 🎯 Tujuan
Tujuan dari level ini adalah menemukan password untuk mengakses Bandit 6. Password tersebut disimpan di dalam salah satu direktori di bawah `inhere`, namun kali ini kita diberikan petunjuk spesifik mengenai ciri-ciri file tersebut:
1. *Human-readable* (berupa teks yang bisa dibaca)
2. Ukurannya tepat **1033 bytes**
3. *Not executable* (tidak bisa dieksekusi/dijalankan sebagai program)

## 🔐 Kredensial Login
- **Host:** `bandit.labs.overthewire.org`
- **Port:** `2220`
- **Username:** `bandit5`
- **Password:** `6C7h9GD8M6ai5nr7wo1RonrzFjj9yIrG` Password Dari Mesin Bandit Level 4

## 🛠️ Langkah Penyelesaian

1. **Membuat Koneksi SSH**
   
   Masuk ke server menggunakan kredensial `bandit5`.
   ```bash
   ssh bandit5@bandit.labs.overthewire.org -p 2220

2. **Berpindah ke Direktori Target**

   Masuk ke dalam folder `inhere` dan periksa isinya.
   ```bash
   bandit5@bandit:~$ cd inhere
    bandit5@bandit:~/inhere$ ls
    maybehere00  maybehere04  maybehere08  maybehere12  maybehere16
    maybehere01  maybehere05  maybehere09  maybehere13  maybehere17
    maybehere02  maybehere06  maybehere10  maybehere14  maybehere18
    maybehere03  maybehere07  maybehere11  maybehere15  maybehere19
    ```
   <img width="1100" height="184" alt="1_DsaE0HnJQ9oI6gp8XBPsyg" src="https://github.com/user-attachments/assets/b12a31d4-cb67-4c6f-b501-5a7045f35437" />
    Kali ini terdapat banyak sekali folder, dan di dalam setiap folder tersebut terdapat banyak file. Mencari secara manual satu per satu sangat tidak efisien.

3. **Mencari File Berdasarkan Kriteria Spesifik**

   Kita akan menggunakan perintah `find` dipadukan dengan kriteria yang diberikan pada soal untuk menemukan file tersebut secara otomatis.
   ```bash
   bandit5@bandit:~/inhere$ find . -type f -size 1033c ! -executable
    ./maybehere07/.file2
   ```
   <img width="797" height="101" alt="1_l9jLjziJ-juvMUxyI95tgQ" src="https://github.com/user-attachments/assets/e01305d2-dee0-44a3-b706-820a0652e283" />
   Terminal langsung menunjukkan lokasi pasti dari file yang memenuhi ketiga kriteria tersebut, yaitu `.file2` di dalam folder `maybehere07`.

4. **Membaca File yang Ditemukan**

   Gunakan perintah `cat` untuk membaca file di lokasi yang telah ditemukan.
   ```bash
   bandit5@bandit:~/inhere$ cat ./maybehere07/.file2
   ```
   <img width="617" height="82" alt="1_05dtuHcN3BiMTsbz_p5IEA" src="https://github.com/user-attachments/assets/322829b4-992a-4b3d-a808-74995c9cd3b4" />

5. **Menutup Sesi**

   Salin password, lalu keluar dari server.
   ```bash
   bandit5@bandit:~/inhere$ exit
   ```

## 📖 Penjelasan Perintah
  - `find` : Perintah yang sangat kuat (powerful) di Linux untuk mencari file dan direktori dalam hierarki sistem file berdasarkan berbagai kriteria (nama, ukuran, tanggal modifikasi, hak akses, dll).
  - `.`: Memberitahu `find` untuk memulai pencarian dari direktori saat ini dan semua sub-direktori di bawahnya.
  - `-type f` : Mencari hanya yang berjenis file (mengabaikan folder/direktori).
  - `-size 1033c` : Mencari file dengan ukuran tepat 1033 bytes. (Huruf c di sini berarti bytes, bukan character).
  - `! -executable` : Tanda seru ! adalah negasi (NOT). Kriteria ini berarti mencari file yang tidak memiliki hak akses executable (tidak bisa dieksekusi).

## 🚩 Flag / Password Level 6
  Password Untuk Login Ke Mesin Bandit Level 6
  - pXa26xhMWaC2SvDotA4r9EgZkulOeSBW
