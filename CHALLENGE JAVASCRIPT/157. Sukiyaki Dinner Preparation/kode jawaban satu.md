# 🍲 Dokumentasi Fungsi `prepareSukiyaki`

## 📋 Deskripsi

Fungsi `prepareSukiyaki` adalah fungsi JavaScript yang digunakan untuk menggabungkan dua array (daging dan sayuran) secara berselang-seling (alternating). Fungsi ini akan mengambil elemen dari array `meats` dan `vegetables` secara bergantian, layaknya menyusun bahan-bahan sukiyaki di dalam panci.

Fungsi ini sangat berguna ketika Anda ingin mencampur dua jenis data dengan pola yang berselang-seling, seperti:
- Menyusun bahan masakan
- Menggabungkan dua daftar dengan pola bergantian
- Membuat urutan data yang diselingi dari dua sumber berbeda

---

## 🎯 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `meats` | `Array` | Array yang berisi daftar daging (atau elemen pertama yang ingin digabungkan) |
| `vegetables` | `Array` | Array yang berisi daftar sayuran (atau elemen kedua yang ingin digabungkan) |

### 💡 Catatan Penting:
- Kedua parameter bisa memiliki panjang yang berbeda
- Fungsi akan tetap berjalan sampai semua elemen dari array terpanjang diproses
- Jika salah satu array lebih pendek, elemen dari array yang lebih panjang akan tetap ditambahkan

---

## 🔄 Return Value

**Tipe:** `Array`

Mengembalikan array baru yang berisi elemen dari kedua array input secara berselang-seling.

---

## 📝 Source Code

```javascript
function prepareSukiyaki(meats, vegetables) {
  // Array untuk menyimpan hasil gabungan
  const result = [];
  
  // Mencari panjang maksimal dari kedua array
  const maxLength = Math.max(meats.length, vegetables.length);
  
  // Loop sebanyak panjang array terpanjang
  for (let i = 0; i < maxLength; i++) {
    // Tambahkan daging jika indeks masih dalam jangkauan array meats
    if (i < meats.length) {
      result.push(meats[i]);
    }
    
    // Tambahkan sayuran jika indeks masih dalam jangkauan array vegetables
    if (i < vegetables.length) {
      result.push(vegetables[i]);
    }
  }
  
  // Kembalikan array hasil gabungan
  return result;
}
```

---

## 🎬 Contoh Penggunaan

### Contoh 1: Array dengan Panjang Sama

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

### Contoh 2: Array Daging Lebih Panjang

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
  '🦐 Shrimp'
]
```

---

### Contoh 3: Array Sayuran Lebih Panjang

```javascript
const daging = ['🥩 Beef'];
const sayuran = ['🥬 Bok Choy', '🍄 Mushroom', '🧅 Onion', '🥕 Carrot'];

const sukiyaki = prepareSukiyaki(daging, sayuran);
console.log(sukiyaki);
```

**Output:**
```javascript
[
  '🥩 Beef',
  '🥬 Bok Choy',
  '🍄 Mushroom',
  '🧅 Onion',
  '🥕 Carrot'
]
```

---

### Contoh 4: Salah Satu Array Kosong

```javascript
const daging = ['🥩 Beef', '🐔 Chicken'];
const sayuran = [];

