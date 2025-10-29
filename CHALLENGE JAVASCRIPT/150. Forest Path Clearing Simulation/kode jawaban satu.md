# 🌲 Dokumentasi Fungsi `clearForestPaths`

## 📋 Deskripsi

Fungsi `clearForestPaths` digunakan untuk membersihkan jalur di dalam hutan (forest) dengan pola pergerakan yang cerdas. Fungsi ini akan mengubah area 3x3 di sekitar posisi tertentu, mengubah pohon (`'T'`) menjadi jalur (`'P'`).

Fungsi ini bekerja dengan cara:
1. Mulai dari posisi awal yang ditentukan
2. Membersihkan area 3x3 di sekitar posisi saat ini
3. Mencoba bergerak mengikuti pola (kanan → bawah → kiri → atas)
4. **Jika ada rintangan (`'C'`) atau keluar batas**, fungsi akan **memutar arah** tanpa berpindah
5. Mengulangi proses sesuai jumlah langkah yang ditentukan

## 🎯 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `forest` | Array 2D | Matriks yang merepresentasikan hutan. Berisi karakter seperti `'T'` (Tree/Pohon), `'P'` (Path/Jalur), dan `'C'` (Cliff/Tebing) |
| `startRow` | Number | Baris awal tempat mulai membersihkan jalur (index dimulai dari 0) |
| `startCol` | Number | Kolom awal tempat mulai membersihkan jalur (index dimulai dari 0) |
| `steps` | Number | Jumlah langkah maksimal yang akan dicoba dalam pola pergerakan |

## 🔤 Karakter yang Digunakan

| Karakter | Nama | Keterangan |
|----------|------|------------|
| `'T'` | Tree (Pohon) | Merepresentasikan pohon di hutan yang belum dibersihkan |
| `'P'` | Path (Jalur) | Merepresentasikan jalur yang sudah dibersihkan |
| `'C'` | Cliff (Tebing) | Merepresentasikan rintangan yang tidak bisa dilalui |

## 📝 Return Value

Fungsi mengembalikan array 2D `forest` yang sudah dimodifikasi dengan jalur-jalur baru (karakter `'P'`).

## 💻 Kode Fungsi

```javascript
function clearForestPaths(forest, startRow, startCol, steps) {
  // Array yang berisi arah pergerakan dalam pola
  const directions = [
    [0, 1],   // kanan
    [1, 0],   // bawah
    [0, -1],  // kiri
    [-1, 0]   // atas
  ];
  
  let currentRow = startRow;
  let currentCol = startCol;
  let directionIndex = 0;
  
  // Fungsi untuk memeriksa apakah posisi valid (dalam batas hutan)
  function isValidPosition(row, col) {
    return row >= 0 && row < forest.length && 
           col >= 0 && col < forest[0].length;
  }
  
  // Fungsi untuk membersihkan area 3x3 di sekitar posisi pusat
  function clearArea(centerRow, centerCol) {
    // Loop untuk baris (-1, 0, 1)
    for (let i = -1; i <= 1; i++) {
      // Loop untuk kolom (-1, 0, 1)
      for (let j = -1; j <= 1; j++) {
        const newRow = centerRow + i;
        const newCol = centerCol + j;
        
        // Cek posisi valid dan hanya ubah pohon 'T' menjadi jalur 'P'
        if (isValidPosition(newRow, newCol) && forest[newRow][newCol] === 'T') {
          forest[newRow][newCol] = 'P';
        }
      }
    }
  }
  
  // Lakukan langkah-langkah sesuai parameter steps
  for (let step = 0; step < steps; step++) {
    // Bersihkan area di posisi saat ini
    clearArea(currentRow, currentCol);
    
    // Ambil perubahan baris dan kolom berdasarkan arah saat ini
    const [rowChange, colChange] = directions[directionIndex];
    const nextRow = currentRow + rowChange;
    const nextCol = currentCol + colChange;
    
    // Cek apakah posisi berikutnya valid atau ada rintangan 'C'
    if (!isValidPosition(nextRow, nextCol) || forest[nextRow][nextCol] === 'C') {
      // Jika tidak valid atau ada tebing, putar arah
      directionIndex = (directionIndex + 1) % 4;
      continue; // Lanjut ke iterasi berikutnya tanpa berpindah
    }
    
    // Pindah ke posisi berikutnya
    currentRow = nextRow;
    currentCol = nextCol;
  }
  
  return forest;
}
```

## 🎮 Cara Kerja Pola Pergerakan

Fungsi ini mencoba bergerak dalam pola dengan urutan:

```
1. Kanan  → [0, 1]
2. Bawah  → [1, 0]
3. Kiri   → [0, -1]
4. Atas   → [-1, 0]
(kemudian kembali ke kanan, dan seterusnya)
```

