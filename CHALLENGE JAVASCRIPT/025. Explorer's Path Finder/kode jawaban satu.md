# 🗺️ Dokumentasi Fungsi `explorerPathFinder` (Versi Optimized)

## 📋 Deskripsi

Fungsi `explorerPathFinder` adalah sebuah algoritma yang mensimulasikan perjalanan seorang penjelajah (explorer) berdasarkan aturan biner. Versi ini menggunakan pendekatan yang lebih efisien dengan memodifikasi array asli dan menggunakan boolean flag untuk mengontrol arah pergerakan.

---

## 🔧 Sintaks

```javascript
explorerPathFinder(currentPath, binaryRules)
```

### Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `currentPath` | `Array<number>` | Array berisi koordinat jalur yang sudah ada (akan dimodifikasi) |
| `binaryRules` | `string` | String biner (contoh: "101") yang akan dikonversi menjadi jumlah langkah |

### Nilai Kembalian

- **Tipe**: `Array<number>`
- **Deskripsi**: Array yang sama dengan parameter input, sudah ditambahkan koordinat baru

---

## 🎯 Cara Kerja

### Langkah-langkah Algoritma:

1. **Konversi Biner ke Desimal**
   - String biner dikonversi menjadi angka desimal menggunakan `parseInt(binaryRules, 2)`
   - Angka ini menentukan berapa banyak langkah yang akan ditambahkan

2. **Inisialisasi Variabel**
   - `lastCoordinate`: koordinat terakhir dari array sebagai titik mulai
   - `add`: boolean flag yang dimulai dengan `true` (menambah)

3. **Iterasi Langkah dengan Toggle Pattern**
   - Untuk setiap langkah (dari 0 hingga jumlah langkah):
     - **Jika `add = true`**: tambah 1 ke koordinat
     - **Jika `add = false`**: kurangi 1 dari koordinat
     - Koordinat baru ditambahkan ke array asli
     - Toggle nilai `add` dengan `add = !add`

---

## 💻 Kode Lengkap

```javascript
function explorerPathFinder(currentPath, binaryRules) {
  const steps = parseInt(binaryRules, 2);
  let lastCoordinate = currentPath[currentPath.length - 1];
  let add = true;

  for (let i = 0; i < steps; i++) {
    if (add) {
      lastCoordinate += 1;
    } else {
      lastCoordinate -= 1;
    }
    currentPath.push(lastCoordinate);
    add = !add;
  }

  return currentPath;
}
```

---

## 📚 Contoh Penggunaan

### Contoh 1: Kasus Dasar

```javascript
const path = [1, 2, 3];
const result = explorerPathFinder(path, "101");
console.log(result);
// Output: [1, 2, 3, 4, 3, 4, 3, 4]
console.log(path);
// Output: [1, 2, 3, 4, 3, 4, 3, 4] (array asli juga berubah!)
```

**Penjelasan Detail:**
- Jalur awal: `[1, 2, 3]`
- Aturan biner: `"101"` = 5 dalam desimal
- Koordinat terakhir: 3
- Proses langkah dengan toggle:
  - Langkah 0: `add=true` → 3 + 1 = **4**, toggle → `add=false`
  - Langkah 1: `add=false` → 4 - 1 = **3**, toggle → `add=true`
  - Langkah 2: `add=true` → 3 + 1 = **4**, toggle → `add=false`
  - Langkah 3: `add=false` → 4 - 1 = **3**, toggle → `add=true`
  - Langkah 4: `add=true` → 3 + 1 = **4**

### Contoh 2: Aturan Biner Berbeda

```javascript
const path = [0, 5];
const result = explorerPathFinder(path, "11");
console.log(result);
// Output: [0, 5, 6, 5, 4]
```

**Penjelasan:**
- Jalur awal: `[0, 5]`
- Aturan biner: `"11"` = 3 dalam desimal
- Koordinat terakhir: 5
- Proses: 5→6 (add)→5 (subtract)→4 (add)

### Contoh 3: String Biner Panjang

