# 🐦 Tantangan Bird Code Generator

## 📋 Overview Tantangan

**Tingkat Kesulitan:** `Easy`

Buat function bernama `birdCode` yang menganalisis nama burung dan menghasilkan kode khusus berdasarkan properti matematika dan linguistik.

---

## 🎯 Spesifikasi Function

### Function Signature
```javascript
function birdCode(birdName)
```

**Parameter:**
- `birdName` (string): Nama burung yang akan dianalisis

**Return:**
- String berisi kode yang dihasilkan

---

## 🔍 Aturan Pembuatan Kode

Function mengevaluasi tiga kondisi berbeda dan membangun kode sesuai dengan aturan berikut:

### Aturan 1: Jumlah Vowel Prima
- **Kondisi:** Nama burung mengandung **bilangan prima** vowel
- **Aksi:** Tambahkan `"1"` ke kode
- **Vowel:** `a`, `e`, `i`, `o`, `u` (case-insensitive)

### Aturan 2: Panjang Perfect Square
- **Kondisi:** Panjang nama burung adalah **perfect square**
- **Aksi:** Tambahkan `"2"` ke kode
- **Perfect square:** 1, 4, 9, 16, 25, 36, 49, 64, 81, 100...

### Aturan 3: Deteksi Palindrome
- **Kondisi:** Nama burung adalah **palindrome**
- **Aksi:** Tambahkan `"3"` ke kode
- **Palindrome:** Dibaca sama dari depan dan belakang

### Kasus Default
- **Kondisi:** Tidak ada aturan di atas yang berlaku
- **Aksi:** Return `"0"`

---

## 📚 Definisi Kunci

| Istilah | Definisi | Contoh |
|---------|----------|---------|
| **Vowel** | Huruf: a, e, i, o, u (uppercase/lowercase) | `"Eagle"` memiliki 3 vowel: e, a, e |
| **Bilangan Prima** | Bilangan asli > 1 dengan tepat dua pembagi | 2, 3, 5, 7, 11, 13, 17, 19, 23... |
| **Perfect Square** | Integer yang sama dengan n² untuk integer n | 1=1², 4=2², 9=3², 16=4², 25=5² |
| **Palindrome** | Kata yang dibaca sama dari depan dan belakang | "racecar", "madam", "level" |

---

## 💡 Skenario Contoh

### Multiple Conditions
Jika nama burung memenuhi beberapa aturan, gabungkan semua kode yang berlaku:
- ✅ Vowel prima + Panjang perfect square → `"12"`
- ✅ Vowel prima + Palindrome → `"13"`
- ✅ Perfect square + Palindrome → `"23"`
- ✅ Ketiga kondisi terpenuhi → `"123"`

### Sample Test Cases
```
birdCode("Eagle")     // Analisis jumlah vowel, panjang, palindrome
birdCode("Owl")       // Periksa ketiga kondisi
birdCode("Raven")     // Evaluasi berdasarkan aturan
birdCode("Dove")      // Terapkan kondisi secara berurutan
```

---

## 🚀 Tips Implementasi

1. **Counting Vowel:** Gunakan pencocokan case-insensitive
2. **Pengecekan Prima:** Implementasikan deteksi prima yang efisien
3. **Perfect Square:** Gunakan validasi square root
4. **Palindrome:** Bandingkan string dengan kebalikannya
5. **Pembangunan Kode:** Gabungkan kondisi sesuai urutan (1→2→3)

---

## ⚡ Referensi Cepat

```
Kondisi Terpenuhi → Penambahan Kode
──────────────────────────────────
Vowel prima       →      "1"
Perfect square    →      "2"  
Palindrome        →      "3"
Tidak ada         →      "0"
```

---

*Semoga berhasil dengan implementasinya! 🎯*
