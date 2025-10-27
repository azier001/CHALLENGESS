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
    
    // Menentukan tingkat pertumbuhan berdasarkan posisi index
    // Index genap (0, 2, 4, ...) tumbuh 1 cm/hari
    // Index ganjil (1, 3, 5, ...) tumbuh 2 cm/hari
    const growthRate = index % 2 === 0 ? 1 : 2;
    
    // Menghitung tinggi akhir = tinggi awal + (tingkat pertumbuhan × jumlah hari)
    return height + (growthRate * days);
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
- Bunga 1 (index 0): 10 + (1 × 5) = **15 cm**
- Bunga 2 (index 1): 15 + (2 × 5) = **25 cm**
- Bunga 3 (index 2): 20 + (1 × 5) = **25 cm**
- Bunga 4 (index 3): 25 + (2 × 5) = **35 cm**
- Bunga 5 (index 4): 30 + (1 × 5) = **35 cm**

### Contoh 2: Pertumbuhan 10 Hari

```javascript
const tinggiAwal = [5, 10, 15];
const hari = 10;

const tinggiAkhir = sunflowerHeights(tinggiAwal, hari);

console.log(tinggiAkhir);
// Output: [15, 30, 25]
```

**Penjelasan:**
- Bunga 1 (index 0): 5 + (1 × 10) = **15 cm**
- Bunga 2 (index 1): 10 + (2 × 10) = **30 cm**
- Bunga 3 (index 2): 15 + (1 × 10) = **25 cm**

### Contoh 3: Tanpa Pertumbuhan (0 Hari)

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
   - Cek posisi index (genap atau ganjil) menggunakan modulo (`%`)
   - Tentukan tingkat pertumbuhan (1 atau 2 cm/hari)
   - Hitung tinggi akhir dengan rumus: `tinggi awal + (tingkat pertumbuhan × hari)`
4. **Mengembalikan array baru** dengan semua tinggi akhir

---

## 💡 Tips untuk Pemula

- **Operator `%` (modulo)**: Menghasilkan sisa pembagian. Jika `index % 2 === 0`, artinya index adalah bilangan genap.
- **Method `.map()`**: Membuat array baru dengan mengubah setiap elemen array lama tanpa mengubah array aslinya.
- **Arrow function**: `(height, index) => { ... }` adalah cara penulisan fungsi modern di JavaScript.
- **Ternary operator**: `kondisi ? nilaiJikaBenar : nilaiJikaSalah` adalah cara singkat menulis if-else.

---

## ⚠️ Catatan Penting

- Fungsi ini **tidak mengubah** array `initialHeights` yang asli
- Index dimulai dari 0 (zero-based indexing)
- Parameter `days` sebaiknya berupa bilangan bulat positif untuk hasil yang logis
- Fungsi akan tetap berjalan meskipun array kosong, dan akan mengembalikan array kosong juga

---

**Selamat mencoba! 🌻🌱**
