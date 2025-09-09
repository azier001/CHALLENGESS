# 🏇 Horse Race Winner Checker

## 📋 Ringkasan Challenge

**Tingkat Kesulitan:** `Easy`

Buat sebuah function bernama `horseRaceWinnerChecker` yang menentukan pemenang balapan kuda berdasarkan posisi saat ini dan bendera yang dikibarkan penonton.

---

## 🎯 Tujuan

Tugas Anda adalah menghitung poin untuk setiap kuda dan mengidentifikasi pemenang balapan. Sistem penilaian menggabungkan keunggulan posisi dengan dukungan penonton melalui pengibaran bendera.

---

## 📊 Sistem Penilaian

### Poin Posisi
| Posisi | Poin yang Diperoleh |
|--------|---------------------|
| 🥇 Tempat 1 | **3 poin** |
| 🥈 Tempat 2 | **2 poin** |
| 🥉 Tempat 3 | **1 poin** |
| Tempat 4+ | **0 poin** |

### Poin Bonus Bendera
- **+1 poin** untuk setiap bendera penonton yang sesuai dengan warna kuda
- Pencocokan warna berdasarkan **kata pertama** dari nama kuda
- Case-insensitive matching

### Aturan Tie-Breaking
> 🏁 Dalam kasus seri, kuda yang muncul **lebih awal** dalam array `horses` asli yang menang.

---

## 🔧 Spesifikasi Function

### Function Signature
```javascript
function horseRaceWinnerChecker(horses, flags)
```

### Parameter

#### `horses` (Array of Strings)
- **Deskripsi:** Kuda-kuda yang terdaftar sesuai urutan posisi balapan saat ini
- **Format:** Setiap nama kuda dimulai dengan identifier warna
- **Contoh:** `["Red Stallion", "Blue Thunder", "Green Lightning"]`

#### `flags` (Array of Strings)  
- **Deskripsi:** Bendera yang sedang dikibarkan oleh penonton
- **Format:** Nama warna dalam huruf kecil
- **Contoh:** `["red", "green", "blue", "red"]`

### Return Value
- **Tipe:** String
- **Deskripsi:** Nama kuda pemenang

---

## 📏 Constraints

| Parameter | Minimum | Maksimum | Nilai Valid |
|-----------|---------|----------|-------------|
| Array `horses` | 1 kuda | 5 kuda | Nama dimulai dengan warna |
| Array `flags` | 1 bendera | 100 bendera | String warna saja |

### Warna yang Didukung
- 🔴 `red`
- 🔵 `blue` 
- 🟢 `green`
- 🟡 `yellow`
- ⚪ `white`

---

## 💡 Contoh Skenario

### Skenario 1: Balapan Dasar
```javascript
horses = ["Red Stallion", "Blue Thunder", "Green Lightning"]
flags = ["red", "red", "blue"]

// Penilaian:
// Red Stallion: 3 (tempat 1) + 2 (red flags) = 5 poin ← Pemenang
// Blue Thunder: 2 (tempat 2) + 1 (blue flag) = 3 poin
// Green Lightning: 1 (tempat 3) + 0 (tidak ada green flags) = 1 poin
```

### Skenario 2: Tie-Breaking
```javascript
horses = ["Yellow Flash", "White Storm"]
flags = ["white", "white", "white"]

// Penilaian:
// Yellow Flash: 3 (tempat 1) + 0 (tidak ada yellow flags) = 3 poin ← Pemenang (tie-breaker)
// White Storm: 2 (tempat 2) + 3 (white flags) = 5 poin
```

---

## ✅ Kriteria Keberhasilan

Function Anda harus:
- ✓ Menghitung poin posisi dengan benar (3-2-1-0)
- ✓ Menghitung bonus bendera yang sesuai secara akurat
- ✓ Menangani tie-breaking berdasarkan posisi array asli
- ✓ Mengembalikan nama kuda persis seperti yang diberikan
- ✓ Bekerja dengan semua kombinasi constraints (1-5 kuda, 1-100 bendera)

---

## 🚀 Memulai

Siap untuk mengimplementasikan solusi Anda? Ingatlah untuk:
1. Parse warna kuda dari kata pertama setiap nama
2. Hitung poin posisi dan bonus bendera
3. Tangani logika tie-breaking dengan benar
4. Test dengan edge cases dan skenario yang berbeda

Semoga berhasil! 🍀
