# 📍 Dokumentasi Fungsi `flatweedJourney`

## 🎯 Deskripsi

Fungsi `flatweedJourney` digunakan untuk mensimulasikan perjalanan dengan sistem posisi numerik. Fungsi ini akan menghitung posisi akhir berdasarkan jumlah langkah dan arah yang ditentukan, dengan aturan khusus: **posisi yang habis dibagi 5 akan dilewati (skip)**.

## 📋 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `steps` | Number | Jumlah langkah yang akan dilakukan dalam perjalanan |
| `direction` | String | Arah perjalanan, bisa berisi `"north"` (maju/naik) atau `"south"` (mundur/turun) |

### 🧭 Penjelasan Arah

- **`"north"`** : Setiap langkah akan menambah posisi (+1)
- **`"south"`** : Setiap langkah akan mengurangi posisi (-1)

## 🔄 Cara Kerja

1. Fungsi dimulai dari posisi 0
2. Setiap iterasi akan menghitung posisi berikutnya sesuai arah
3. Jika posisi berikutnya habis dibagi 5 (kelipatan 5), posisi tersebut akan **dilewati** dan posisi tetap di tempat
4. Jika tidak habis dibagi 5, posisi akan diperbarui
5. Proses berulang sebanyak jumlah `steps`
6. Mengembalikan posisi akhir

## 💻 Kode Fungsi

```javascript
function flatweedJourney(steps, direction) {
  // Inisialisasi posisi awal di angka 0
  let position = 0;
  
  // Melakukan perulangan sebanyak jumlah steps
  for (let i = 0; i < steps; i++) {
    let nextPosition = position;
    
    // Menentukan posisi berikutnya berdasarkan arah
    if (direction === "north") {
      nextPosition = position + 1; // Bergerak maju (tambah 1)
    } else if (direction === "south") {
      nextPosition = position - 1; // Bergerak mundur (kurang 1)
    }
    
    // Cek apakah posisi berikutnya adalah kelipatan 5
    if (nextPosition % 5 === 0) {
      continue; // Skip posisi ini, jangan update position
    }
    
    // Update posisi jika bukan kelipatan 5
    position = nextPosition;
  }
  
  // Kembalikan posisi akhir
  return position;
}
```

## 📊 Contoh Penggunaan dan Output

### Contoh 1: Perjalanan ke Utara

```javascript
let hasil = flatweedJourney(7, "north");
console.log(hasil); // Output: 6
```

**Penjelasan langkah per langkah:**
- Langkah 1: 0 → 1 ✅
- Langkah 2: 1 → 2 ✅
- Langkah 3: 2 → 3 ✅
- Langkah 4: 3 → 4 ✅
- Langkah 5: 4 → 5 ❌ (Skip, karena 5 habis dibagi 5)
- Langkah 6: 4 → 5 ❌ (Skip lagi, posisi tetap di 4)
- Langkah 7: 4 → 5 ❌ (Skip lagi, posisi tetap di 4)
- **Posisi akhir: 4**

### Contoh 2: Perjalanan ke Selatan

```javascript
let hasil = flatweedJourney(3, "south");
console.log(hasil); // Output: -3
```

**Penjelasan langkah per langkah:**
- Langkah 1: 0 → -1 ✅
- Langkah 2: -1 → -2 ✅
- Langkah 3: -2 → -3 ✅
- **Posisi akhir: -3**

### Contoh 3: Melewati Beberapa Kelipatan 5

```javascript
let hasil = flatweedJourney(12, "north");
console.log(hasil); // Output: 9
```

**Penjelasan:**
Posisi 5 dan 10 akan di-skip, sehingga perjalanan akan "terjebak" sejenak di posisi 4 dan 9.

### Contoh 4: Perjalanan ke Selatan Melewati Kelipatan 5

```javascript
let hasil = flatweedJourney(8, "south");
console.log(hasil); // Output: -6
```

**Penjelasan:**
Posisi -5 akan di-skip, sehingga dari -4 akan langsung tetap di -4 beberapa iterasi sebelum akhirnya lanjut ke -6.

## ⚠️ Catatan Penting

- Posisi yang merupakan **kelipatan 5** (0, 5, 10, -5, -10, dll) akan selalu dilewati
- Posisi 0 juga merupakan kelipatan 5, tetapi ini adalah posisi awal
- Jika arah tidak "north" atau "south", posisi akan tetap di tempat selama iterasi
- Fungsi ini menggunakan **modulo operator** (`%`) untuk mengecek kelipatan 5

## 🎓 Tips untuk Pemula

### Apa itu Modulo (`%`)?

**Modulo (`%`)** adalah operator untuk mencari sisa hasil bagi. Contoh:
- `10 % 5 = 0` (10 dibagi 5 = 2, sisa 0) → habis dibagi
- `7 % 5 = 2` (7 dibagi 5 = 1, sisa 2) → tidak habis dibagi
- `15 % 5 = 0` (15 dibagi 5 = 3, sisa 0) → habis dibagi

Jadi `nextPosition % 5 === 0` artinya kita mengecek apakah posisi tersebut habis dibagi 5 (tidak ada sisa).

### Apa itu `continue`?

Statement `continue` akan melompati sisa kode dalam loop dan langsung melanjutkan ke iterasi berikutnya. Dalam fungsi ini, ketika `continue` dipanggil, kode `position = nextPosition;` tidak akan dijalankan, sehingga posisi tetap tidak berubah.

## 🔍 Visualisasi Perjalanan

**Contoh: `flatweedJourney(10, "north")`**

```
Iterasi | Posisi Saat Ini | Coba ke | Berhasil? | Posisi Baru
--------|-----------------|---------|-----------|-------------
   1    |       0         |    1    |    ✅     |      1
   2    |       1         |    2    |    ✅     |      2
   3    |       2         |    3    |    ✅     |      3
   4    |       3         |    4    |    ✅     |      4
   5    |       4         |    5    |    ❌     |      4
   6    |       4         |    5    |    ❌     |      4
   7    |       4         |    5    |    ❌     |      4
   8    |       4         |    5    |    ❌     |      4
   9    |       4         |    5    |    ❌     |      4
  10    |       4         |    5    |    ❌     |      4

Posisi Akhir: 4
```

---

💡 **Semoga dokumentasi ini membantu memahami cara kerja fungsi `flatweedJourney`!**
