# 🔬 Advanced Specimen Data Analysis in a Pristine Laboratory

## 📊 Ringkasan Challenge

**Tingkat Kesulitan:** `Hard`

Anda adalah seorang ilmuwan di laboratorium yang sangat bersih, di mana analisis data spesimen yang teliti sangat penting untuk penelitian yang inovatif. Tugas Anda adalah mengembangkan sebuah function yang memproses array 2D yang merepresentasikan grid data spesimen, di mana setiap cell berisi nilai integer yang merepresentasikan pengukuran yang diambil dari spesimen tersebut.

---

## 🎯 Objektif

Buat sebuah function bernama **`analyzeSpecimenData`** yang melakukan analisis komprehensif pada grid 2D dari pengukuran spesimen.

---

## 📋 Persyaratan Function

### Function Signature

```javascript
function analyzeSpecimenData(dataGrid) {
  // Implementasi Anda di sini
}
```

### Parameter

- **`dataGrid`** *(array)*: Array 2D berisi integer di mana setiap integer merepresentasikan pengukuran dari spesimen di laboratorium.

### Return Value

Function ini mengembalikan sebuah **string** yang merangkum analisis data dengan format berikut:

```javascript
"sum of all measurements: {totalSum}, maximum measurement: {maxMeasurement}, minimum measurement: {minMeasurement}, number of measurements > 50: {countGreaterThan50}"
```

---

## 🔍 Operasi yang Diperlukan

Function Anda harus melakukan empat operasi berikut:

1. **Menghitung sum** dari semua measurements di dalam grid
2. **Menemukan nilai maximum** measurement di dalam grid
3. **Menemukan nilai minimum** measurement di dalam grid
4. **Menghitung** berapa banyak measurements yang lebih besar dari 50

---

## 🛠️ Batasan Teknis

### Method & Struktur yang Diperlukan

Anda harus menggunakan array methods dan loop structures berikut:

#### Array Methods
- `map()`
- `filter()`
- `reduce()`
- `concat()`
- `slice()`
- `splice()`

#### Loop Structures
- `for` loop
- `while` loop
- `do-while` loop
- `forEach()` loop
- Recursion

### Persyaratan Panjang Code

Solusi Anda harus memiliki panjang antara **50 hingga 99 baris** code.

---

## 💡 Contoh

### Input

```javascript
const dataGrid = [
  [23, 67, 45, 89],
  [12, 54, 78, 34],
  [56, 23, 91, 67]
];

analyzeSpecimenData(dataGrid);
```

### Output

```
"sum of all measurements: 639, maximum measurement: 91, minimum measurement: 12, number of measurements > 50: 7"
```

---

## ✅ Kriteria Keberhasilan

- ✔️ Menghitung sum dari semua measurements dengan benar
- ✔️ Mengidentifikasi nilai maximum dengan akurat
- ✔️ Mengidentifikasi nilai minimum dengan akurat
- ✔️ Menghitung measurements yang lebih besar dari 50 dengan tepat
- ✔️ Menggunakan array methods yang sesuai (map, filter, reduce, dll.)
- ✔️ Mengimplementasikan advanced loop structures
- ✔️ Mengembalikan string dengan format yang benar
- ✔️ Panjang code antara 50-99 baris

---

## 🚀 Tips untuk Sukses

> **Efisiensi Itu Penting**: Kombinasikan array methods secara strategis untuk memproses array 2D dengan efisien.

> **Flatten Terlebih Dahulu**: Pertimbangkan untuk melakukan flatten array 2D untuk menyederhanakan operasi.

> **Method Chaining**: Anda dapat melakukan chain beberapa array methods untuk code yang lebih bersih.

> **Edge Cases**: Pertimbangkan empty arrays atau single-element arrays dalam implementasi Anda.

---

## 📝 Catatan

Challenge ini menekankan kombinasi functional programming methods dengan traditional loop structures untuk memproses multidimensional data secara efisien. Fokus pada penulisan code yang bersih dan mudah dibaca yang mendemonstrasikan pemahaman Anda terhadap kedua paradigma tersebut.

Semoga berhasil dengan analisis data laboratorium Anda! 🧪✨
