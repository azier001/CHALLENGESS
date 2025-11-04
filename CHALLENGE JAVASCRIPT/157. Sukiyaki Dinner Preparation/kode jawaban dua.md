# 🍲 Dokumentasi Fungsi `prepareSukiyaki`

## 📋 Deskripsi

Fungsi `prepareSukiyaki` adalah fungsi JavaScript yang digunakan untuk menggabungkan dua array (daging dan sayuran) secara berpasangan dan berselang-seling. Fungsi ini akan mengambil elemen dari array `meats` dan `vegetables` pada indeks yang sama, kemudian menyusunnya secara bergantian dalam satu array baru.

Fungsi ini sangat berguna ketika Anda ingin:
- Menyusun bahan masakan secara berpasangan (daging-sayuran)
- Menggabungkan dua daftar dengan pola bergantian berdasarkan indeks yang sama
- Membuat urutan data yang berpasangan dari dua sumber berbeda

---

## 🎯 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `meats` | `Array` | Array yang berisi daftar daging (atau elemen pertama yang ingin digabungkan) |
| `vegetables` | `Array` | Array yang berisi daftar sayuran (atau elemen kedua yang ingin digabungkan) |

### 💡 Catatan Penting:
- Fungsi ini akan melakukan iterasi sebanyak panjang array `meats`
- **Penting**: Pastikan panjang `vegetables` minimal sama atau lebih panjang dari `meats`, jika tidak akan terjadi `undefined`
- Setiap elemen daging akan dipasangkan dengan sayuran pada indeks yang sama

---

## 🔄 Return Value

**Tipe:** `Array`

Mengembalikan array baru yang berisi elemen dari kedua array input secara berselang-seling, dengan pola: daging[0], sayuran[0], daging[1], sayuran[1], dst.

---

## 📝 Source Code

```javascript
function prepareSukiyaki(meats, vegetables) {
  // Array untuk menyimpan bahan-bahan sukiyaki
  const ingredients = [];
  
  // Loop sebanyak panjang array meats
  for (let i = 0; i < meats.length; i++) {
    // Tambahkan daging pada indeks ke-i
    ingredients.push(meats[i]);
    
    // Tambahkan sayuran pada indeks ke-i
    ingredients.push(vegetables[i]);
  }
  
  // Kembalikan array bahan-bahan yang sudah disusun
  return ingredients;
}
```

---

## 🎬 Contoh Penggunaan

### Contoh 1: Array dengan Panjang Sama (Ideal)

```javascript
const daging = ['🥩 Beef', '🐔 Chicken', '🐷 Pork'];
const sayuran = ['🥬 Bok Choy', '🍄 Mushroom', '🧅 Onion'];

const sukiyaki = prepareSukiyaki(daging, sayuran);
console.log(sukiyaki);
```

**Output:**
```javascript
[
  '🥩 Beef',
  '🥬 Bok Choy',
  '🐔 Chicken',
  '🍄 Mushroom',
  '🐷 Pork',
  '🧅 Onion'
]
```

---

### Contoh 2: Array Sayuran Lebih Panjang (Aman)

```javascript
const daging = ['🥩 Beef', '🐔 Chicken'];
const sayuran = ['🥬 Bok Choy', '🍄 Mushroom', '🧅 Onion', '🥕 Carrot'];

const sukiyaki = prepareSukiyaki(daging, sayuran);
console.log(sukiyaki);
```

**Output:**
```javascript
[
  '🥩 Beef',
  '🥬 Bok Choy',
  '🐔 Chicken',
  '🍄 Mushroom'
]
```

**Penjelasan:** Sayuran 'Onion' dan 'Carrot' tidak diproses karena tidak ada pasangan daging.

---

### Contoh 3: Array Daging Lebih Panjang (⚠️ Berbahaya!)

```javascript
const daging = ['🥩 Beef', '🐔 Chicken', '🐷 Pork', '🦐 Shrimp'];
const sayuran = ['🥬 Bok Choy', '🍄 Mushroom'];

const sukiyaki = prepareSukiyaki(daging, sayuran);
console.log(sukiyaki);
```

**Output:**
```javascript
[
  '🥩 Beef',
  '🥬 Bok Choy',
  '🐔 Chicken',
  '🍄 Mushroom',
  '🐷 Pork',
  undefined,        // ⚠️ Masalah di sini!
  '🦐 Shrimp',
  undefined         // ⚠️ Masalah di sini!
]
```

**⚠️ Perhatian:** Karena array `vegetables` lebih pendek, akan muncul nilai `undefined` yang tidak diinginkan!

---

### Contoh 4: Penggunaan dengan Data Numerik

