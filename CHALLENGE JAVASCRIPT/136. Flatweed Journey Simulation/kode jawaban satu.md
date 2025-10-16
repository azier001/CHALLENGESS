# 📍 Dokumentasi Fungsi `flatweedJourney`

## 🎯 Deskripsi

Fungsi `flatweedJourney` digunakan untuk mensimulasikan perjalanan dengan sistem posisi numerik. Fungsi ini akan menghitung posisi akhir berdasarkan jumlah langkah dan arah yang ditentukan, dengan aturan khusus: **ketika mencapai posisi yang habis dibagi 5, akan otomatis mundur satu langkah** (seperti menabrak penghalang).

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
2. Setiap iterasi akan menggerakkan posisi sesuai arah (north atau south)
3. Setelah bergerak, fungsi mengecek apakah posisi saat ini habis dibagi 5
4. Jika ya (kelipatan 5), posisi akan **mundur satu langkah** ke arah berlawanan
5. Proses berulang sebanyak jumlah `steps`
6. Mengembalikan posisi akhir

## 💻 Kode Fungsi

```javascript
function flatweedJourney(steps, direction) {
  // Inisialisasi posisi awal di angka 0
  let position = 0;
  
  // Melakukan perulangan sebanyak jumlah steps
  for (let i = 0; i < steps; i++) {
    
    // Gerakkan posisi sesuai arah
    if (direction === "north") {
      position++; // Bergerak maju (tambah 1)
    } else if (direction === "south") {
      position--; // Bergerak mundur (kurang 1)
    }
    
    // Cek apakah posisi saat ini adalah kelipatan 5
    if (position % 5 === 0) {
      // Jika ya, mundur satu langkah (arah berlawanan)
      if (direction === "north") {
        position--; // Mundur karena menabrak kelipatan 5
      } else if (direction === "south") {
        position++; // Maju (berlawanan arah south) karena menabrak kelipatan 5
      }
    }
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
- Langkah 1: 0 → 1 ✅ (tidak kelipatan 5)
- Langkah 2: 1 → 2 ✅ (tidak kelipatan 5)
- Langkah 3: 2 → 3 ✅ (tidak kelipatan 5)
- Langkah 4: 3 → 4 ✅ (tidak kelipatan 5)
- Langkah 5: 4 → 5 ❌ (kelipatan 5!) → mundur ke 4
- Langkah 6: 4 → 5 ❌ (kelipatan 5!) → mundur ke 4
- Langkah 7: 4 → 5 ❌ (kelipatan 5!) → mundur ke 4
- **Posisi akhir: 4**

> **Catatan:** Fungsi akan "terjebak" di posisi 4 karena setiap kali mencoba maju ke 5, akan dipaksa mundur lagi ke 4.

### Contoh 2: Perjalanan ke Selatan

```javascript
let hasil = flatweedJourney(3, "south");
console.log(hasil); // Output: -3
```

**Penjelasan langkah per langkah:**
- Langkah 1: 0 → -1 ✅ (tidak kelipatan 5)
- Langkah 2: -1 → -2 ✅ (tidak kelipatan 5)
- Langkah 3: -2 → -3 ✅ (tidak kelipatan 5)
- **Posisi akhir: -3**

### Contoh 3: Terjebak di Kelipatan 5 (Arah Utara)

```javascript
let hasil = flatweedJourney(10, "north");
console.log(hasil); // Output: 4
```

**Penjelasan:**
Setelah mencapai posisi 4, setiap langkah berikutnya akan mencoba ke 5 tetapi selalu mundur ke 4. Posisi akhir tetap di 4.

### Contoh 4: Perjalanan ke Selatan Melewati Kelipatan 5

```javascript
let hasil = flatweedJourney(7, "south");
console.log(hasil); // Output: -6
```

**Penjelasan langkah per langkah:**
- Langkah 1: 0 → -1 ✅
- Langkah 2: -1 → -2 ✅
- Langkah 3: -2 → -3 ✅
- Langkah 4: -3 → -4 ✅
- Langkah 5: -4 → -5 ❌ (kelipatan 5!) → maju ke -4
- Langkah 6: -4 → -5 ❌ (kelipatan 5!) → maju ke -4
- Langkah 7: -4 → -5 ❌ (kelipatan 5!) → maju ke -4
- **Posisi akhir: -4**

## ⚠️ Catatan Penting

- Posisi yang merupakan **kelipatan 5** (5, 10, -5, -10, dll) tidak bisa ditempati secara permanen
- Ketika mencapai kelipatan 5, posisi akan **otomatis mundur satu langkah** ke arah berlawanan
- Posisi 0 adalah posisi awal dan merupakan kelipatan 5, tetapi tidak ada pengecekan di awal
- Fungsi akan "terjebak" sebelum kelipatan 5 jika jumlah langkah tidak cukup untuk melewatinya
- Fungsi ini menggunakan **modulo operator** (`%`) untuk mengecek kelipatan 5

## 🎓 Tips untuk Pemula

### Apa itu Modulo (`%`)?

**Modulo (`%`)** adalah operator untuk mencari sisa hasil bagi. Contoh:
- `10 % 5 = 0` (10 dibagi 5 = 2, sisa 0) → habis dibagi
- `7 % 5 = 2` (7 dibagi 5 = 1, sisa 2) → tidak habis dibagi
- `15 % 5 = 0` (15 dibagi 5 = 3, sisa 0) → habis dibagi

Jadi `position % 5 === 0` artinya kita mengecek apakah posisi tersebut habis dibagi 5 (tidak ada sisa).

### Perbedaan dengan Versi Sebelumnya

Pada versi ini, **tidak menggunakan `continue`**. Sebaliknya, setelah bergerak ke posisi baru:
1. Posisi langsung diubah dulu
2. Kemudian dicek apakah kelipatan 5
3. Jika ya, posisi di-undo (dikembalikan satu langkah)

Ini berbeda dengan versi yang menggunakan `continue` yang tidak mengubah posisi sama sekali.

## 🔍 Visualisasi Perjalanan

**Contoh: `flatweedJourney(10, "north")`**

```
Iterasi | Posisi Awal | Gerak ke | Kelipatan 5? | Mundur ke | Posisi Akhir
--------|-------------|----------|--------------|-----------|-------------
   1    |      0      |    1     |      ❌      |     -     |      1
   2    |      1      |    2     |      ❌      |     -     |      2
   3    |      2      |    3     |      ❌      |     -     |      3
   4    |      3      |    4     |      ❌      |     -     |      4
   5    |      4      |    5     |      ✅      |     4     |      4
   6    |      4      |    5     |      ✅      |     4     |      4
   7    |      4      |    5     |      ✅      |     4     |      4
   8    |      4      |    5     |      ✅      |     4     |      4
   9    |      4      |    5     |      ✅      |     4     |      4
  10    |      4      |    5     |      ✅      |     4     |      4