const sukiyaki = prepareSukiyaki(daging, sayuran);
console.log(sukiyaki);
```

**Output:**
```javascript
[
  '🥩 Beef',
  '🐔 Chicken'
]
```

---

## 🧮 Cara Kerja Fungsi

### Visualisasi Proses

Mari kita lihat bagaimana fungsi bekerja dengan contoh sederhana:

**Input:**
```
meats      = ['Beef', 'Chicken', 'Pork']
vegetables = ['Bok Choy', 'Mushroom']
```

**Proses:**

| Iterasi | Index (i) | Dari meats | Dari vegetables | Result |
|---------|-----------|------------|-----------------|--------|
| 1 | 0 | 'Beef' | 'Bok Choy' | `['Beef', 'Bok Choy']` |
| 2 | 1 | 'Chicken' | 'Mushroom' | `['Beef', 'Bok Choy', 'Chicken', 'Mushroom']` |
| 3 | 2 | 'Pork' | ❌ (index > length) | `['Beef', 'Bok Choy', 'Chicken', 'Mushroom', 'Pork']` |

**Output Final:**
```
['Beef', 'Bok Choy', 'Chicken', 'Mushroom', 'Pork']
```

---

## ⚙️ Langkah-langkah Algoritma

1. **Inisialisasi**: Buat array kosong bernama `result` untuk menyimpan hasil
2. **Tentukan Panjang Maksimal**: Hitung panjang terpanjang antara `meats` dan `vegetables`
3. **Loop**: Ulangi sebanyak panjang maksimal:
   - Jika masih ada elemen di `meats` pada indeks ke-i, tambahkan ke `result`
   - Jika masih ada elemen di `vegetables` pada indeks ke-i, tambahkan ke `result`
4. **Return**: Kembalikan array `result` yang sudah berisi gabungan kedua array

---

## 🎓 Tips untuk Pemula

### ✅ Kapan Menggunakan Fungsi Ini?

- Ketika Anda ingin menggabungkan dua list dengan pola berselang-seling
- Saat membuat playlist yang diselingi antara dua genre musik
- Ketika menyusun jadwal yang bergantian antara dua aktivitas
- Untuk membuat pola data yang teratur dari dua sumber

### ⚠️ Hal yang Perlu Diperhatikan

- Fungsi ini **tidak mengubah** array asli (`meats` dan `vegetables`)
- Fungsi membuat array **baru** sebagai hasil
- Urutan elemen tetap dipertahankan dari array asli
- Fungsi bisa menerima array dengan tipe data apapun (string, number, object, dll)

---

## 🔧 Variasi dan Modifikasi

### Modifikasi 1: Menambahkan Separator

```javascript
function prepareSukiyakiWithSeparator(meats, vegetables, separator = '---') {
  const result = [];
  const maxLength = Math.max(meats.length, vegetables.length);
  
  for (let i = 0; i < maxLength; i++) {
    if (i < meats.length) {
      result.push(meats[i]);
    }
    result.push(separator);
    if (i < vegetables.length) {
      result.push(vegetables[i]);
    }
  }
  
  return result;
}
```

### Modifikasi 2: Menggabungkan Lebih dari 2 Array

```javascript
function prepareSukiyakiMultiple(...arrays) {
  const result = [];
  const maxLength = Math.max(...arrays.map(arr => arr.length));
  
  for (let i = 0; i < maxLength; i++) {
    for (let arr of arrays) {
      if (i < arr.length) {
        result.push(arr[i]);
      }
    }
  }
  
  return result;
}
```

---

## 📚 Referensi Metode JavaScript yang Digunakan

| Metode/Konsep | Penjelasan |
|---------------|------------|
| `Math.max()` | Mengembalikan nilai terbesar dari angka-angka yang diberikan |
| `array.length` | Properti yang mengembalikan jumlah elemen dalam array |
| `array.push()` | Menambahkan elemen baru ke akhir array |
| `for loop` | Struktur perulangan untuk mengiterasi sejumlah kali tertentu |
| `if statement` | Kondisi untuk mengecek apakah suatu syarat terpenuhi |

---

## 📞 Kesimpulan

Fungsi `prepareSukiyaki` adalah cara yang elegant dan efisien untuk menggabungkan dua array secara berselang-seling. Fungsi ini sangat fleksibel karena dapat menangani array dengan panjang berbeda dan tetap menjaga urutan elemen dari array asli.

**Kompleksitas:**
- **Time Complexity:** O(n) - dimana n adalah panjang array terpanjang
- **Space Complexity:** O(n) - karena membuat array baru untuk hasil

---

💡 **Selamat Coding!** 🚀
