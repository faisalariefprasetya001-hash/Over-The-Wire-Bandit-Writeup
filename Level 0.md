# OverTheWire Bandit: Level 0 → Level 1

## 🎯 Tujuan
Tujuan dari level ini adalah menemukan password untuk mengakses level selanjutnya (Bandit 1). Password tersebut disimpan di dalam sebuah file bernama `readme` yang terletak di *home directory* pengguna.

## 🔐 Kredensial Login
- **Host:** `bandit.labs.overthewire.org`
- **Port:** `2220`
- **Username:** `bandit0`
- **Password:** `bandit0`

## 🛠️ Langkah Penyelesaian

1. **Membuat Koneksi SSH**
   Masuk ke server menggunakan kredensial yang diberikan.
   ```bash
   ssh bandit0@bandit.labs.overthewire.org -p 2220
2. **Melihat Isi Direktori**
   Setelah berhasil login, periksa file apa saja yang ada di direktori saat ini menggunakan perintah ls.
   ```bash
   bandit0@bandit:~$ ls
   readme
3. **Membaca Isi File**
   Gunakan perintah cat untuk mencetak isi teks dari file readme ke layar terminal.
   ```bash
   bandit0@bandit:~$ cat readme
   Congratulations on your first steps into the bandit game!!
   Please make sure you have read the rules at https://overthewire.org/rules/
   If you are following a course, workshop, walkthrough or other educational activity,
   please inform the instructor about the rules as well and encourage them to
   contribute to the OverTheWire community so we can keep these games free!

   The password you are looking for is: 6y2kwnwK6grgvwvpvLaa2T1cpFEKOhNR
4. **Menutup Sesi**
   Salin password yang muncul, lalu tutup koneksi dari server bandit0 sebelum melanjutkan ke level berikutnya.
   ```bash
   bandit0@bandit:~$ exit
   ```
   
## 📖 Penjelasan Perintah

- `ls` (List): Perintah dasar Linux untuk menampilkan daftar file dan folder di dalam direktori aktif.
- `cat` (Concatenate): Perintah standar untuk membaca isi file teks dan menampilkannya secara langsung di terminal tanpa membuka teks editor
- `exit`: Menutup sesi shell saat ini secara aman dan memutuskan koneksi dari server remote.

## 🚩 Flag / Password Level 1
password untuk login ke mesin bandit level 1
- 6y2kwnwK6grgvwvpvLaa2T1cpFEKOhNR
