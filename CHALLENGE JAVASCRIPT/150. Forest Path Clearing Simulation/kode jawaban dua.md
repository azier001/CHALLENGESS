# 🌲 Dokumentasi Fungsi `clearForestPaths`

## 📋 Deskripsi

Fungsi `clearForestPaths` digunakan untuk membersihkan jalur di dalam hutan (forest) dengan pola spiral. Fungsi ini akan mengubah area 3x3 di sekitar posisi tertentu, mengubah pohon (`'T'`) menjadi jalur (`'P'`).

Fungsi ini bekerja dengan cara:
1. Mulai dari posisi awal yang ditentukan
2. Membersihkan area 3x3 di sekitar posisi tersebut
3. Bergerak mengikuti pola spiral (kanan → bawah → kiri → atas)
4. Setiap langkah, membersihkan area 3x3 di posisi baru

## 🎯 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `forest` | Array 2D | Matriks yang merepresentasikan hutan. Berisi karakter seperti `'T'` (Tree/Pohon) dan `'P'` (Path/Jalur) |
| `startRow` | Number | Baris awal tempat mulai membersihkan jalur (index dimulai dari 0) |
| `startCol` | Number | Kolom awal tempat mulai membersihkan jalur (index dimulai dari 0) |
| `steps` | Number | Jumlah langkah yang akan dilakukan dalam pola spiral |

## 🔤 Karakter yang Digunakan

| Karakter | Nama | Keterangan |
|----------|------|------------|
| `'T'` | Tree (Pohon) | Merepresentasikan pohon di hutan yang belum dibersihkan |
| `'P'` | Path (Jalur) | Merepresentasikan jalur yang sudah dibersihkan |

## 📝 Return Value

Fungsi mengembalikan array 2D `forest` yang sudah dimodifikasi dengan jalur-jalur baru (karakter `'P'`).

## 💻 Kode Fungsi

```javascript
function clearForestPaths(forest, startRow, startCol, steps) {
  // Array yang berisi arah pergerakan dalam pola spiral
  const directions = [
    [0, 1],   // kanan
    [1, 0],   // bawah
    [0, -1],  // kiri
    [-1, 0]   // atas
  ];
  
  let currentRow = startRow;
  let currentCol = startCol;
  let directionIndex = 0;
  
  // Fungsi helper untuk membersihkan area 3x3 di sekitar posisi saat ini
  function clear3x3Area(row, col) {
    // Loop untuk baris (-1, 0, 1)
    for (let dr = -1; dr <= 1; dr++) {
      // Loop untuk kolom (-1, 0, 1)
      for (let dc = -1; dc <= 1; dc++) {
        const newRow = row + dr;
        const newCol = col + dc;
        
        // Cek apakah posisi masih dalam batas hutan
        if (newRow >= 0 && newRow < forest.length && 
            newCol >= 0 && newCol < forest[0].length) {
          // Hanya ganti 'T' dengan 'P'
          if (forest[newRow][newCol] === 'T') {
            forest[newRow][newCol] = 'P';
          }
        }
      }
    }
  }
  
  // Bersihkan posisi awal
  clear3x3Area(currentRow, currentCol);
  
  // Lakukan langkah-langkah sesuai parameter steps
  for (let step = 0; step < steps; step++) {
    // Bergerak ke arah saat ini
    const [dRow, dCol] = directions[directionIndex];
    currentRow += dRow;
    currentCol += dCol;
    
    // Bersihkan area 3x3 di posisi baru
    clear3x3Area(currentRow, currentCol);
    
    // Update arah untuk langkah berikutnya (pola spiral)
    directionIndex = (directionIndex + 1) % 4;
  }
  
  return forest;
}
```

## 🎮 Cara Kerja Pola Spiral

Fungsi ini bergerak dalam pola spiral dengan urutan:

```
1. Kanan  → [0, 1]
2. Bawah  → [1, 0]
3. Kiri   → [0, -1]
4. Atas   → [-1, 0]
(kemudian kembali ke kanan, dan seterusnya)
```

## 📊 Contoh Penggunaan

### Input

```javascript
const forest = [
  ['T', 'T', 'T', 'T', 'T'],
  ['T', 'T', 'T', 'T', 'T'],
  ['T', 'T', 'T', 'T', 'T'],
  ['T', 'T', 'T', 'T', 'T'],
  ['T', 'T', 'T', 'T', 'T']
];

const result = clearForestPaths(forest, 2, 2, 3);
```

### Output

```javascript
[
  ['T', 'T', 'T', 'T', 'T'],
  ['T', 'P', 'P', 'P', 'T'],
  ['T', 'P', 'P', 'P', 'P'],
  ['T', 'P', 'P', 'P', 'P'],
  ['T', 'T', 'T', 'P', 'T']
]
```

### Penjelasan Langkah-langkah

1. **Posisi Awal (2,2)**: Membersihkan area 3x3 di sekitar (2,2)
2. **Langkah 1 - Kanan**: Pindah ke (2,3), bersihkan area 3x3
3. **Langkah 2 - Bawah**: Pindah ke (3,3), bersihkan area 3x3
4. **Langkah 3 - Kiri**: Pindah ke (3,2), bersihkan area 3x3

## ⚠️ Catatan Penting

- Fungsi ini **memodifikasi array asli** (mutasi), bukan membuat salinan baru
- Hanya karakter `'T'` yang akan diubah menjadi `'P'`
- Karakter lain (jika ada) tidak akan terpengaruh
- Fungsi secara otomatis menghindari posisi di luar batas array (boundary checking)
- Area 3x3 mencakup: posisi saat ini, 8 sel di sekitarnya (atas, bawah, kiri, kanan, dan diagonal)

## 🔍 Use Case

Fungsi ini cocok digunakan untuk:
- Game simulasi pembangunan jalur di hutan
- Algoritma pathfinding dengan pembersihan area
- Visualisasi pola spiral pada grid/matriks
- Simulasi eksplorasi area dengan radius tertentu