```javascript
const angkaGanjil = [1, 3, 5];
const angkaGenap = [2, 4, 6];

const gabungan = prepareSukiyaki(angkaGanjil, angkaGenap);
console.log(gabungan);
```

**Output:**
```javascript
[1, 2, 3, 4, 5, 6]
```

---

## 🧮 Cara Kerja Fungsi

### Visualisasi Proses

Mari kita lihat bagaimana fungsi bekerja dengan contoh sederhana:

**Input:**
```
meats      = ['Beef', 'Chicken', 'Pork']
vegetables = ['Bok Choy', 'Mushroom', 'Onion']
```

**Proses:**

| Iterasi | Index (i) | meats[i] | vegetables[i] | ingredients |
|---------|-----------|----------|---------------|-------------|
| Mulai | - | - | - | `[]` |
| 1 | 0 | 'Beef' | 'Bok Choy' | `['Beef', 'Bok Choy']` |
| 2 | 1 | 'Chicken' | 'Mushroom' | `['Beef', 'Bok Choy', 'Chicken', 'Mushroom']` |
| 3 | 2 | 'Pork' | 'Onion' | `['Beef', 'Bok Choy', 'Chicken', 'Mushroom', 'Pork', 'Onion']` |

**Output Final:**
```
['Beef', 'Bok Choy', 'Chicken', 'Mushroom', 'Pork', 'Onion']
```

---

## ⚙️ Langkah-langkah Algoritma

1. **Inisialisasi**: Buat array kosong bernama `ingredients` untuk menyimpan hasil
2. **Loop**: Ulangi dari indeks 0 sampai panjang array `meats`:
   - Tambahkan elemen `meats[i]` ke dalam `ingredients`
   - Tambahkan elemen `vegetables[i]` ke dalam `ingredients`
3. **Return**: Kembalikan array `ingredients` yang sudah berisi gabungan kedua array

---

## 🎓 Tips untuk Pemula

### ✅ Kapan Menggunakan Fungsi Ini?

- Ketika Anda ingin menggabungkan dua list dengan pola berpasangan berselang-seling
- Saat membuat daftar alternatif dari dua sumber data dengan indeks yang sama
- Ketika menyusun data yang memiliki relasi 1:1 antara dua array
- Untuk membuat pola data zigzag dari dua array dengan ukuran sama

### ⚠️ Hal yang Perlu Diperhatikan

- Fungsi ini **tidak mengubah** array asli (`meats` dan `vegetables`)
- Fungsi membuat array **baru** sebagai hasil
- **PENTING**: Pastikan `vegetables.length >= meats.length` untuk menghindari `undefined`
- Loop berjalan sebanyak panjang array `meats`, bukan array terpanjang
- Jika `vegetables` lebih pendek dari `meats`, akan muncul nilai `undefined` di hasil

### 🚨 Masalah Potensial

**Masalah:** Mendapatkan `undefined` dalam hasil

```javascript
// ❌ SALAH - vegetables lebih pendek
const daging = ['Beef', 'Chicken', 'Pork'];
const sayuran = ['Bok Choy'];
prepareSukiyaki(daging, sayuran);
// Output: ['Beef', 'Bok Choy', 'Chicken', undefined, 'Pork', undefined]
```

**Solusi:** Pastikan vegetables memiliki panjang yang sama atau lebih

```javascript
// ✅ BENAR
const daging = ['Beef', 'Chicken', 'Pork'];
const sayuran = ['Bok Choy', 'Mushroom', 'Onion'];
prepareSukiyaki(daging, sayuran);
// Output: ['Beef', 'Bok Choy', 'Chicken', 'Mushroom', 'Pork', 'Onion']
```

---

## 🔧 Variasi dan Modifikasi

### Modifikasi 1: Versi Aman (Menghindari Undefined)

```javascript
function prepareSukiyakiSafe(meats, vegetables) {
  // Array untuk menyimpan bahan-bahan sukiyaki
  const ingredients = [];
  
  // Gunakan panjang terkecil untuk menghindari undefined
  const minLength = Math.min(meats.length, vegetables.length);
  
  for (let i = 0; i < minLength; i++) {
    ingredients.push(meats[i]);
    ingredients.push(vegetables[i]);
  }
  
  return ingredients;
}
```

### Modifikasi 2: Dengan Validasi Input

```javascript
function prepareSukiyakiWithValidation(meats, vegetables) {
  // Validasi: pastikan vegetables tidak lebih pendek dari meats
  if (vegetables.length < meats.length) {
    throw new Error('Array vegetables harus minimal sama panjang dengan meats!');
  }
  
  const ingredients = [];
  
  for (let i = 0; i < meats.length; i++) {
    ingredients.push(meats[i]);
    ingredients.push(vegetables[i]);
  }
  
  return ingredients;
}
```

