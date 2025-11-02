# 🌊 Dokumentasi Fungsi `navigateOcean`

## 📋 Deskripsi

Fungsi `navigateOcean` adalah fungsi sederhana yang digunakan untuk memeriksa apakah sebuah posisi dapat mencapai tujuan dalam satu langkah lurus (horizontal atau vertikal). Fungsi ini mengembalikan nilai `true` jika posisi saat ini dan tujuan berada pada baris yang sama ATAU kolom yang sama.

Fungsi ini berguna untuk:
- 🗺️ Validasi pergerakan dalam grid/papan permainan
- 🚢 Pengecekan jalur navigasi sederhana
- ♟️ Logika permainan strategi berbasis koordinat

---

## 📝 Kode Fungsi

```javascript
function navigateOcean(currentPosition, destination) {
  // Mengecek apakah posisi saat ini dan tujuan berada di baris yang sama (indeks 0)
  // ATAU di kolom yang sama (indeks 1)
  return currentPosition[0] === destination[0] || currentPosition[1] === destination[1];
}
```

---

## 🎯 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `currentPosition` | `Array [x, y]` | Array berisi 2 elemen yang merepresentasikan koordinat posisi saat ini. Elemen pertama adalah baris (x), elemen kedua adalah kolom (y) |
| `destination` | `Array [x, y]` | Array berisi 2 elemen yang merepresentasikan koordinat tujuan. Elemen pertama adalah baris (x), elemen kedua adalah kolom (y) |

### Penjelasan Detail Parameter:

- **currentPosition[0]**: Koordinat X atau baris dari posisi saat ini
- **currentPosition[1]**: Koordinat Y atau kolom dari posisi saat ini
- **destination[0]**: Koordinat X atau baris dari tujuan
- **destination[1]**: Koordinat Y atau kolom dari tujuan

---

## 🔄 Return Value

| Tipe | Nilai | Kondisi |
|------|-------|---------|
| `Boolean` | `true` | Jika posisi dan tujuan berada di baris yang sama ATAU kolom yang sama |
| `Boolean` | `false` | Jika posisi dan tujuan tidak berada di baris atau kolom yang sama |

---

## 💡 Cara Kerja

Fungsi ini menggunakan operator logika OR (`||`) untuk memeriksa dua kondisi:

1. **Kondisi Pertama**: `currentPosition[0] === destination[0]`
   - Mengecek apakah baris posisi saat ini sama dengan baris tujuan
   - Jika `true`, artinya bisa bergerak secara horizontal

2. **Kondisi Kedua**: `currentPosition[1] === destination[1]`
   - Mengecek apakah kolom posisi saat ini sama dengan kolom tujuan
   - Jika `true`, artinya bisa bergerak secara vertikal

Jika salah satu kondisi terpenuhi, fungsi mengembalikan `true`.

---

## 📊 Visualisasi Grid

Berikut contoh visualisasi untuk memahami cara kerja fungsi:

```
    0   1   2   3   4
  +---+---+---+---+---+
0 | A |   |   |   | B |  ← Baris 0 (horizontal)
  +---+---+---+---+---+
1 |   |   | C |   |   |
  +---+---+---+---+---+
2 |   |   | D |   |   |  ← D di kolom 2 (vertikal dengan C)
  +---+---+---+---+---+
3 |   |   |   |   |   |
  +---+---+---+---+---+
```

| Posisi | Tujuan | Hasil | Alasan |
|--------|--------|-------|--------|
| A [0,0] | B [0,4] | ✅ `true` | Berada di baris yang sama (baris 0) |
| C [1,2] | D [2,2] | ✅ `true` | Berada di kolom yang sama (kolom 2) |
| A [0,0] | C [1,2] | ❌ `false` | Tidak di baris atau kolom yang sama |

---

## 🔍 Contoh Penggunaan

### Contoh 1: Pergerakan Horizontal ✅

```javascript
const posisiSekarang = [3, 5];
const tujuan = [3, 8];

const bisaBergerak = navigateOcean(posisiSekarang, tujuan);
console.log(bisaBergerak); 
// Output: true
// Penjelasan: Berada di baris yang sama (baris 3)
```

### Contoh 2: Pergerakan Vertikal ✅

```javascript
const posisiSekarang = [2, 4];
const tujuan = [7, 4];

const bisaBergerak = navigateOcean(posisiSekarang, tujuan);
console.log(bisaBergerak); 
// Output: true
// Penjelasan: Berada di kolom yang sama (kolom 4)
```

### Contoh 3: Pergerakan Diagonal ❌

```javascript
const posisiSekarang = [1, 1];
const tujuan = [3, 3];

const bisaBergerak = navigateOcean(posisiSekarang, tujuan);
console.log(bisaBergerak); 
// Output: false
// Penjelasan: Tidak berada di baris atau kolom yang sama
```

### Contoh 4: Posisi yang Sama ✅

```javascript
const posisiSekarang = [5, 5];
const tujuan = [5, 5];

const bisaBergerak = navigateOcean(posisiSekarang, tujuan);
console.log(bisaBergerak); 
// Output: true
// Penjelasan: Baris DAN kolom sama (posisi identik)
```

---

## ⚠️ Catatan Penting

- Fungsi ini **tidak memperhitungkan rintangan** di jalur
- Fungsi hanya mengecek **kemungkinan jalur lurus**, bukan validasi pergerakan lengkap
- Koordinat dimulai dari `[0, 0]` seperti array pada umumnya
- Fungsi tidak mengecek apakah koordinat valid atau dalam batas tertentu

---

## 🎮 Use Case

Fungsi ini cocok digunakan untuk:

1. **Game Catur/Checkers**: Validasi pergerakan rook (benteng)
2. **Battleship**: Pengecekan penempatan kapal
3. **Pathfinding Sederhana**: Langkah awal algoritma navigasi
4. **Grid-based Games**: Validasi pergerakan karakter

---

## 🚀 Pengembangan Lebih Lanjut

Berikut beberapa ide untuk mengembangkan fungsi ini:

```javascript
// Tambahkan pengecekan batas grid
function navigateOceanWithBounds(currentPosition, destination, gridSize) {
  const inBounds = destination[0] >= 0 && destination[0] < gridSize &&
                   destination[1] >= 0 && destination[1] < gridSize;
  
  return inBounds && (currentPosition[0] === destination[0] || 
                      currentPosition[1] === destination[1]);
}

// Tambahkan pengecekan obstacle
function navigateOceanWithObstacles(currentPosition, destination, obstacles) {
  const canNavigate = currentPosition[0] === destination[0] || 
                      currentPosition[1] === destination[1];
  
  if (!canNavigate) return false;
  
  // Cek apakah ada obstacle di jalur
  // (implementasi lebih lanjut diperlukan)
  return true;
}
```

---

## 📚 Referensi

- [MDN - Array](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array)
- [MDN - Logical OR (||)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Logical_OR)
- [MDN - Strict Equality (===)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Strict_equality)

---

<div align="center">

**Dibuat dengan ❤️ untuk pembelajaran pemrograman**

</div>