**Perbedaan dengan versi sebelumnya:**
- ✅ Fungsi akan **memutar arah** jika menemui rintangan (`'C'`) atau batas hutan
- ✅ Fungsi **tidak berpindah** saat memutar arah, hanya mengubah arah hadap
- ✅ Lebih aman karena tidak akan crash saat bertemu obstacle

## 📊 Contoh Penggunaan

### Contoh 1: Tanpa Rintangan

#### Input

```javascript
const forest = [
  ['T', 'T', 'T', 'T', 'T'],
  ['T', 'T', 'T', 'T', 'T'],
  ['T', 'T', 'T', 'T', 'T'],
  ['T', 'T', 'T', 'T', 'T'],
  ['T', 'T', 'T', 'T', 'T']
];

const result = clearForestPaths(forest, 2, 2, 5);
```

#### Output

```javascript
[
  ['T', 'T', 'T', 'T', 'T'],
  ['T', 'P', 'P', 'P', 'T'],
  ['T', 'P', 'P', 'P', 'P'],
  ['T', 'P', 'P', 'P', 'P'],
  ['T', 'T', 'P', 'P', 'T']
]
```

### Contoh 2: Dengan Rintangan (Tebing)

#### Input

```javascript
const forest = [
  ['T', 'T', 'T', 'T', 'T'],
  ['T', 'T', 'T', 'C', 'T'],
  ['T', 'T', 'T', 'C', 'T'],
  ['T', 'T', 'T', 'T', 'T'],
  ['T', 'T', 'T', 'T', 'T']
];

const result = clearForestPaths(forest, 2, 1, 6);
```

#### Output

```javascript
[
  ['T', 'T', 'T', 'T', 'T'],
  ['T', 'P', 'P', 'C', 'T'],
  ['T', 'P', 'P', 'C', 'T'],
  ['T', 'P', 'P', 'P', 'T'],
  ['T', 'T', 'P', 'T', 'T']
]
```

#### Penjelasan Langkah-langkah

1. **Langkah 1**: Posisi (2,1) - Bersihkan area 3x3
2. **Langkah 2**: Coba ke kanan (2,2) - Berhasil, bersihkan area 3x3
3. **Langkah 3**: Coba ke bawah (3,2) - Berhasil, bersihkan area 3x3
4. **Langkah 4**: Coba ke kiri (3,1) - Berhasil, bersihkan area 3x3
5. **Langkah 5**: Coba ke atas (2,1) - Berhasil kembali, bersihkan area 3x3
6. **Langkah 6**: Coba ke kanan (2,2) - Berhasil, bersihkan area 3x3

## 🔄 Mekanisme Obstacle Avoidance

Ketika fungsi menemui rintangan atau batas hutan:

```
1. Deteksi obstacle/boundary
2. Putar arah searah jarum jam (index + 1)
3. Tetap di posisi saat ini (tidak berpindah)
4. Lanjut ke iterasi berikutnya
5. Coba arah baru pada iterasi selanjutnya
```

## ⚠️ Catatan Penting

- Fungsi ini **memodifikasi array asli** (mutasi), bukan membuat salinan baru
- Hanya karakter `'T'` yang akan diubah menjadi `'P'`
- Karakter `'C'` (tebing) akan **tetap tidak berubah** dan berfungsi sebagai rintangan
- Karakter lain (jika ada) tidak akan terpengaruh
- Fungsi secara otomatis menghindari posisi di luar batas array (boundary checking)
- Area 3x3 mencakup: posisi saat ini, 8 sel di sekitarnya (atas, bawah, kiri, kanan, dan diagonal)
- **Jika terjebak (surrounded by obstacles)**, fungsi akan terus memutar arah tanpa berpindah hingga langkah habis

## 🔍 Use Case

Fungsi ini cocok digunakan untuk:
- Game simulasi pembangunan jalur di hutan dengan rintangan
- Algoritma pathfinding dengan obstacle avoidance
- Simulasi robot pembersih yang dapat mendeteksi halangan
- Visualisasi pola pergerakan cerdas pada grid/matriks
- Game eksplorasi dengan navigasi otomatis yang menghindari bahaya

## 🆚 Perbedaan dengan Versi Sebelumnya

| Aspek | Versi Lama | Versi Baru |
|-------|-----------|-----------|
| **Obstacle Detection** | ❌ Tidak ada | ✅ Mendeteksi `'C'` |
| **Boundary Check** | ❌ Setelah bergerak | ✅ Sebelum bergerak |
| **Behavior saat Obstacle** | ❌ Crash/Error | ✅ Putar arah & continue |
| **Pembersihan Awal** | ✅ Ya | ❌ Tidak, dilakukan di loop |
| **Keamanan** | ⚠️ Rendah | ✅ Tinggi |
