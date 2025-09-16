# 📚 Dokumentasi Fungsi `sortMonasteryBooks`

## 🎯 Deskripsi

Fungsi `sortMonasteryBooks` adalah sebuah utilitas untuk mengurutkan sebagian koleksi buku dalam perpustakaan biara secara alfabetis. Fungsi ini memungkinkan Anda untuk mengurutkan hanya bagian tertentu dari array buku tanpa mengubah posisi buku-buku di luar rentang yang dipilih.

## ✨ Fitur Utama

- ✅ Mengurutkan hanya bagian tertentu dari array
- ✅ Tidak mengubah array asli (immutable)
- ✅ Pengurutan alfabetis otomatis
- ✅ Fleksibel dalam menentukan rentang sorting
- ✅ Implementasi yang lebih concise dan modern

## 📋 Parameter

| Parameter | Tipe | Deskripsi | Wajib |
|-----------|------|-----------|-------|
| `books` | Array | Array berisi daftar judul buku yang akan diurutkan | ✅ |
| `startIndex` | Number | Indeks awal dari bagian yang akan diurutkan (inklusif) | ✅ |
| `endIndex` | Number | Indeks akhir dari bagian yang akan diurutkan (inklusif) | ✅ |

### 🔍 Detail Parameter

- **books**: Array string yang berisi judul-judul buku
- **startIndex**: Posisi mulai pengurutan (dimulai dari 0)
- **endIndex**: Posisi akhir pengurutan (termasuk dalam pengurutan)

## 📤 Return Value

Mengembalikan array baru dengan bagian yang dipilih telah diurutkan secara alfabetis, sedangkan bagian lainnya tetap pada posisi semula.

## 💻 Kode Fungsi

```javascript
function sortMonasteryBooks(books, startIndex, endIndex) {
  // Mengambil bagian yang akan diurutkan dan langsung mengurutkannya secara alfabetis
  const sortedSection = books.slice(startIndex, endIndex + 1).sort();
  
  // Mengembalikan array baru dengan menggabungkan:
  // - Bagian sebelum rentang pengurutan
  // - Bagian yang sudah diurutkan
  // - Bagian setelah rentang pengurutan
  return [
    ...books.slice(0, startIndex),           // Bagian awal (tidak diurutkan)
    ...sortedSection,                        // Bagian tengah (sudah diurutkan)
    ...books.slice(endIndex + 1)             // Bagian akhir (tidak diurutkan)
  ];
}
```

## 🔧 Cara Penggunaan

```javascript
// Contoh penggunaan dasar
const bukuBiara = [
    "Kitab Suci",
    "Doa Harian", 
    "Alkitab Terjemahan Baru",
    "Buku Kidung",
    "Ajaran Moral"
];

const hasilUrutan = sortMonasteryBooks(bukuBiara, 1, 3);
console.log(hasilUrutan);
```

## 📊 Contoh Output

### Input
```javascript
const books = [
    "Kitab Suci",
    "Doa Harian", 
    "Alkitab Terjemahan Baru",
    "Buku Kidung",
    "Ajaran Moral"
];

sortMonasteryBooks(books, 1, 3);
```

### Output
```javascript
[
    "Kitab Suci",              // Tidak berubah (di luar rentang)
    "Alkitab Terjemahan Baru", // Diurutkan
    "Buku Kidung",             // Diurutkan  
    "Doa Harian",              // Diurutkan
    "Ajaran Moral"             // Tidak berubah (di luar rentang)
]
```

## 📈 Contoh Penggunaan Lanjutan

### Contoh 1: Mengurutkan Seluruh Array
```javascript
const allBooks = ["Zebra", "Alpha", "Beta", "Charlie"];
const sortedAll = sortMonasteryBooks(allBooks, 0, allBooks.length - 1);
// Output: ["Alpha", "Beta", "Charlie", "Zebra"]
```

### Contoh 2: Mengurutkan Bagian Tengah
```javascript
const middleBooks = ["First", "Delta", "Alpha", "Charlie", "Last"];
const sortedMiddle = sortMonasteryBooks(middleBooks, 1, 3);
// Output: ["First", "Alpha", "Charlie", "Delta", "Last"]
```

### Contoh 3: Mengurutkan Hanya 2 Element
```javascript
const twoBooks = ["Kitab A", "Zebra", "Alpha", "Kitab Z"];
const sortedTwo = sortMonasteryBooks(twoBooks, 1, 2);
// Output: ["Kitab A", "Alpha", "Zebra", "Kitab Z"]
```

### Contoh 4: Mengurutkan Bagian Awal
```javascript
const startBooks = ["Zulu", "Alpha", "Charlie", "Keep", "This", "Order"];
const sortedStart = sortMonasteryBooks(startBooks, 0, 2);
// Output: ["Alpha", "Charlie", "Zulu", "Keep", "This", "Order"]
```

## 🔍 Analisis Kode

### 🚀 Keunggulan Implementasi

1. **Lebih Concise**: Menggunakan spread operator untuk menggabungkan array
2. **Functional Programming**: Tidak menggunakan loop manual
3. **Method Chaining**: Langsung mengurutkan hasil slice()
4. **Readable**: Kode lebih mudah dibaca dan dipahami

### ⚙️ Cara Kerja

```javascript
// Langkah 1: Ambil dan urutkan bagian yang dipilih
const sortedSection = books.slice(startIndex, endIndex + 1).sort();

// Langkah 2: Gabungkan 3 bagian array
return [
  ...books.slice(0, startIndex),     // Bagian awal
  ...sortedSection,                  // Bagian yang diurutkan
  ...books.slice(endIndex + 1)       // Bagian akhir
];
```

## ⚠️ Catatan Penting

1. **Indeks dimulai dari 0**: Elemen pertama array memiliki indeks 0
2. **endIndex bersifat inklusif**: Elemen pada posisi endIndex ikut diurutkan
3. **Array asli tidak berubah**: Fungsi mengembalikan array baru
4. **Pengurutan case-sensitive**: Huruf besar akan muncul sebelum huruf kecil
5. **Immutable**: Menggunakan spread operator untuk menjaga immutability

## 🚨 Peringatan

- Pastikan `startIndex` ≤ `endIndex`
- Pastikan indeks tidak melebihi panjang array
- Array kosong atau parameter yang tidak valid dapat menyebabkan error
- Parameter harus berupa angka non-negatif

## 🎯 Use Case Ideal

Fungsi ini cocok digunakan untuk:
- 📖 Mengorganisir koleksi buku berdasarkan kategori tertentu
- 📝 Mengurutkan bagian spesifik dari daftar tanpa mengacak urutan keseluruhan  
- 🏛️ Sistem manajemen perpustakaan dengan kategori khusus
- 💻 Aplikasi yang membutuhkan partial sorting
- 📚 Katalog digital perpustakaan biara
- 🗂️ Sistem filing dokumen dengan prioritas tertentu

## 🎨 Kelebihan Versi Ini

- **Modern ES6+ Syntax**: Menggunakan spread operator dan method chaining
- **Performa Lebih Baik**: Menghindari loop manual
- **Kode Lebih Bersih**: Lebih sedikit variabel dan lebih readable
- **Functional Style**: Mengikuti paradigma functional programming