Posisi Akhir: 4
```

**Contoh: `flatweedJourney(10, "south")`**

```
Iterasi | Posisi Awal | Gerak ke | Kelipatan 5? | Maju ke | Posisi Akhir
--------|-------------|----------|--------------|---------|-------------
   1    |      0      |   -1     |      ❌      |    -    |     -1
   2    |     -1      |   -2     |      ❌      |    -    |     -2
   3    |     -2      |   -3     |      ❌      |    -    |     -3
   4    |     -3      |   -4     |      ❌      |    -    |     -4
   5    |     -4      |   -5     |      ✅      |   -4    |     -4
   6    |     -4      |   -5     |      ✅      |   -4    |     -4
   7    |     -4      |   -5     |      ✅      |   -4    |     -4
   8    |     -4      |   -5     |      ✅      |   -4    |     -4
   9    |     -4      |   -5     |      ✅      |   -4    |     -4
  10    |     -4      |   -5     |      ✅      |   -4    |     -4

Posisi Akhir: -4
```

## 🎮 Analogi Sederhana

Bayangkan kamu sedang bermain game platformer:
- Kamu berjalan ke kanan (north) atau ke kiri (south)
- Setiap posisi yang merupakan kelipatan 5 adalah **dinding penghalang**
- Ketika kamu menabrak dinding, kamu akan terpental mundur satu langkah
- Kamu akan "застряжка" (terjebak) di depan dinding jika terus mencoba melewatinya

---

💡 **Semoga dokumentasi ini membantu memahami cara kerja fungsi `flatweedJourney`!**
