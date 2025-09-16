# 📚 Dokumentasi Fungsi `sortMonasteryBooks`

## 🎯 Deskripsi

Fungsi `sortMonasteryBooks` adalah sebuah utilitas untuk mengurutkan sebagian koleksi buku dalam perpustakaan biara secara alfabetis. Fungsi ini memungkinkan Anda untuk mengurutkan hanya bagian tertentu dari array buku tanpa mengubah posisi buku-buku di luar rentang yang dipilih.

## ✨ Fitur Utama

- ✅ Mengurutkan hanya bagian tertentu dari array
- ✅ Tidak mengubah array asli (immutable)
- ✅ Pengurutan alfabetis otomatis
- ✅ Fleksibel dalam menentukan rentang sorting

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
    // Membuat salinan dari array asli untuk menghindari modifikasi langsung
    const result = [...books];
    
    // Mengekstrak bagian yang akan diurutkan
    const sectionToSort = result.slice(startIndex, endIndex + 1);
    
    // Mengurutkan bagian tersebut secara alfabetis
    sectionToSort.sort();
    
    // Mengganti bagian asli dengan bagian yang sudah diurutkan
    for (let i = 0; i < sectionToSort.length; i++) {
        result[startIndex + i] = sectionToSort[i];
    }
    
    return result;
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
    "Kitab Suci",           // Tidak berubah (di luar rentang)
    "Alkitab Terjemahan Baru", // Diurutkan
    "Buku Kidung",          // Diurutkan  
    "Doa Harian",           // Diurutkan
    "Ajaran Moral"          // Tidak berubah (di luar rentang)
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

## ⚠️ Catatan Penting

1. **Indeks dimulai dari 0**: Elemen pertama array memiliki indeks 0
2. **endIndex bersifat inklusif**: Elemen pada posisi endIndex ikut diurutkan
3. **Array asli tidak berubah**: Fungsi mengembalikan array baru
4. **Pengurutan case-sensitive**: Huruf besar akan muncul sebelum huruf kecil

## 🚨 Peringatan

- Pastikan `startIndex` ≤ `endIndex`
- Pastikan indeks tidak melebihi panjang array
- Array kosong atau parameter yang tidak valid dapat menyebabkan error

## 🎯 Use Case Ideal

Fungsi ini cocok digunakan untuk:
- Mengorganisir koleksi buku berdasarkan kategori tertentu
- Mengurutkan bagian spesifik dari daftar tanpa mengacak urutan keseluruhan  
- Sistem manajemen perpustakaan dengan kategori khusus
- Aplikasi yang membutuhkan partial sorting