```javascript
const path = [10];
const result = explorerPathFinder(path, "1000");
console.log(result);
// Output: [10, 11, 10, 11, 10, 11, 10, 11, 10]
```

**Penjelasan:**
- Jalur awal: `[10]`
- Aturan biner: `"1000"` = 8 dalam desimal
- Pola bolak-balik sempurna: 10→11→10→11→...

---

## ⚡ Kompleksitas

- **Kompleksitas Waktu**: O(n), di mana n adalah nilai desimal dari string biner
- **Kompleksitas Ruang**: O(1), tidak ada alokasi memori tambahan (in-place modification)

---

## 🚨 Perbedaan dengan Versi Sebelumnya

### ✅ Keunggulan Versi Ini:

1. **Lebih Efisien Memory**
   ```javascript
   // Tidak perlu membuat salinan array
   // const finalPath = [...currentPath]; ❌
   ```

2. **Kode Lebih Sederhana**
   ```javascript
   // Menggunakan boolean toggle daripada modulo
   add = !add; // ✅ Lebih mudah dibaca
   // i % 2 === 0 ❌ Lebih kompleks
   ```

3. **Performa Lebih Baik**
   - Tidak ada operasi copying array
   - Tidak ada operasi modulo dalam loop

### ⚠️ Hal yang Perlu Diperhatikan:

1. **Array Asli Akan Berubah**
   ```javascript
   const originalPath = [1, 2, 3];
   explorerPathFinder(originalPath, "10");
   console.log(originalPath); // [1, 2, 3, 4, 3] - BERUBAH!
   ```

2. **Side Effect**
   - Fungsi ini memiliki side effect karena memodifikasi parameter input
   - Jika Anda perlu mempertahankan array asli, buat salinan terlebih dahulu:
   ```javascript
   const backup = [...originalPath];
   explorerPathFinder(originalPath, "101");
   ```

---

## 🔄 Pola Toggle Mechanism

### Visualisasi Boolean Toggle:

```
Langkah | add (awal) | Operasi | add (akhir) | Hasil
--------|------------|---------|-------------|-------
   0    |    true    |   +1    |    false    |  +1
   1    |   false    |   -1    |    true     |  -1
   2    |    true    |   +1    |    false    |  +1
   3    |   false    |   -1    |    true     |  -1
   4    |    true    |   +1    |    false    |  +1
```

**Pola**: `add = !add` menciptakan pergantian antara `true` dan `false` secara otomatis.

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

Toggle Pattern:
T | F | T | F | T
+ | - | + | - | +
```

---

## 🔍 Use Case & Best Practices

### 📋 Kapan Menggunakan Versi Ini:
- Ketika memory efficiency penting
- Ketika Anda tidak perlu mempertahankan array asli
- Untuk aplikasi real-time dengan performa tinggi
- Ketika bekerja dengan dataset besar

### 📋 Kapan Menggunakan Versi Immutable:
- Ketika array asli harus tetap tidak berubah
- Dalam functional programming paradigm
- Ketika debugging dan tracing data flow penting
- Dalam aplikasi dengan state management yang ketat

### 💡 Tips Penggunaan:

```javascript
// Jika perlu backup array asli
function safeExplorerPathFinder(currentPath, binaryRules) {
  const pathCopy = [...currentPath];
  return explorerPathFinder(pathCopy, binaryRules);
}

// Penggunaan dengan error handling
function robustExplorerPathFinder(currentPath, binaryRules) {
  if (!Array.isArray(currentPath) || currentPath.length === 0) {
    throw new Error('currentPath harus berupa array yang tidak kosong');
  }
  
  if (!/^[01]+$/.test(binaryRules)) {
    throw new Error('binaryRules harus berupa string biner valid');
  }
  
  return explorerPathFinder(currentPath, binaryRules);
}
```

---

## 📊 Perbandingan Performa

| Aspek | Versi Original | Versi Optimized |
|-------|----------------|-----------------|
| Memory Usage | O(n) | O(1) |
| Speed | Slower (copying) | Faster |
| Side Effects | None | Modifies input |
| Code Readability | Good | Better |
| Functional Programming | ✅ | ❌ |
