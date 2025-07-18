# 🎯 Exam Panic: Matrix Manipulation

## 📊 Challenge Overview
**Difficulty:** `Easy`  
**Topic:** Operasi Matrix & Manipulasi Array

---

## 🎭 Skenario

Bayangkan ini: Kamu adalah seorang mahasiswa yang nervous sedang mengikuti ujian licensing terakhir di universitas. Telapak tanganmu berkeringat, jantungmu berdetak kencang, dan kamu sedang menatap soal matematika yang kompleks melibatkan matrix. Dalam keadaan cemas ini, kamu perlu melakukan serangkaian operasi untuk menyelesaikan masalah dan lulus ujian!

## 🎯 Misi Kamu

Buat sebuah function bernama **`examPanic`** yang menerima matrix sebagai parameter dan melakukan operasi berikut:

### 📝 Operasi yang Diperlukan

1. **📊 Kalkulasi Sum**
   - Hitung sum dari semua elemen dalam matrix asli

2. **🔄 Reverse Row**
   - Reverse urutan elemen di setiap row matrix

3. **🔢 Product Diagonal**
   - Hitung product dari elemen diagonal (dari top-left ke bottom-right) pada matrix yang sudah di-reverse

---

## 📋 Spesifikasi Function

### Function Signature
```javascript
function examPanic(matrix) {
    // Implementasi kamu disini
}
```

### Parameter
- **`matrix`** *(integer-2d-array)*: Array 2D berisi integer yang merepresentasikan soal matematika di kertas ujianmu. Setiap sub-array merepresentasikan row dalam matrix.

### Return Value
Function mengembalikan sebuah **array** yang berisi tiga elemen:
```javascript
[sum, reversedMatrix, diagonalProduct]
```

Dimana:
- **`sum`** *(integer)*: Sum dari semua elemen dalam matrix asli
- **`reversedMatrix`** *(integer-2d-array)*: Matrix setelah setiap row di-reverse
- **`diagonalProduct`** *(integer)*: Product dari elemen diagonal dalam matrix yang sudah di-reverse

---

## 💡 Contoh

### Input Matrix:
```
[
  [1, 2, 3],
  [4, 5, 6],
  [7, 8, 9]
]
```

### Proses Step-by-Step:

1. **Sum dari semua elemen:** `1+2+3+4+5+6+7+8+9 = 45`

2. **Matrix yang di-reverse (setiap row di-reverse):**
   ```
   [
     [3, 2, 1],
     [6, 5, 4],
     [9, 8, 7]
   ]
   ```

3. **Product diagonal:** `3 × 5 × 7 = 105`

### Expected Output:
```javascript
[45, [[3, 2, 1], [6, 5, 4], [9, 8, 7]], 105]
```

---

## 🔍 Poin Penting untuk Diingat

- ⚠️ Bekerja dengan **matrix asli** untuk kalkulasi sum
- 🔄 Terapkan reverse row untuk membuat **matrix baru**
- 🎯 Hitung product diagonal dari **matrix yang sudah di-reverse**
- 📦 Return ketiga hasil dalam satu array

---

## 🚀 Siap Menghadapi Challenge?

Tarik napas dalam-dalam, keluarkan jiwa matematikawan dalam dirimu, dan tunjukkan siapa yang berkuasa pada ujian ini! Ingat, bahkan dalam keadaan panic, berpikir sistematis akan membimbingmu ke solusi.

*Semoga berhasil, calon sarjana!* 🎓
