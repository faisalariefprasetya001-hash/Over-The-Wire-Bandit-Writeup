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
