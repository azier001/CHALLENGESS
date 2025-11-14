# 📊 Dokumentasi Fungsi `analyzeSpecimenData`

## 🎯 Deskripsi

Fungsi `analyzeSpecimenData` adalah sebuah fungsi JavaScript yang digunakan untuk menganalisis data pengukuran spesimen yang disimpan dalam bentuk array 2 dimensi (grid). Fungsi ini akan menghitung berbagai statistik dari data tersebut seperti jumlah total, nilai maksimum, nilai minimum, dan jumlah pengukuran yang melebihi nilai tertentu.

## 📝 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `dataGrid` | `Array<Array<Number>>` | Array 2 dimensi yang berisi data pengukuran numerik. Setiap baris adalah array yang berisi beberapa nilai pengukuran. |

### Contoh Format Parameter:

```javascript
// Contoh dataGrid dengan 3 baris dan beberapa kolom
[
  [45, 67, 32, 89],
  [12, 54, 76, 43],
  [91, 23, 58, 65]
]
```

## 🔄 Nilai Return

| Tipe | Deskripsi |
|------|-----------|
| `String` | String yang berisi ringkasan analisis dengan format: `"sum of all measurements: [total], maximum measurement: [max], minimum measurement: [min], number of measurements > 50: [count]"` |

## 📊 Contoh Output

### Input:
```javascript
const data = [
  [10, 20, 30],
  [40, 50, 60],
  [70, 80, 90]
];

const result = analyzeSpecimenData(data);
console.log(result);
```

### Output:
```
sum of all measurements: 450, maximum measurement: 90, minimum measurement: 10, number of measurements > 50: 4
```

## 💻 Source Code

```javascript
function analyzeSpecimenData(dataGrid) {
  
  // Membuat array kosong untuk menampung data yang sudah diratakan
  let flattenedData = [];
  
  // Menggunakan loop for untuk iterasi melalui setiap baris
  for (let i = 0; i < dataGrid.length; i++) {
    // Menggunakan concat untuk menggabungkan setiap baris ke dalam array yang diratakan
    flattenedData = flattenedData.concat(dataGrid[i]);
  }
  
  
  // Menghitung jumlah total dari semua pengukuran menggunakan reduce
  const totalSum = flattenedData.reduce((accumulator, currentValue) => {
    return accumulator + currentValue;
  }, 0);
  
  
  // Mencari nilai pengukuran maksimum menggunakan reduce
  const maxMeasurement = flattenedData.reduce((max, currentValue) => {
    if (currentValue > max) {
      return currentValue;
    }
    return max;
  }, flattenedData[0]);
  
  
  // Mencari nilai pengukuran minimum menggunakan reduce
  const minMeasurement = flattenedData.reduce((min, currentValue) => {
    if (currentValue < min) {
      return currentValue;
    }
    return min;
  }, flattenedData[0]);
  
  
  // Menghitung pengukuran yang lebih besar dari 50 menggunakan filter
  const measurementsGreaterThan50 = flattenedData.filter((measurement) => {
    return measurement > 50;
  });
  
  const countGreaterThan50 = measurementsGreaterThan50.length;
  
  
  // Pendekatan alternatif: menggunakan loop forEach untuk menghitung
  let alternativeCount = 0;
  flattenedData.forEach((measurement) => {
    if (measurement > 50) {
      alternativeCount++;
    }
  });
  
  
  // Membuat string hasil analisis
  const resultString = `sum of all measurements: ${totalSum}, maximum measurement: ${maxMeasurement}, minimum measurement: ${minMeasurement}, number of measurements > 50: ${countGreaterThan50}`;
  
  return resultString;
}
```

## 🔍 Cara Kerja Fungsi

### 1️⃣ **Meratakan Array 2D menjadi 1D** (Flattening)
Fungsi ini pertama-tama mengubah array 2 dimensi menjadi array 1 dimensi agar lebih mudah diproses:
```javascript
// Input: [[10, 20], [30, 40]]
// Output: [10, 20, 30, 40]
```

### 2️⃣ **Menghitung Total Sum**
Menggunakan metode `reduce()` untuk menjumlahkan semua nilai dalam array:
```javascript
// [10, 20, 30, 40] → 100
```

### 3️⃣ **Mencari Nilai Maksimum**
Menggunakan `reduce()` untuk membandingkan setiap nilai dan menemukan yang terbesar:
```javascript
// [10, 20, 30, 40] → 40
```

### 4️⃣ **Mencari Nilai Minimum**
Menggunakan `reduce()` untuk membandingkan setiap nilai dan menemukan yang terkecil:
```javascript
// [10, 20, 30, 40] → 10
```

### 5️⃣ **Menghitung Jumlah Nilai > 50**
Menggunakan `filter()` untuk menyaring nilai yang lebih besar dari 50, kemudian menghitung jumlahnya:
```javascript
// [10, 20, 60, 70] → [60, 70] → count: 2
```

## 📌 Catatan Penting

- ⚠️ Fungsi ini mengasumsikan bahwa `dataGrid` tidak kosong dan berisi minimal satu nilai
- ⚠️ Semua nilai dalam array harus berupa angka (number)
- 💡 Terdapat dua cara untuk menghitung nilai > 50: menggunakan `filter()` dan `forEach()`, namun hanya hasil dari `filter()` yang digunakan dalam output
- 💡 Nilai awal untuk `reduce()` saat mencari min/max menggunakan elemen pertama array (`flattenedData[0]`)

## 🎓 Untuk Pemula

Fungsi ini seperti seorang asisten laboratorium yang:
1. **Mengumpulkan** semua data pengukuran dari berbagai tempat (meratakan array)
2. **Menjumlahkan** semua hasil pengukuran
3. **Mencari** nilai pengukuran tertinggi dan terendah
4. **Menghitung** berapa banyak pengukuran yang hasilnya bagus (> 50)
5. **Membuat laporan** ringkasan dari semua analisis tersebut

Semua informasi ini dikembalikan dalam bentuk kalimat yang mudah dibaca!

## 📚 Contoh Penggunaan Lengkap

```javascript
// Data pengukuran dari 3 hari
const weeklyData = [
  [45, 67, 32],  // Hari 1
  [89, 12, 54],  // Hari 2
  [76, 43, 91]   // Hari 3
];

const analysis = analyzeSpecimenData(weeklyData);
console.log(analysis);

// Output:
// sum of all measurements: 509, maximum measurement: 91, 
// minimum measurement: 12, number of measurements > 50: 5
```

---

💡 **Tips**: Fungsi ini sangat berguna untuk analisis data cepat dalam penelitian atau quality control!