### Modifikasi 3: Versi Fleksibel (Menggunakan Array Terpanjang)

```javascript
function prepareSukiyakiFlexible(meats, vegetables) {
  const ingredients = [];
  const maxLength = Math.max(meats.length, vegetables.length);
  
  for (let i = 0; i < maxLength; i++) {
    // Tambahkan daging jika masih ada
    if (i < meats.length) {
      ingredients.push(meats[i]);
    }
    
    // Tambahkan sayuran jika masih ada
    if (i < vegetables.length) {
      ingredients.push(vegetables[i]);
    }
  }
  
  return ingredients;
}
```

---

## 📊 Perbandingan dengan Versi Lain

| Aspek | Versi Original | Versi Aman | Versi Fleksibel |
|-------|----------------|------------|-----------------|
| Iterasi | `meats.length` | `Math.min()` | `Math.max()` |
| Risiko Undefined | ⚠️ Ya | ✅ Tidak | ✅ Tidak |
| Gunakan Semua Data | ❌ Tidak | ❌ Tidak | ✅ Ya |
| Kompleksitas | Sederhana | Sederhana | Sederhana |
| Rekomendasi | Gunakan jika yakin ukuran sama | Paling aman | Paling fleksibel |

---

## 📚 Referensi Metode JavaScript yang Digunakan

| Metode/Konsep | Penjelasan |
|---------------|------------|
| `array.length` | Properti yang mengembalikan jumlah elemen dalam array |
| `array.push()` | Menambahkan elemen baru ke akhir array |
| `for loop` | Struktur perulangan untuk mengiterasi sejumlah kali tertentu |
| `array[index]` | Mengakses elemen array pada indeks tertentu |
| `const` | Keyword untuk mendeklarasikan variabel yang tidak bisa diubah referensinya |

---

## 🎯 Kasus Penggunaan Real-World

### 1. Membuat Daftar Belanja Berpasangan
```javascript
const buah = ['🍎 Apel', '🍌 Pisang', '🍊 Jeruk'];
const jumlah = ['1 kg', '2 sisir', '500 gram'];

const daftarBelanja = prepareSukiyaki(buah, jumlah);
// ['🍎 Apel', '1 kg', '🍌 Pisang', '2 sisir', '🍊 Jeruk', '500 gram']
```

### 2. Membuat Dialog Chat
```javascript
const pengirim = ['Alice', 'Bob', 'Alice'];
const pesan = ['Halo!', 'Hi, apa kabar?', 'Baik, terima kasih!'];

const chat = prepareSukiyaki(pengirim, pesan);
// ['Alice', 'Halo!', 'Bob', 'Hi, apa kabar?', 'Alice', 'Baik, terima kasih!']
```

### 3. Membuat Pasangan Key-Value
```javascript
const keys = ['nama', 'umur', 'kota'];
const values = ['Budi', 25, 'Jakarta'];

const data = prepareSukiyaki(keys, values);
// ['nama', 'Budi', 'umur', 25, 'kota', 'Jakarta']
```

---

## 📞 Kesimpulan

Fungsi `prepareSukiyaki` adalah cara sederhana untuk menggabungkan dua array secara berselang-seling dengan pola berpasangan berdasarkan indeks. Fungsi ini sangat efektif ketika kedua array memiliki panjang yang sama atau array kedua lebih panjang.

**Kelebihan:**
- ✅ Kode sederhana dan mudah dipahami
- ✅ Efisien untuk data berpasangan
- ✅ Menjaga urutan elemen

**Kekurangan:**
- ⚠️ Rentan terhadap `undefined` jika `vegetables` lebih pendek dari `meats`
- ⚠️ Tidak menggunakan semua elemen jika array memiliki panjang berbeda

**Kompleksitas:**
- **Time Complexity:** O(n) - dimana n adalah panjang array `meats`
- **Space Complexity:** O(2n) - karena membuat array baru dengan ukuran 2x panjang array `meats`

---

## 💡 Rekomendasi

Untuk penggunaan yang lebih aman, pertimbangkan untuk:

1. **Tambahkan validasi** untuk memastikan `vegetables.length >= meats.length`
2. **Gunakan versi aman** dengan `Math.min()` jika tidak masalah kehilangan beberapa data
3. **Gunakan versi fleksibel** dengan `Math.max()` dan pengecekan kondisi jika ingin semua data diproses

---

💡 **Selamat Coding!** 🚀
