# 📚 Dokumentasi Fungsi `organizeLibrary` (Versi ES6)

## 📝 Deskripsi

Fungsi `organizeLibrary` adalah sebuah fungsi JavaScript modern yang menggunakan ES6+ features untuk mengorganisir dan memformat koleksi buku sains dan filsafat. Fungsi ini menggabungkan kedua jenis buku tersebut ke dalam satu array dengan format judul yang konsisten (huruf pertama kapital, sisanya huruf kecil) menggunakan pendekatan functional programming.

## ⚙️ Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `scienceBooks` | Array | Array yang berisi judul-judul buku sains dalam bentuk string |
| `philosophyBooks` | Array | Array yang berisi judul-judul buku filsafat dalam bentuk string |

## 🔄 Return Value

**Tipe:** `Array`

**Deskripsi:** Mengembalikan array baru yang berisi semua judul buku (sains dan filsafat) dengan format yang telah distandarisasi.

## 💻 Kode Fungsi

```javascript
function organizeLibrary(scienceBooks, philosophyBooks) {
  // Fungsi helper untuk memformat judul buku
  const formatTitle = (title) => {
    return title.charAt(0).toUpperCase() + title.slice(1).toLowerCase();
  };
  
  // Memformat semua judul buku sains menggunakan map()
  const formattedScience = scienceBooks.map(formatTitle);
  
  // Memformat semua judul buku filsafat menggunakan map()
  const formattedPhilosophy = philosophyBooks.map(formatTitle);
  
  // Menggabungkan kedua array menggunakan spread operator
  return [...formattedScience, ...formattedPhilosophy];
}
```

## 🚀 Cara Kerja

1. **Definisi Helper Function**: 
   - Membuat fungsi `formatTitle` untuk memformat setiap judul
   - Menggunakan `charAt(0).toUpperCase()` untuk huruf pertama kapital
   - Menggunakan `slice(1).toLowerCase()` untuk sisa huruf menjadi kecil

2. **Pemrosesan dengan Map**: 
   - Menggunakan method `map()` untuk mentransformasi setiap elemen array
   - `formattedScience` berisi buku sains yang sudah diformat
   - `formattedPhilosophy` berisi buku filsafat yang sudah diformat

3. **Penggabungan Array**: 
   - Menggunakan spread operator (`...`) untuk menggabungkan kedua array
   - Urutan: buku sains terlebih dahulu, kemudian buku filsafat

4. **Return**: Mengembalikan array gabungan yang sudah diformat

## 🎨 Fitur ES6+ yang Digunakan

| Fitur | Deskripsi | Keuntungan |
|-------|-----------|------------|
| **Arrow Functions** | `(title) => { ... }` | Sintaks lebih ringkas dan clean |
| **Array.map()** | Transformasi array secara functional | Lebih readable dan immutable |
| **Spread Operator** | `[...array1, ...array2]` | Penggabungan array yang elegant |
| **Const Declaration** | `const formatTitle = ...` | Mencegah reassignment yang tidak diinginkan |

## 📋 Contoh Penggunaan

```javascript
// Contoh data input
const bukuSains = ["FISIKA KUANTUM", "biologi molekuler", "KiMiA oRgAnIk"];
const bukuFilsafat = ["ETIKA ARISTOTELES", "logika simbolik", "FiLsAfAt MoDeRn"];

// Memanggil fungsi
const perpustakaanTerorganisir = organizeLibrary(bukuSains, bukuFilsafat);

console.log(perpustakaanTerorganisir);
```

## 📤 Contoh Output

```javascript
[
    "Fisika kuantum",
    "Biologi molekuler", 
    "Kimia organik",
    "Etika aristoteles",
    "Logika simbolik",
    "Filsafat modern"
]
```

## 🎯 Keunggulan Versi Ini

- **Functional Programming**: Menggunakan paradigma functional yang lebih modern
- **Reusability**: Fungsi `formatTitle` bisa digunakan kembali untuk keperluan lain
- **Immutability**: Tidak mengubah array original, selalu membuat array baru
- **Readability**: Kode lebih mudah dibaca dan dipahami
- **Performance**: Method `map()` umumnya lebih efisien dibanding loop manual
- **Maintainability**: Struktur kode yang lebih modular dan mudah di-maintain

## 🔄 Perbandingan dengan Versi Loop Tradisional

| Aspek | Versi ES6 (Ini) | Versi Loop Tradisional |
|-------|-----------------|------------------------|
| **Panjang Kode** | Lebih ringkas | Lebih panjang |
| **Readability** | Sangat mudah dibaca | Butuh fokus lebih |
| **Functional Style** | ✅ Ya | ❌ Tidak |
| **Reusability** | ✅ Helper function | ❌ Logic tersebar |
| **Modern JavaScript** | ✅ ES6+ | ❌ ES5 |

## ⚠️ Catatan Penting

- Fungsi ini sepenuhnya immutable (tidak mengubah array input)
- Menggunakan functional programming approach yang lebih modern
- Helper function `formatTitle` bisa di-extract menjadi utility function terpisah
- Kompatibel dengan browser modern yang mendukung ES6+
- Lebih mudah untuk di-test dan di-debug karena struktur yang modular

## 🛠️ Tips Pengembangan Lebih Lanjut

```javascript
// Bisa dijadikan lebih fleksibel dengan parameter tambahan
function organizeLibrary(scienceBooks, philosophyBooks, customFormatter = null) {
  const formatTitle = customFormatter || ((title) => {
    return title.charAt(0).toUpperCase() + title.slice(1).toLowerCase();
  });
  
  return [
    ...scienceBooks.map(formatTitle),
    ...philosophyBooks.map(formatTitle)
  ];
}
```
