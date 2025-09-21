# 🦠 Fungsi microbeCounter

## 📖 Deskripsi

Fungsi `microbeCounter` adalah sebuah utility yang digunakan untuk menghitung jumlah kemunculan setiap jenis mikroba dalam sebuah sampel. Fungsi ini sangat berguna dalam analisis mikrobiologi untuk mendapatkan distribusi dan frekuensi berbagai jenis mikroorganisme.

## ⚙️ Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `sample` | Array | Array yang berisi nama-nama mikroba yang akan dihitung |

## 💻 Kode Fungsi

```javascript
function microbeCounter(sample) {
  // Membuat objek kosong untuk menyimpan hasil perhitungan
  const counts = {};
  
  // Melakukan iterasi pada setiap mikroba dalam sampel
  for (const microbe of sample) {
    // Menghitung jumlah setiap mikroba
    // Jika mikroba belum ada di objek counts, set ke 0, lalu tambah 1
    counts[microbe] = (counts[microbe] || 0) + 1;
  }
  
  // Mengembalikan objek yang berisi hasil perhitungan
  return counts;
}
```

## 📊 Cara Kerja

1. **Inisialisasi**: Fungsi membuat objek kosong `counts` untuk menyimpan hasil perhitungan
2. **Iterasi**: Menggunakan loop `for...of` untuk mengakses setiap elemen dalam array `sample`
3. **Perhitungan**: Untuk setiap mikroba, fungsi akan:
   - Mengecek apakah mikroba sudah ada dalam objek `counts`
   - Jika belum ada, inisialisasi dengan nilai 0
   - Menambah 1 pada nilai yang sudah ada
4. **Return**: Mengembalikan objek yang berisi pasangan key-value (nama mikroba - jumlah kemunculan)

## 🧪 Contoh Penggunaan

### Input:
```javascript
const sampleData = [
  'E.coli', 
  'Salmonella', 
  'E.coli', 
  'Lactobacillus', 
  'E.coli', 
  'Salmonella'
];

const result = microbeCounter(sampleData);
console.log(result);
```

### Output:
```javascript
{
  'E.coli': 3,
  'Salmonella': 2,
  'Lactobacillus': 1
}
```

## 📋 Contoh Lainnya

### Sampel dengan berbagai jenis mikroba:
```javascript
const mixedSample = [
  'Streptococcus',
  'Staphylococcus',
  'Candida',
  'Streptococcus',
  'Candida',
  'Candida',
  'Bacillus'
];

console.log(microbeCounter(mixedSample));
// Output: 
// {
//   'Streptococcus': 2,
//   'Staphylococcus': 1,
//   'Candida': 3,
//   'Bacillus': 1
// }
```

### Sampel kosong:
```javascript
console.log(microbeCounter([]));
// Output: {}
```

## 🔍 Kegunaan

Fungsi ini dapat dimanfaatkan untuk:
- **Analisis mikrobiologi**: Menghitung distribusi mikroorganisme dalam sampel
- **Quality control**: Memantau kontaminasi dalam produk makanan atau farmasi
- **Penelitian**: Menganalisis diversitas mikroba dalam lingkungan tertentu
- **Data processing**: Menghitung frekuensi kemunculan item dalam array secara umum

## ⚠️ Catatan Penting

- Fungsi ini case-sensitive, jadi `'E.coli'` dan `'e.coli'` akan dianggap sebagai mikroba yang berbeda
- Pastikan input berupa array, jika tidak fungsi akan menghasilkan error
- Fungsi ini tidak melakukan validasi input, pastikan data yang dimasukkan sudah benar

## 🚀 Tips Penggunaan

1. **Normalisasi data**: Pertimbangkan untuk mengubah semua nama mikroba ke lowercase sebelum memproses jika diperlukan
2. **Validasi input**: Tambahkan pengecekan untuk memastikan `sample` adalah array yang valid
3. **Sorting hasil**: Anda bisa mengurutkan hasil berdasarkan nama mikroba atau jumlah kemunculan sesuai kebutuhan
