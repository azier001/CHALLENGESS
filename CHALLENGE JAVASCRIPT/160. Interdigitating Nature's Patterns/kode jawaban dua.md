# 📚 Dokumentasi Fungsi `interdigitate`

## 🎯 Deskripsi

Fungsi `interdigitate` adalah fungsi yang menggabungkan dua array dengan cara **berselang-seling** (interleaving). Fungsi ini akan mengambil elemen dari array pertama dan array kedua secara bergantian, kemudian menggabungkannya menjadi satu array baru.

Bayangkan seperti menyusun kartu remi: Anda mengambil satu kartu dari tumpukan kiri, lalu satu kartu dari tumpukan kanan, dan seterusnya secara bergantian.

---

## 📋 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `strata1` | Array | Array pertama yang akan digabungkan |
| `strata2` | Array | Array kedua yang akan digabungkan |

---

## 🔄 Cara Kerja

1. Fungsi mencari panjang maksimal dari kedua array
2. Melakukan iterasi sebanyak panjang array terpanjang
3. Pada setiap iterasi:
   - Mengambil elemen dari `strata1` (jika masih ada)
   - Mengambil elemen dari `strata2` (jika masih ada)
4. Mengembalikan array hasil gabungan

---

## 💻 Kode Fungsi

```javascript
function interdigitate(strata1, strata2) {
  // Array untuk menampung hasil penggabungan
  const interdigitated = [];
  
  // Cari panjang maksimal dari kedua array
  const maxLength = Math.max(strata1.length, strata2.length);
  
  // Loop sebanyak panjang array terpanjang
  for (let i = 0; i < maxLength; i++) {
    // Tambahkan elemen dari array pertama jika masih ada
    if (i < strata1.length) {
      interdigitated.push(strata1[i]);
    }
    
    // Tambahkan elemen dari array kedua jika masih ada
    if (i < strata2.length) {
      interdigitated.push(strata2[i]);
    }
  }
  
  // Kembalikan array hasil gabungan
  return interdigitated;
}
```

---

## 📊 Contoh Penggunaan

### Contoh 1: Array dengan Panjang Sama

```javascript
const array1 = ['A', 'B', 'C'];
const array2 = ['1', '2', '3'];

const hasil = interdigitate(array1, array2);
console.log(hasil);
```

**Output:**
```javascript
['A', '1', 'B', '2', 'C', '3']
```

**Penjelasan:** Elemen dari kedua array diambil secara bergantian: A dari array1, 1 dari array2, B dari array1, 2 dari array2, dan seterusnya.

---

### Contoh 2: Array dengan Panjang Berbeda (Array Pertama Lebih Pendek)

```javascript
const array1 = ['Merah', 'Hijau'];
const array2 = ['🔴', '🟢', '🔵', '🟡'];

const hasil = interdigitate(array1, array2);
console.log(hasil);
```

**Output:**
```javascript
['Merah', '🔴', 'Hijau', '🟢', '🔵', '🟡']
```

**Penjelasan:** Setelah array1 habis, fungsi akan terus mengambil elemen dari array2 yang masih tersisa.

---

### Contoh 3: Array dengan Panjang Berbeda (Array Kedua Lebih Pendek)

```javascript
const array1 = ['Satu', 'Dua', 'Tiga', 'Empat'];
const array2 = ['1️⃣', '2️⃣'];

const hasil = interdigitate(array1, array2);
console.log(hasil);
```

**Output:**
```javascript
['Satu', '1️⃣', 'Dua', '2️⃣', 'Tiga', 'Empat']
```

**Penjelasan:** Setelah array2 habis, fungsi akan terus mengambil elemen dari array1 yang masih tersisa.

---

### Contoh 4: Salah Satu Array Kosong

```javascript
const array1 = [];
const array2 = ['X', 'Y', 'Z'];

const hasil = interdigitate(array1, array2);
console.log(hasil);
```

**Output:**
```javascript
['X', 'Y', 'Z']
```

**Penjelasan:** Jika salah satu array kosong, hasil akan berisi semua elemen dari array yang tidak kosong.

---

### Contoh 5: Kedua Array Kosong

```javascript
const array1 = [];
const array2 = [];

const hasil = interdigitate(array1, array2);
console.log(hasil);
```

**Output:**
```javascript
[]
```

**Penjelasan:** Jika kedua array kosong, hasil akan berupa array kosong.

---

### Contoh 6: Array dengan Tipe Data Campuran

```javascript
const array1 = [1, 3, 5, 7, 9];
const array2 = [2, 4, 6, 8];

const hasil = interdigitate(array1, array2);
console.log(hasil);
```

**Output:**
```javascript
[1, 2, 3, 4, 5, 6, 7, 8, 9]
```

**Penjelasan:** Fungsi bekerja dengan berbagai tipe data, termasuk angka. Hasilnya adalah urutan angka berselang-seling dengan elemen terakhir dari array terpanjang.

---

## 📝 Catatan Penting

- ✅ Fungsi ini **lebih sederhana** karena tidak menambahkan string kosong untuk array kosong
- 🔢 Urutan penggabungan: elemen dari `strata1` selalu diambil terlebih dahulu, baru `strata2`
- 📏 Fungsi akan terus berjalan hingga semua elemen dari array terpanjang diproses
- 💡 Fungsi ini tidak mengubah array asli (non-destructive)
- 🎯 Jika salah satu array lebih panjang, elemen sisanya akan ditambahkan di akhir

---

## 🎨 Visualisasi Proses

### Kasus 1: Array Sama Panjang
```
strata1: [A, B, C]
strata2: [1, 2, 3]

Iterasi 0: Ambil A → Ambil 1
Iterasi 1: Ambil B → Ambil 2
Iterasi 2: Ambil C → Ambil 3

Hasil: [A, 1, B, 2, C, 3]
```

### Kasus 2: Array Berbeda Panjang
```
strata1: [A, B]
strata2: [1, 2, 3, 4]

Iterasi 0: Ambil A → Ambil 1
Iterasi 1: Ambil B → Ambil 2
Iterasi 2: (strata1 habis) → Ambil 3
Iterasi 3: (strata1 habis) → Ambil 4

Hasil: [A, 1, B, 2, 3, 4]
```

---

## 🚀 Return Value

| Tipe | Deskripsi |
|------|-----------|
| Array | Array baru yang berisi gabungan elemen dari kedua array secara berselang-seling |

---

## 💡 Tips Penggunaan

- **Menggabungkan data paralel**: Cocok untuk menggabungkan label dan nilai, pertanyaan dan jawaban
- **Membuat pola**: Berguna untuk membuat pola berselang-seling dalam visualisasi atau UI
- **Merge sorted arrays**: Dapat digunakan untuk menggabungkan dua array dengan pola tertentu
- **Flexible length**: Tidak perlu khawatir tentang panjang array yang berbeda, fungsi akan menangani secara otomatis

---

## ⚡ Kompleksitas

- **Time Complexity**: O(n + m) dimana n dan m adalah panjang dari `strata1` dan `strata2`
- **Space Complexity**: O(n + m) untuk menyimpan array hasil

---

## 🔍 Perbedaan dengan Versi Sebelumnya

Versi ini **lebih sederhana** karena:
- ❌ Tidak menambahkan string kosong untuk array kosong
- ✅ Hasil lebih intuitif: array kosong menghasilkan array kosong
- ✅ Kode lebih ringkas dan mudah dipahami
