# 🌻 Dokumentasi Fungsi `sunflowerHeights`

## 📋 Deskripsi

Fungsi `sunflowerHeights` digunakan untuk menghitung tinggi bunga matahari setelah beberapa hari pertumbuhan. Setiap bunga matahari memiliki tingkat pertumbuhan yang berbeda berdasarkan posisinya:
- Bunga matahari pada posisi **genap** (index 0, 2, 4, ...) tumbuh **1 cm per hari**
- Bunga matahari pada posisi **ganjil** (index 1, 3, 5, ...) tumbuh **2 cm per hari**

Fungsi ini akan mengembalikan array baru yang berisi tinggi akhir dari setiap bunga matahari setelah periode pertumbuhan tertentu.

---

## 📦 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `initialHeights` | `Array<Number>` | Array yang berisi tinggi awal setiap bunga matahari (dalam cm) |
| `days` | `Number` | Jumlah hari pertumbuhan bunga matahari |

---

## 🔄 Return Value

**Tipe**: `Array<Number>`

Mengembalikan array baru yang berisi tinggi akhir setiap bunga matahari setelah masa pertumbuhan.

---

## 📊 Tabel Tingkat Pertumbuhan

| Posisi Index | Kategori | Pertumbuhan per Hari |
|--------------|----------|---------------------|
| 0, 2, 4, 6, ... | Genap | 1 cm/hari |
| 1, 3, 5, 7, ... | Ganjil | 2 cm/hari |

---

## 💻 Kode Fungsi

```javascript
function sunflowerHeights(initialHeights, days) {
  // Menggunakan map untuk mengubah setiap tinggi awal menjadi tinggi akhir
  return initialHeights.map((height, index) => {
    
    // Cek apakah posisi index adalah genap
    if (index % 2 === 0) {
      // Index genap (0, 2, 4, ...): tumbuh 1 cm per hari
      return height + days;
      
    } else {
      // Index ganjil (1, 3, 5, ...): tumbuh 2 cm per hari
      return height + (days * 2);
    }
  });
}
```

---

## 🎯 Contoh Penggunaan

### Contoh 1: Pertumbuhan 5 Hari

```javascript
const tinggiAwal = [10, 15, 20, 25, 30];
const hari = 5;

const tinggiAkhir = sunflowerHeights(tinggiAwal, hari);

console.log(tinggiAkhir);
// Output: [15, 25, 25, 35, 35]
```

**Penjelasan:**
- Bunga 1 (index 0, genap): 10 + 5 = **15 cm**
- Bunga 2 (index 1, ganjil): 15 + (5 × 2) = **25 cm**
- Bunga 3 (index 2, genap): 20 + 5 = **25 cm**
- Bunga 4 (index 3, ganjil): 25 + (5 × 2) = **35 cm**
- Bunga 5 (index 4, genap): 30 + 5 = **35 cm**

### Contoh 2: Pertumbuhan 10 Hari

```javascript
const tinggiAwal = [5, 10, 15];
const hari = 10;

const tinggiAkhir = sunflowerHeights(tinggiAwal, hari);

console.log(tinggiAkhir);
// Output: [15, 30, 25]
```

**Penjelasan:**
- Bunga 1 (index 0, genap): 5 + 10 = **15 cm**
- Bunga 2 (index 1, ganjil): 10 + (10 × 2) = **30 cm**
- Bunga 3 (index 2, genap): 15 + 10 = **25 cm**

### Contoh 3: Pertumbuhan 3 Hari

```javascript
const tinggiAwal = [8, 12, 18, 20];
const hari = 3;

const tinggiAkhir = sunflowerHeights(tinggiAwal, hari);

console.log(tinggiAkhir);
// Output: [11, 18, 21, 26]
```

**Penjelasan:**
- Bunga 1 (index 0, genap): 8 + 3 = **11 cm**
- Bunga 2 (index 1, ganjil): 12 + (3 × 2) = **18 cm**
- Bunga 3 (index 2, genap): 18 + 3 = **21 cm**
- Bunga 4 (index 3, ganjil): 20 + (3 × 2) = **26 cm**

### Contoh 4: Tanpa Pertumbuhan (0 Hari)

```javascript
const tinggiAwal = [100, 200, 300];
const hari = 0;

const tinggiAkhir = sunflowerHeights(tinggiAwal, hari);

console.log(tinggiAkhir);
// Output: [100, 200, 300]
```

**Penjelasan:**
Tidak ada pertumbuhan karena jumlah hari = 0, sehingga tinggi akhir sama dengan tinggi awal.

---

## 🧠 Cara Kerja Fungsi

1. **Fungsi menerima 2 parameter**: array tinggi awal dan jumlah hari
2. **Menggunakan method `.map()`** untuk iterasi setiap bunga matahari
3. **Untuk setiap bunga**:
   - Cek posisi index menggunakan modulo (`index % 2 === 0`)
   - **Jika index genap**: tambahkan `days` ke tinggi awal
   - **Jika index ganjil**: tambahkan `days × 2` ke tinggi awal
4. **Mengembalikan array baru** dengan semua tinggi akhir

---

## 🔍 Visualisasi Pertumbuhan

Misalkan kita punya 4 bunga dengan tinggi awal [10, 10, 10, 10] selama 5 hari:

```
Hari ke-0:  [10, 10, 10, 10]
           
Setelah 5 hari:
Index 0 (genap):  10 + 5     = 15 cm  🌻
Index 1 (ganjil): 10 + (5×2) = 20 cm  🌻🌻
Index 2 (genap):  10 + 5     = 15 cm  🌻
Index 3 (ganjil): 10 + (5×2) = 20 cm  🌻🌻

Hasil akhir: [15, 20, 15, 20]
```

Bunga ganjil tumbuh **2x lebih cepat** dari bunga genap! 🚀

---

## 💡 Tips untuk Pemula

- **Operator `%` (modulo)**: Menghasilkan sisa pembagian. Jika `index % 2 === 0`, artinya index adalah bilangan genap (habis dibagi 2).
- **Method `.map()`**: Membuat array baru dengan mengubah setiap elemen array lama tanpa mengubah array aslinya.
- **Arrow function**: `(height, index) => { ... }` adalah cara penulisan fungsi modern di JavaScript.
- **if-else statement**: Digunakan untuk membuat keputusan berdasarkan kondisi tertentu.

---

## 🆚 Perbedaan dengan Ternary Operator

Kode ini bisa juga ditulis dengan ternary operator yang lebih ringkas:

```javascript
function sunflowerHeights(initialHeights, days) {
  return initialHeights.map((height, index) => {
    const growthRate = index % 2 === 0 ? 1 : 2;
    return height + (growthRate * days);
  });
}
```

Kedua cara menghasilkan output yang sama, namun:
- **if-else**: Lebih eksplisit dan mudah dibaca oleh pemula
- **Ternary operator**: Lebih ringkas untuk kondisi sederhana

---

## ⚠️ Catatan Penting

- Fungsi ini **tidak mengubah** array `initialHeights` yang asli
- Index dimulai dari 0 (zero-based indexing)
- Parameter `days` sebaiknya berupa bilangan bulat positif untuk hasil yang logis
- Fungsi akan tetap berjalan meskipun array kosong, dan akan mengembalikan array kosong juga
- Bunga pada posisi ganjil akan selalu tumbuh 2x lebih cepat dari bunga pada posisi genap

---

**Selamat mencoba! 🌻🌱**
