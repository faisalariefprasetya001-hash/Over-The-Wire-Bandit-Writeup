# OverTheWire Bandit: Level 1 → Level 2

## 🎯 Tujuan
Tujuan dari level ini adalah menemukan password untuk mengakses Bandit 2. Password tersebut disimpan di dalam sebuah file dengan nama unik, yaitu `-` (tanda strip/dash), yang terletak di *home directory*.

## 🔐 Kredensial Login
- **Host:** `bandit.labs.overthewire.org`
- **Port:** `2220`
- **Username:** `bandit1`
- **Password:** `6y2kwnwK6grgvwvpvLaa2T1cpFEKOhNR` Di dapatkan dari mesin bandit level 0

## 🛠️ Langkah Penyelesaian

1. **Membuat Koneksi SSH**
   
   Masuk ke server menggunakan kredensial `bandit1`.
   ```bash
   ssh bandit1@bandit.labs.overthewire.org -p 2220
2. **Melihat Isi Direktori**
   
   Periksa file yang ada di direktori saat ini.
   ```bash
   bandit1@bandit:~$ ls
   -
3. **Membaca File Bernama Strip (-)**
   
   Karakter `-` sering digunakan dalam perintah Linux untuk menandakan standard input atau          parameter argumen. Jika Anda mengetik `cat -`, terminal akan diam menunggu inputan Anda    
alih-      alih membaca file.

   Untuk membacanya, Anda harus menggunakan path (jalur) spesifik yang memberitahu sistem bahwa `-` adalah sebuah nama file di lokasi saat ini.
   
   <img width="1100" height="139" alt="1_OfNNHx6J0NyNXyg93YVy2Q" src="https://github.com/user-attachments/assets/2a4e1df3-1f8c-440a-8b4e-e98b46e6b0cc" />

5. **Menutup Sesi**

   ```bash
   bandit1@bandit:~$ exit
   ```

## 📖 Penjelasan Perintah
- `./` : Titik mewakili current directory (direktori tempat Anda berada saat ini) dan garis miring adalah pemisah folder. Menambahkan `./` di depan nama file memaksa sistem operasi dan perintah cat untuk membaca karakter berikutnya murni sebagai nama file (sebagai objek), bukan sebagai sebuah parameter perintah.
  
## 🚩 Flag / Password Level 2
Password untuk login mesin bandit level 2
- PK8fYLZg2hnHSz83plBL1iEPKdD3QToB
