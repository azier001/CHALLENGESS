# 📊 Dokumentasi Fungsi `examPanic`

## 🎯 Deskripsi Fungsi

Fungsi `examPanic` adalah sebuah fungsi JavaScript yang melakukan tiga operasi utama pada sebuah matriks:
1. **Menghitung jumlah total** dari semua elemen dalam matriks
2. **Membalik urutan elemen** di setiap baris matriks
3. **Menghitung hasil perkalian** elemen-elemen diagonal pada matriks yang sudah dibalik

Fungsi ini mengembalikan array yang berisi ketiga hasil operasi tersebut.

## 📝 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `matrix` | Array 2D | Matriks berupa array dua dimensi yang berisi angka |

## 🔧 Kode Fungsi

```javascript
function examPanic(matrix) {
    // 1. Menghitung jumlah total semua elemen dalam matriks
    let sum = 0;
    
    for (let i = 0; i < matrix.length; i++) {
        for (let j = 0; j < matrix[i].length; j++) {
            sum += matrix[i][j];
        }
    }
    
    // 2. Membalik urutan elemen di setiap baris matriks
    const reversedMatrix = matrix.map(row => [...row].reverse());
    
    // 3. Menghitung hasil perkalian elemen diagonal pada matriks yang sudah dibalik
    let diagonalProduct = 1;
    const size = Math.min(reversedMatrix.length, reversedMatrix[0].length);
    
    for (let i = 0; i < size; i++) {
        diagonalProduct *= reversedMatrix[i][i];
    }
    
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
Fungsi akan menjumlahkan semua elemen dalam matriks menggunakan nested loop.

### Step 2: Membalik Setiap Baris 🔄
Setiap baris dalam matriks akan dibalik urutannya menggunakan method `reverse()`.

### Step 3: Menghitung Perkalian Diagonal ✖️
Mengalikan elemen-elemen yang berada di posisi diagonal utama (dari kiri atas ke kanan bawah) pada matriks yang sudah dibalik.

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
    168                    // Perkalian diagonal: 3 × 5 × 7 = 105
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
// Output: [100, [[20,10],[40,30]], 800]
```

### 🔢 Penjelasan Contoh 2:
- **Jumlah total**: 10 + 20 + 30 + 40 = 100
- **Matriks terbalik**: [[20,10],[40,30]]
- **Perkalian diagonal**: 20 × 30 = 600

## ⚠️ Catatan Penting

1. **Matriks harus berisi angka** untuk hasil yang benar
2. **Matriks kosong** akan menghasilkan error
3. **Matriks persegi** akan memberikan hasil perkalian diagonal yang lebih akurat
4. **Matriks tidak persegi** akan menggunakan ukuran minimum antara baris dan kolom untuk menghitung diagonal

## 🎓 Tips untuk Pemula

- Fungsi ini menggunakan konsep **nested loop** untuk iterasi matriks
- Method `map()` dan `reverse()` digunakan untuk manipulasi array
- **Spread operator** `...` digunakan untuk membuat copy array sebelum di-reverse
- **Math.min()** memastikan tidak ada error saat mengakses elemen diagonal pada matriks tidak persegi
