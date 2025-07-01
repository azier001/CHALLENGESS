# 🗺️ Explorer's Path Finder

## 🎯 Apa itu Masalah Ini?

**Pencari Jalur Penjelajah** adalah sebuah fungsi yang membantu seorang penjelajah berjalan melalui hutan belantara. Penjelajah ini menggunakan aturan khusus yang ditulis dalam kode biner (angka 0 dan 1) untuk menentukan berapa banyak langkah tambahan yang harus dia ambil.

Bayangkan kamu adalah seorang penjelajah yang sedang berjalan di hutan, dan kamu punya peta rahasia berupa kode biner yang memberitahu berapa langkah lagi yang harus kamu ambil!

---

## 📋 Detail Fungsi

### Nama Fungsi
```javascript
explorerPathFinder(currentPath, binaryRules)
```

### 🔧 Parameter (Input)

| Parameter | Tipe Data | Penjelasan |
|-----------|-----------|------------|
| `currentPath` | Array Angka | Daftar koordinat tempat penjelajah sudah berjalan |
| `binaryRules` | String | Kode biner (contoh: "1101") yang berisi aturan perjalanan |

### 🎯 Yang Dikembalikan (Return Value)
- **Tipe**: Array Angka
- **Isi**: Jalur lengkap setelah menambahkan langkah-langkah baru

---

## ⚙️ Cara Kerja Fungsi (Langkah demi Langkah)

### Langkah 1: Ubah Kode Biner ke Angka Biasa
Pertama, kita ubah kode biner menjadi angka decimal untuk tahu berapa banyak langkah tambahan yang perlu diambil.

> **Contoh**: Kode biner `"1101"` = Angka `13` = Penjelajah harus ambil 13 langkah tambahan

### Langkah 2: Tambahkan Koordinat Baru dengan Pola Khusus
Mulai dari koordinat terakhir di `currentPath`, kita tambahkan koordinat baru dengan pola bergantian:

- **Langkah ganjil (1, 3, 5, ...)**: Tambah 1 dari koordinat sebelumnya
- **Langkah genap (2, 4, 6, ...)**: Kurangi 1 dari koordinat sebelumnya

---

## 📊 Contoh Mudah Dipahami

Mari kita lihat contoh konkret:

### Input (Masukan)
- `currentPath = [5, 3, 7]`
- `binaryRules = "101"` (dalam angka biasa = 5)

### Proses Perhitungan
```
Jalur awal: [5, 3, 7]
Koordinat terakhir: 7

Langkah 1 (ganjil):  7 + 1 = 8  ➡️ Maju
Langkah 2 (genap):   8 - 1 = 7  ⬅️ Mundur  
Langkah 3 (ganjil):  7 + 1 = 8  ➡️ Maju
Langkah 4 (genap):   8 - 1 = 7  ⬅️ Mundur
Langkah 5 (ganjil):  7 + 1 = 8  ➡️ Maju
```

### Hasil Akhir
```
Jalur lengkap: [5, 3, 7, 8, 7, 8, 7, 8]
```

---

## 🧩 Memahami Pola Pergerakan

### Gerakan Zigzag
Penjelajah bergerak seperti zigzag:
- ↗️ **Maju** (+1): Saat langkah ke-1, 3, 5, 7, ... (ganjil)
- ↙️ **Mundur** (-1): Saat langkah ke-2, 4, 6, 8, ... (genap)

### Pengaruh Binary Rules
- **Kode biner besar** → Banyak langkah tambahan
- **Kode biner kecil** → Sedikit langkah tambahan
- **Kode biner "0"** → Tidak ada langkah tambahan (jalur tetap sama)

---

## 📈 Seberapa Cepat Fungsi Ini?

| Aspek | Kecepatan |
|-------|-----------|
| **Waktu Eksekusi** | Bergantung pada nilai biner (semakin besar semakin lama) |
| **Penggunaan Memori** | Bergantung pada panjang jalur awal + langkah tambahan |

---

## 🎮 Untuk Apa Fungsi Ini Berguna?

### 🏔️ Simulasi Petualangan
Cocok untuk membuat game petualangan di mana karakter bergerak mengikuti pola tertentu.

### 🎯 Pengembangan Game
Berguna untuk game yang memerlukan pergerakan karakter berdasarkan kode atau aturan khusus.

### 📊 Analisis Pergerakan
Membantu menganalisis pola pergerakan dan memprediksi posisi berdasarkan kode biner.

---

## ⚠️ Hal-hal yang Perlu Diperhatikan

| Situasi | Yang Harus Dilakukan |
|---------|---------------------|
| `currentPath` kosong | Tangani dengan baik atau beri error yang jelas |
| `binaryRules = "0"` | Kembalikan jalur asli tanpa perubahan |
| Kode biner tidak valid | Periksa apakah input benar (hanya berisi 0 dan 1) |
| Kode biner sangat besar | Pertimbangkan kecepatan program |

---

## 🚀 Tantangan Pemrograman

Tugas kamu adalah membuat fungsi `explorerPathFinder` yang bisa:

1. ✅ Mengubah kode biner menjadi angka biasa
2. ✅ Menambahkan koordinat baru dengan pola bergantian (+1, -1, +1, -1, ...)
3. ✅ Mengembalikan jalur lengkap
4. ✅ Menangani kasus-kasus khusus dengan baik

### 💡 Tips untuk Pemula:
- Mulai dengan memahami cara mengubah binary ke decimal
- Ingat pola ganjil-genap untuk menentukan +1 atau -1
- Gunakan loop untuk menambahkan setiap langkah baru
- Jangan lupa test dengan contoh sederhana dulu!

**Siap membantu penjelajah menemukan jalurnya? Semangat coding!** 🌲⛰️

---

*Selamat belajar dan semoga berhasil! 🧭*
