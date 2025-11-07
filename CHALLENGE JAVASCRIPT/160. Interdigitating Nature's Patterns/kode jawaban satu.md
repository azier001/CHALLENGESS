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
4. Jika salah satu array kosong di awal, akan menambahkan string kosong
5. Mengembalikan array hasil gabungan

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
    } else if (strata1.length === 0 && i === 0) {
      // Jika array pertama kosong, tambahkan string kosong
      interdigitated.push('');
    }
    
    // Tambahkan elemen dari array kedua jika masih ada
    if (i < strata2.length) {
      interdigitated.push(strata2[i]);
    } else if (strata2.length === 0 && i === 0) {
      // Jika array kedua kosong, tambahkan string kosong
      interdigitated.push('');
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

### Contoh 2: Array dengan Panjang Berbeda

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

### Contoh 3: Array Kosong

```javascript
const array1 = [];
const array2 = ['X', 'Y', 'Z'];

const hasil = interdigitate(array1, array2);
console.log(hasil);
```

**Output:**
```javascript
['', 'X', 'Y', 'Z']
```

**Penjelasan:** Jika array1 kosong, fungsi akan menambahkan string kosong `''` di awal sebelum elemen dari array2.

---

### Contoh 4: Kedua Array Kosong

```javascript
const array1 = [];
const array2 = [];

const hasil = interdigitate(array1, array2);
console.log(hasil);
```

**Output:**
```javascript
['', '']
```

**Penjelasan:** Jika kedua array kosong, hasil akan berisi dua string kosong.

---

## 📝 Catatan Penting

- ⚠️ Fungsi ini akan menambahkan string kosong (`''`) jika salah satu atau kedua array kosong
- 🔢 Urutan penggabungan: elemen dari `strata1` selalu diambil terlebih dahulu, baru `strata2`
- 📏 Fungsi akan terus berjalan hingga semua elemen dari array terpanjang diproses
- 💡 Fungsi ini tidak mengubah array asli (non-destructive)

---

## 🎨 Visualisasi Proses

```
strata1: [A, B, C]
strata2: [1, 2, 3]

Iterasi 1: Ambil A → Ambil 1
Iterasi 2: Ambil B → Ambil 2
Iterasi 3: Ambil C → Ambil 3

Hasil: [A, 1, B, 2, C, 3]
```

---

## 🚀 Return Value

| Tipe | Deskripsi |
|------|-----------|
| Array | Array baru yang berisi gabungan elemen dari kedua array secara berselang-seling |

---

## 💡 Tips Penggunaan

- Gunakan fungsi ini ketika Anda perlu menggabungkan dua kumpulan data secara bergantian
- Cocok untuk kasus seperti: menggabungkan pertanyaan dan jawaban, membuat pola berselang-seling, atau menyusun data secara paralel
- Pastikan kedua array berisi tipe data yang kompatibel untuk hasil yang optimal
