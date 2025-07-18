# 📊 Dokumentasi Fungsi `examPanic`

## 🎯 Deskripsi Fungsi

Fungsi `examPanic` adalah sebuah fungsi JavaScript yang melakukan tiga operasi utama pada sebuah matriks:
1. **Menghitung jumlah total** dari semua elemen dalam matriks
2. **Membalik urutan elemen** di setiap baris matriks
3. **Menghitung hasil perkalian** elemen-elemen diagonal pada matriks yang sudah dibalik

Fungsi ini mengembalikan array yang berisi ketiga hasil operasi tersebut. Versi ini menggunakan pendekatan **functional programming** dengan `reduce()` dan `map()` untuk operasi yang lebih elegan dan ringkas.

## 📝 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `matrix` | Array 2D | Matriks berupa array dua dimensi yang berisi angka |

## 🔧 Kode Fungsi

```javascript
function examPanic(matrix) {
    // Menghitung jumlah total semua elemen dalam matriks
    // Menggunakan reduce untuk menjumlahkan semua baris, lalu setiap elemen dalam baris
    const sum = matrix.reduce((acc, row) => 
        acc + row.reduce((sum, num) => sum + num, 0), 0
    );
    
    // Membalik urutan elemen di setiap baris matriks
    // Menggunakan map untuk transformasi setiap baris dengan reverse
    const reversedMatrix = matrix.map(row => [...row].reverse());
    
    // Menghitung hasil perkalian elemen diagonal pada matriks yang sudah dibalik
    // Menggunakan reduce dengan index untuk mengakses elemen diagonal
    const diagonalProduct = reversedMatrix.reduce((product, row, index) => 
        product * row[index], 1
    );
    
    // Mengembalikan array dengan sum, reversedMatrix, dan diagonalProduct
    return [sum, reversedMatrix, diagonalProduct];
}
```

## 📤 Nilai Kembalian

Fungsi ini mengembalikan sebuah array dengan tiga elemen:

| Index | Tipe | Deskripsi |
|-------|------|-----------|
| 0 | Number | Jumlah total semua elemen dalam matriks asli |
| 1 | Array 2D | Matriks baru dengan setiap baris yang sudah dibalik |
| 2 | Number | Hasil perkalian elemen-elemen diagonal matriks yang sudah dibalik |

## 🔍 Cara Kerja Step by Step

### Step 1: Menghitung Jumlah Total 🧮
Menggunakan **nested reduce()** untuk menjumlahkan semua elemen:
- `reduce()` pertama iterasi setiap baris
- `reduce()` kedua menjumlahkan elemen dalam setiap baris
- Hasil akhir: jumlah total semua elemen

### Step 2: Membalik Setiap Baris 🔄
Menggunakan **map()** untuk transformasi setiap baris:
- Membuat copy baris dengan spread operator `...`
- Membalik urutan dengan `reverse()`

### Step 3: Menghitung Perkalian Diagonal ✖️
Menggunakan **reduce()** dengan parameter `index`:
- Mengalikan elemen pada posisi diagonal (`row[index]`)
- Dimulai dari nilai awal `1` untuk perkalian

## 💡 Contoh Penggunaan

```javascript
// Contoh 1: Matriks 3x3
const matrix1 = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
];

const result1 = examPanic(matrix1);
console.log(result1);
```

### 🎯 Output Contoh 1:
```javascript
[
    45,                    // Jumlah total: 1+2+3+4+5+6+7+8+9 = 45
    [                      // Matriks dengan baris terbalik:
        [3, 2, 1],         // [1,2,3] → [3,2,1]
        [6, 5, 4],         // [4,5,6] → [6,5,4]
        [9, 8, 7]          // [7,8,9] → [9,8,7]
    ],
    105                    // Perkalian diagonal: 3 × 5 × 7 = 105
]
```

### 📊 Tabel Proses untuk Contoh 1:

| Tahap | Matriks Asli | Matriks Terbalik | Elemen Diagonal |
|-------|-------------|------------------|-----------------|
| Input | `[[1,2,3],[4,5,6],[7,8,9]]` | - | - |
| Setelah Reverse | - | `[[3,2,1],[6,5,4],[9,8,7]]` | - |
| Diagonal | - | - | `3, 5, 7` |

## 🚀 Contoh Lain

```javascript
// Contoh 2: Matriks 2x2
const matrix2 = [
    [10, 20],
    [30, 40]
];

const result2 = examPanic(matrix2);
console.log(result2);
// Output: [100, [[20,10],[40,30]], 600]
```

### 🔢 Penjelasan Contoh 2:
- **Jumlah total**: 10 + 20 + 30 + 40 = 100
- **Matriks terbalik**: [[20,10],[40,30]]
- **Perkalian diagonal**: 20 × 30 = 600

```javascript
// Contoh 3: Matriks 2x3 (tidak persegi)
const matrix3 = [
    [1, 2, 3],
    [4, 5, 6]
];

const result3 = examPanic(matrix3);
console.log(result3);
// Output: [21, [[3,2,1],[6,5,4]], 15]
```

### 🔢 Penjelasan Contoh 3:
- **Jumlah total**: 1 + 2 + 3 + 4 + 5 + 6 = 21
- **Matriks terbalik**: [[3,2,1],[6,5,4]]
- **Perkalian diagonal**: 3 × 5 = 15 (hanya 2 elemen diagonal)

## 🎓 Keunggulan Pendekatan Functional Programming

### ✅ Kelebihan:
- **Lebih ringkas** dan mudah dibaca
- **Immutable** - tidak mengubah data asli
- **Declarative** - fokus pada "apa" bukan "bagaimana"
- **Chainable** - bisa digabungkan dengan method lain

### 📚 Method yang Digunakan:

| Method | Fungsi | Contoh |
|--------|--------|---------|
| `reduce()` | Mengurangi array menjadi satu nilai | Penjumlahan, perkalian |
| `map()` | Transformasi setiap elemen array | Membalik baris |
| `reverse()` | Membalik urutan elemen | Membalik baris |
| Spread `...` | Membuat copy array | Mencegah mutasi |

## ⚠️ Catatan Penting

1. **Matriks harus berisi angka** untuk hasil yang benar
2. **Matriks kosong** akan menghasilkan error
3. **Matriks persegi** akan memberikan hasil perkalian diagonal yang lebih akurat
4. **Matriks tidak persegi** akan menggunakan jumlah baris yang tersedia untuk diagonal
5. **Spread operator** `...` penting untuk mencegah mutasi array asli

## 🎓 Tips untuk Pemula

- **Functional Programming**: Pendekatan ini lebih modern dan elegan
- **Reduce()** adalah method yang powerful untuk operasi akumulasi
- **Immutability**: Selalu buat copy data sebelum memodifikasi
- **Index parameter**: Dalam reduce, parameter ketiga adalah index yang berguna untuk diagonal
- **Chainable methods**: Bisa menggabungkan beberapa method untuk operasi kompleks

## 🔧 Perbandingan dengan Loop Tradisional

| Aspek | Loop Tradisional | Functional Programming |
|-------|------------------|----------------------|
| **Readability** | Lebih verbose | Lebih ringkas |
| **Performance** | Sedikit lebih cepat | Sedikit lebih lambat |
| **Maintainability** | Lebih sulit maintain | Lebih mudah maintain |
| **Debugging** | Lebih mudah debug | Butuh pemahaman method |
