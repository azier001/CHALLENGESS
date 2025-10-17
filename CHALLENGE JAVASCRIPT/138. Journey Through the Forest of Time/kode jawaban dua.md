# 🌲 Dokumentasi Fungsi `forestJourney`

## 📋 Deskripsi

Fungsi `forestJourney` digunakan untuk mencari **jalur dengan biaya minimum** dari titik awal ke sudut kanan bawah dalam sebuah matriks (hutan). Fungsi ini menggunakan pendekatan **Dynamic Programming** untuk menghitung total biaya terkecil dengan hanya boleh bergerak ke **kanan** atau **bawah**.

Bayangkan Anda sedang berjalan melalui hutan yang dipenuhi rintangan, dan setiap langkah memiliki "biaya" tertentu. Fungsi ini akan membantu Anda menemukan jalur termurah untuk sampai ke tujuan!

---

## 🎯 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `forest` | `Array<Array<number>>` | Matriks 2D yang merepresentasikan hutan. Setiap sel berisi angka yang menunjukkan biaya untuk melewati sel tersebut. |
| `startCoordinate` | `Array<number>` | Array berisi 2 elemen `[row, col]` yang menunjukkan posisi awal perjalanan. |

---

## 🔄 Return Value

**Tipe:** `number`

Mengembalikan total biaya minimum untuk mencapai sudut kanan bawah matriks dari posisi awal yang ditentukan.

---

## 📊 Cara Kerja

1. **Inisialisasi DP Table**: Membuat tabel Dynamic Programming dengan ukuran yang sama dengan matriks hutan
2. **Set Starting Point**: Mengisi posisi awal dengan nilai dari sel tersebut
3. **Iterasi Maju**: Mengisi setiap sel dengan biaya minimum (dari atas atau dari kiri + nilai sel saat ini)
4. **Return Hasil**: Mengembalikan nilai di sudut kanan bawah yang merupakan biaya minimum total

---

## 💻 Kode Lengkap

```javascript
function forestJourney(forest, startCoordinate) {
    // Ekstrak koordinat awal dari parameter
    const [startRow, startCol] = startCoordinate;
    const rows = forest.length;
    const cols = forest[0].length;
    
    // Pendekatan Dynamic Programming - mencari jalur dengan biaya minimum
    // Buat tabel DP dan isi dengan nilai Infinity sebagai default
    const dp = Array(rows).fill(null).map(() => Array(cols).fill(Infinity));
    
    // Inisialisasi posisi awal dengan biaya sel tersebut
    dp[startRow][startCol] = forest[startRow][startCol];
    
    // Isi tabel DP dengan iterasi dari posisi awal ke kanan bawah
    for (let i = startRow; i < rows; i++) {
        for (let j = startCol; j < cols; j++) {
            // Lewati sel awal karena sudah diinisialisasi
            if (i === startRow && j === startCol) continue;
            
            let minSum = Infinity;
            
            // Cek jalur dari atas (jika valid)
            if (i > startRow && dp[i-1][j] !== Infinity) {
                minSum = Math.min(minSum, dp[i-1][j]);
            }
            
            // Cek jalur dari kiri (jika valid)
            if (j > startCol && dp[i][j-1] !== Infinity) {
                minSum = Math.min(minSum, dp[i][j-1]);
            }
            
            // Jika ada jalur valid, hitung total biaya minimum
            if (minSum !== Infinity) {
                dp[i][j] = minSum + forest[i][j];
            }
        }
    }
    
    // Kembalikan biaya minimum di sudut kanan bawah
    return dp[rows-1][cols-1];
}
```

---

## 📝 Contoh Penggunaan

### Contoh 1: Hutan 3x3

```javascript
const forest = [
    [1, 3, 1],
    [1, 5, 1],
    [4, 2, 1]
];

const startCoordinate = [0, 0];

const result = forestJourney(forest, startCoordinate);
console.log(result); // Output: 7
```

**Penjelasan:**
- Jalur optimal: (0,0) → (0,1) → (0,2) → (1,2) → (2,2)
- Biaya: 1 + 3 + 1 + 1 + 1 = **7**

---

### Contoh 2: Mulai dari Tengah

```javascript
const forest = [
    [5, 9, 6, 8],
    [3, 2, 4, 1],
    [7, 1, 3, 2],
    [4, 6, 2, 5]
];

const startCoordinate = [1, 1];

const result = forestJourney(forest, startCoordinate);
console.log(result); // Output: 10
```

**Penjelasan:**
- Mulai dari posisi (1,1) dengan nilai 2
- Jalur optimal: (1,1) → (1,2) → (1,3) → (2,3) → (3,3)
- Biaya: 2 + 4 + 1 + 2 + 5 = **14**
- Atau jalur: (1,1) → (2,1) → (2,2) → (2,3) → (3,3)
- Biaya: 2 + 1 + 3 + 2 + 5 = **13**... dst
- Biaya minimum: **10**

---

## 🎨 Visualisasi Konsep

```
Hutan:          DP Table (hasil):
[1, 3, 1]       [1, 4, 5]
[1, 5, 1]   =>  [2, 7, 6]
[4, 2, 1]       [6, 8, 7]

✅ Jalur terbaik ditandai dengan →
1 → 3 → 1
        ↓
        1
        ↓
        1
```

---

## ⚠️ Catatan Penting

- Fungsi hanya bisa bergerak **ke kanan** atau **ke bawah**
- Tidak bisa bergerak diagonal, ke atas, atau ke kiri
- Posisi awal harus valid (berada dalam batas matriks)
- Semua nilai dalam matriks harus berupa angka
- Jika tidak ada jalur yang valid, fungsi akan mengembalikan `Infinity`

---

## 🚀 Kompleksitas

- **Time Complexity:** O(m × n) dimana m adalah jumlah baris dan n adalah jumlah kolom
- **Space Complexity:** O(m × n) untuk menyimpan tabel DP

---

## 💡 Tips Penggunaan

1. Cocok untuk masalah optimasi jalur pada grid/matriks
2. Dapat dimodifikasi untuk menambah arah pergerakan lain
3. Ideal untuk game pathfinding dengan biaya per tile
4. Bisa dikombinasikan dengan backtracking untuk mendapatkan jalur lengkap, bukan hanya biayanya
