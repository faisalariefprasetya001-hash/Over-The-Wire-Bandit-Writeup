# OverTheWire Bandit: Level 7 → Level 8

## 🎯 Tujuan
Tujuan dari level ini adalah menemukan password untuk mengakses Bandit 8. Password tersebut disimpan di dalam sebuah file bernama `data.txt`, dan letaknya tepat di sebelah kata **`millionth`**.

## 🔐 Kredensial Login
- **Host:** `bandit.labs.overthewire.org`
- **Port:** `2220`
- **Username:** `bandit7`
- **Password:** `Bmnnvf82KzQlfxgAI2d1zYbr1u9pr3E3` Password Dari Mesin Bandit Level 6

## 🛠️ Langkah Penyelesaian

1. **Membuat Koneksi SSH**
   
   Masuk ke server menggunakan kredensial `bandit7`.
   ```bash
   ssh bandit7@bandit.labs.overthewire.org -p 2220

2. **Melihat Isi Direktori**

   Periksa file yang ada di direktori saat ini.
   ```bash
   bandit7@bandit:~$ ls
   data.txt
   ```
   <img width="561" height="87" alt="1_6-siw0VbUkPjW0Dk_M0Nqg" src="https://github.com/user-attachments/assets/19bc0251-172a-4dd2-b10c-871fd4ff768a" />

   Terdapat file `data.txt`. Jika Anda mencoba membacanya langsung dengan perintah `cat data.txt`, terminal Anda akan dibanjiri oleh puluhan ribu baris teks acak, sehingga mencari satu kata secara manual sangat tidak mungkin.

3. **Mencari Kata Spesifik di Dalam File**

   Untuk mencari baris teks yang mengandung kata tertentu di dalam sebuah file, kita menggunakan perintah `grep`.
   ```bash
   bandit7@bandit:~$ grep "millionth" data.txt
   millionth
   ```
   <img width="607" height="80" alt="1__UmYs2wAdaU1VKzS9s9e6A" src="https://github.com/user-attachments/assets/29793613-50c9-4c38-9aac-f3d6ee652c39" />
   Terminal akan langsung menyaring dan hanya menampilkan baris yang memiliki kata `millionth` di dalamnya.

4. **Menutup Sesi**

   Salin password yang berada di sebelah kata `millionth`, lalu keluar dari server.
   ```bash
   bandit7@bandit:~$ exit
   ```

## 📖 Penjelasan Perintah
- `grep` (Global Regular Expression Print): Ini adalah salah satu perintah paling penting dalam administrasi Linux dan cybersecurity. Fungsinya adalah memindai isi satu atau beberapa file, mencari pola atau teks tertentu, dan hanya mencetak baris yang cocok dengan pencarian tersebut ke layar terminal.

## 🚩 Flag / Password Level 8
  Password Untuk Login Ke mesin Bandit Level 8
  - VR1ljMayciFxbnUokuQmJFw6QC9VKtub<img width="561" height="87" alt="1_6-siw0VbUkPjW0Dk_M0Nqg" src="https://github.com/user-attachments/assets/d6cbf2f5-7268-454a-9d9a-23cb8ab86539" />
