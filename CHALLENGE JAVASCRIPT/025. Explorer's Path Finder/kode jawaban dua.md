# 🗺️ Dokumentasi Fungsi `explorerPathFinder`

## 📋 Deskripsi

Fungsi `explorerPathFinder` adalah sebuah algoritma yang mensimulasikan perjalanan seorang penjelajah (explorer) berdasarkan aturan biner. Fungsi ini mengambil jalur koordinat yang sudah ada dan menambahkan koordinat baru berdasarkan konversi dari string biner ke desimal.

---

## 🔧 Sintaks

```javascript
explorerPathFinder(currentPath, binaryRules)
```

### Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `currentPath` | `Array<number>` | Array berisi koordinat jalur yang sudah ada |
| `binaryRules` | `string` | String biner (contoh: "101") yang akan dikonversi menjadi jumlah langkah |

### Nilai Kembalian

- **Tipe**: `Array<number>`
- **Deskripsi**: Array baru berisi jalur lengkap (jalur lama + koordinat baru)

---

## 🎯 Cara Kerja

### Langkah-langkah Algoritma:

1. **Konversi Biner ke Desimal**
   - String biner dikonversi menjadi angka desimal menggunakan `parseInt(binaryRules, 2)`
   - Angka ini menentukan berapa banyak langkah yang akan ditambahkan

2. **Inisialisasi**
   - Membuat salinan array `currentPath` untuk menghindari modifikasi array asli
   - Mengambil koordinat terakhir sebagai titik awal

3. **Iterasi Langkah**
   - Untuk setiap langkah (dari 0 hingga jumlah langkah):
     - **Langkah genap (0, 2, 4, ...)**: tambah 1 ke koordinat
     - **Langkah ganjil (1, 3, 5, ...)**: kurangi 1 dari koordinat
   - Setiap koordinat baru ditambahkan ke array hasil

---

## 💻 Kode Lengkap

```javascript
function explorerPathFinder(currentPath, binaryRules) {
    // Convert binary string to decimal
    const steps = parseInt(binaryRules, 2);
    
    // Create a copy of the current path to avoid modifying the original
    const finalPath = [...currentPath];
    
    // Get the last coordinate from the current path
    let lastCoordinate = finalPath[finalPath.length - 1];
    
    // Add new coordinates based on the number of steps
    for (let i = 0; i < steps; i++) {
        if (i % 2 === 0) {
            // Even index: add 1
            lastCoordinate += 1;
        } else {
            // Odd index: subtract 1
            lastCoordinate -= 1;
        }
        finalPath.push(lastCoordinate);
    }
    
    return finalPath;
}
```

---

## 📚 Contoh Penggunaan

### Contoh 1: Kasus Dasar

```javascript
const result = explorerPathFinder([1, 2, 3], "101");
console.log(result);
// Output: [1, 2, 3, 4, 3, 4, 3, 4]
```

**Penjelasan Detail:**
- Jalur awal: `[1, 2, 3]`
- Aturan biner: `"101"` = 5 dalam desimal
- Koordinat terakhir: 3
- Proses langkah:
  - Langkah 0 (genap): 3 + 1 = **4**
  - Langkah 1 (ganjil): 4 - 1 = **3**
  - Langkah 2 (genap): 3 + 1 = **4**
  - Langkah 3 (ganjil): 4 - 1 = **3**
  - Langkah 4 (genap): 3 + 1 = **4**

### Contoh 2: Aturan Biner Berbeda

```javascript
const result = explorerPathFinder([0, 5], "11");
console.log(result);
// Output: [0, 5, 6, 5, 4]
```

**Penjelasan:**
- Jalur awal: `[0, 5]`
- Aturan biner: `"11"` = 3 dalam desimal
- Koordinat terakhir: 5
- Proses: 5→6→5→4

### Contoh 3: Jalur Kosong (Edge Case)

```javascript
const result = explorerPathFinder([10], "1000");
console.log(result);
// Output: [10, 11, 10, 11, 10, 11, 10, 11, 10]
```

**Penjelasan:**
- Jalur awal: `[10]`
- Aturan biner: `"1000"` = 8 dalam desimal
- Pola bolak-balik: 10→11→10→11→...

---

## ⚡ Kompleksitas

- **Kompleksitas Waktu**: O(n), di mana n adalah nilai desimal dari string biner
- **Kompleksitas Ruang**: O(m + n), di mana m adalah panjang `currentPath` dan n adalah jumlah langkah

---

## 🚨 Catatan Penting

### Hal yang Perlu Diperhatikan:

1. **Array Asli Tidak Berubah**
   - Fungsi menggunakan spread operator `[...currentPath]` untuk membuat salinan
   - Array `currentPath` yang diberikan sebagai parameter tidak akan termodifikasi

2. **Validasi Input**
   - Pastikan `currentPath` tidak kosong
   - Pastikan `binaryRules` adalah string biner yang valid

3. **Pola Pergerakan**
   - Langkah genap selalu menambah (+1)
   - Langkah ganjil selalu mengurangi (-1)
   - Ini menciptakan pola zigzag dalam koordinat

---

## 🎨 Visualisasi

Untuk `explorerPathFinder([1, 2, 3], "101")`:

```
Koordinat vs Waktu:
4 |     ●     ●     ●
3 | ●     ●     ●
2 | ●
1 | ●
  +─────────────────→
    0 1 2 3 4 5 6 7 8
```

Pola pergerakan: **↗↙↗↙↗** (naik-turun-naik-turun-naik)

---

## 🔍 Use Case

Fungsi ini dapat digunakan untuk:
- Simulasi pergerakan karakter dalam game
- Algoritma pathfinding sederhana
- Demonstrasi konsep konversi biner ke desimal
- Pembelajaran pemrograman dasar (array, loop, conditional)
