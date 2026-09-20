# OverTheWire Bandit: Level 10 → Level 11

## 🎯 Tujuan
Tujuan dari level ini adalah menemukan password untuk mengakses Bandit 11. Password tersebut disimpan di dalam file `data.txt`, namun teks di dalamnya telah disandikan (di-encode) menggunakan algoritma **base64**.

## 🔐 Kredensial Login
- **Host:** `bandit.labs.overthewire.org`
- **Port:** `2220`
- **Username:** `bandit10`
- **Password:** `[Masukkan password yang Anda dapatkan dari Level 9]`

## 🛠️ Langkah Penyelesaian

1. **Membuat Koneksi SSH**
   
   Masuk ke server menggunakan kredensial `bandit10`.
   ```bash
   ssh bandit10@bandit.labs.overthewire.org -p 2220

2. **Melihat Isi Direktori**
   
   Periksa file yang ada di direktori saat ini.
   ```bash
   bandit10@bandit:~$ ls
   data.txt
   ```

   <img width="342" height="110" alt="1_7n-3aXjAjXtUfilbeyrNNA" src="https://github.com/user-attachments/assets/4151d263-57d2-4834-beb3-c9451d2976a8" />

4. **Mendekode Data Base64**
   
   Jika Anda mengetik `cat data.txt`, Anda akan melihat teks acak yang tampak seperti ini: `VGhlIHBhc3N3b3JkIGlz....` Ini adalah bentuk teks yang sudah di-encode.

   Untuk mengembalikan teks tersebut ke bentuk aslinya (teks biasa), kita gunakan perintah `base64` dengan argumen untuk melakukan decode.

    <img width="860" height="127" alt="1_pf2zoIbadHUtdG6vRC9yKg" src="https://github.com/user-attachments/assets/bd586ca1-aae0-449f-8274-cc6243c64849" />
   ```bash
   bandit10@bandit:~$ base64 -d data.txt
   ```

5. **Menutup Sesi**

   Salin password yang muncul, lalu keluar dari server.
   ```bash
   bandit10@bandit:~$ exit
   ```

## 📖 Penjelasan Perintah
   - `Base64` Encoding : Ini bukan sebuah enkripsi untuk keamanan (karena tidak butuh key/password untuk membukanya), melainkan sebuah skema penyandian (encoding) yang mengubah data biner menjadi teks format ASCII yang aman untuk ditransmisikan melalui jaringan.

   - `base64` : Perintah bawaan Linux untuk melakukan proses encoding (menyandikan) atau decoding (menguraikan) data ke/dari format base64.

   - `-d` (Decode) : Parameter atau flag yang memberitahu perintah `base64` untuk menguraikan sandi kembali menjadi teks asli. Jika tanpa `-d`, perintah tersebut justru akan menyandikan file.

 ## 🚩 Flag / Password Level 11    
   Password Untuk Login Ke mesin Bandit Level 11
   - pYfOY6HwUsDj5rL9UvyhU7MCmv8vN5Ro
   
