# 🏝️ Decode Island Map Challenge

## 📋 Ringkasan Challenge

**Tingkat Kesulitan:** `Easy`

Buatlah sebuah function yang dapat mendecode peta harta karun dengan menghitung harta tersembunyi yang direpresentasikan sebagai '1' dalam sebuah encoded string.

---

## 🎯 Deskripsi Masalah

Implementasikan sebuah function bernama `decodeIslandMap` yang:

- **Input:** Parameter string `encodedMap` yang hanya berisi karakter '0' dan '1'
- **Output:** Integer yang merepresentasikan total jumlah '1' (harta karun) yang ditemukan dalam map
- **Tugas:** Hitung semua kemunculan karakter '1' dalam input string

---

## 💡 Contoh

```javascript
decodeIslandMap("10110")  // Returns: 3
```

**Penjelasan:** String "10110" mengandung tiga '1' pada posisi 0, 2, dan 3.

---

## ⚡ Function Signature

```javascript
function decodeIslandMap(encodedMap) {
    // Implementasi kode Anda di sini
}
```

---

## 📏 Constraints

| Constraint | Nilai |
|------------|-------|
| **Karakter Input** | Hanya '0' dan '1' |
| **Panjang String** | 1 ≤ panjang ≤ 100 |
| **Tipe Input** | String |
| **Tipe Output** | Integer |

---

## 🧪 Test Cases

### Test Case 1
```javascript
decodeIslandMap("1001")
// Expected Output: 2
// Penjelasan: Dua '1' ditemukan pada posisi 0 dan 3
```

### Test Case 2
```javascript
decodeIslandMap("00000")
// Expected Output: 0
// Penjelasan: Tidak ada '1' yang ditemukan dalam string
```

### Test Case 3
```javascript
decodeIslandMap("1111111")
// Expected Output: 7
// Penjelasan: Semua tujuh karakter adalah '1'
```

---

## 🎨 Representasi Visual

```
Input:  "1 0 1 1 0"
         ↓   ↓ ↓
Harta Karun: 🏆 🏆 🏆
Jumlah: 3
```

---

## 💭 Ide Pendekatan

- **Method 1:** Iterasi setiap karakter dan hitung '1'
- **Method 2:** Gunakan string methods seperti `split()` atau regular expressions
- **Method 3:** Gunakan array methods dengan `filter()` atau `reduce()`

---

## 🔍 Edge Cases yang Perlu Dipertimbangkan

- String kosong (meskipun constraints menentukan panjang minimum 1)
- String dengan semua '0'
- String dengan semua '1'
- String dengan karakter tunggal

---

*Selamat coding! 🚀*
