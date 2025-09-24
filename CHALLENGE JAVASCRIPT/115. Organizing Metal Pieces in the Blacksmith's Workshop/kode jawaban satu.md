# 🔧 Dokumentasi Fungsi `sortMetalPieces`

## 📝 Deskripsi

Fungsi `sortMetalPieces` adalah fungsi JavaScript yang digunakan untuk mengurutkan potongan-potongan logam berdasarkan beratnya dan mengembalikan urutan pengangkatan yang telah diformat. Fungsi ini sangat berguna dalam aplikasi industri atau manufaktur untuk menentukan urutan optimal dalam mengangkat berbagai komponen logam.

## 🎯 Tujuan Fungsi

- Mengurutkan potongan logam dari yang paling ringan ke paling berat
- Memberikan format output yang mudah dibaca untuk urutan pengangkatan
- Menyederhanakan proses perencanaan pengangkatan material

## 📋 Sintaks

```javascript
function sortMetalPieces(pieces)
```

## ⚙️ Parameter

| Parameter | Tipe | Wajib | Deskripsi |
|-----------|------|-------|-----------|
| `pieces` | Array | Ya | Array berisi string dengan format `"nama-berat"` dimana nama adalah nama potongan logam dan berat adalah angka dalam kilogram |

### Format Input yang Diharapkan:
- Setiap elemen array harus berformat: `"namaPiece-beratDalamKg"`
- Contoh: `["steel-50", "aluminum-25", "iron-75"]`

## 💻 Kode Lengkap

```javascript
function sortMetalPieces(pieces) {
  // Parsing berat dan membuat array objek untuk memudahkan manipulasi data
  const parsedPieces = pieces.map(piece => {
    // Memisahkan string berdasarkan '-' untuk mendapatkan nama dan berat
    const [name, weight] = piece.split('-');
    
    // Mengembalikan objek dengan nama dan berat yang sudah dikonversi ke integer
    return { 
      name, 
      weight: parseInt(weight) 
    };
  });

  // Mengurutkan potongan berdasarkan berat dari yang paling ringan ke paling berat
  parsedPieces.sort((a, b) => a.weight - b.weight);

  // Membuat string yang diformat dengan nomor urut dan nama potongan
  const liftOrder = parsedPieces.map((piece, index) => 
    `${index + 1}. ${piece.name}`
  ).join(', ');

  // Mengembalikan hasil dengan format "Lift order: ..."
  return `Lift order: ${liftOrder}`;
}
```

## 🔍 Cara Kerja Fungsi

1. **Parsing Input**: Mengubah setiap string menjadi objek dengan properti `name` dan `weight`
2. **Konversi Data**: Mengkonversi berat dari string menjadi integer untuk sorting yang akurat
3. **Sorting**: Mengurutkan array objek berdasarkan properti `weight` secara ascending
4. **Mapping**: Mengubah objek menjadi string dengan format nomor dan nama
5. **Formatting**: Menggabungkan hasil dengan format yang mudah dibaca

## 📊 Contoh Penggunaan

### Contoh 1: Potongan Logam Ringan
```javascript
const metalPieces = ["steel-45", "aluminum-20", "copper-35"];
const result = sortMetalPieces(metalPieces);
console.log(result);
```

**Output:**
```
Lift order: 1. aluminum, 2. copper, 3. steel
```

### Contoh 2: Berbagai Jenis Material
```javascript
const industrialParts = ["iron-80", "titanium-15", "brass-60", "zinc-25"];
const liftOrder = sortMetalPieces(industrialParts);
console.log(liftOrder);
```

**Output:**
```
Lift order: 1. titanium, 2. zinc, 3. brass, 4. iron
```

### Contoh 3: Material Berat
```javascript
const heavyMetals = ["lead-200", "gold-150", "platinum-180"];
const sequence = sortMetalPieces(heavyMetals);
console.log(sequence);
```

**Output:**
```
Lift order: 1. gold, 2. platinum, 3. lead
```

### Contoh 4: Campuran Material Industri
```javascript
const mixedMaterials = ["bronze-90", "silver-105", "nickel-70", "tin-30"];
const order = sortMetalPieces(mixedMaterials);
console.log(order);
```

**Output:**
```
Lift order: 1. tin, 2. nickel, 3. bronze, 4. silver
```

## 📈 Tabel Contoh Proses Parsing

| Input String | Nama | Berat (kg) | Objek Hasil |
|--------------|------|------------|-------------|
| "aluminum-20" | aluminum | 20 | `{name: "aluminum", weight: 20}` |
| "copper-35" | copper | 35 | `{name: "copper", weight: 35}` |
| "steel-45" | steel | 45 | `{name: "steel", weight: 45}` |

## 🏗️ Struktur Data Internal

Fungsi ini menggunakan pendekatan Object-Oriented untuk memudahkan manipulasi data:

```javascript
// Contoh struktur data setelah parsing
[
  { name: "aluminum", weight: 20 },
  { name: "copper", weight: 35 },
  { name: "steel", weight: 45 }
]
```

## ⚠️ Catatan Penting

- **Format Input**: Pastikan setiap string menggunakan format `"nama-angka"`
- **Tipe Data**: Bagian berat harus berupa angka yang valid untuk `parseInt()`
- **Separator**: Gunakan tanda `-` sebagai pemisah antara nama dan berat
- **Case Sensitive**: Nama material akan ditampilkan persis seperti input
- **Validasi**: Pastikan tidak ada nilai `NaN` hasil dari `parseInt()`

## 🎯 Use Case Praktis

Fungsi ini sangat berguna untuk:
- **Perencanaan Crane**: Menentukan urutan optimal pengangkatan material
- **Optimasi Workflow**: Mengatur urutan kerja berdasarkan beban
- **Safety Planning**: Memulai dari material paling ringan untuk keamanan
- **Inventory Management**: Mengatur prioritas handling material
- **Logistics Planning**: Perencanaan pengiriman berdasarkan berat

## 🔧 Keunggulan Pendekatan Ini

1. **Readability**: Kode lebih mudah dibaca dengan menggunakan objek
2. **Maintainability**: Struktur data yang jelas memudahkan maintenance
3. **Debugging**: Lebih mudah untuk debug karena data terstruktur
4. **Scalability**: Mudah untuk menambahkan properti lain (ukuran, material, dll)

## 💡 Tips Penggunaan

1. **Validasi Input**: Selalu pastikan format input sesuai sebelum memanggil fungsi
2. **Konsistensi Unit**: Gunakan satuan berat yang sama untuk semua item
3. **Penamaan**: Gunakan nama yang deskriptif untuk memudahkan identifikasi
4. **Error Handling**: Pertimbangkan untuk menambahkan validasi tambahan

## 🚀 Pengembangan Lebih Lanjut

Fungsi ini dapat diperluas dengan fitur:
- Validasi input yang lebih robust
- Support untuk multiple separator
- Sorting berdasarkan kriteria lain (nama, ukuran, dll)
- Format output yang dapat dikustomisasi

## 📚 Referensi Method JavaScript

Fungsi ini menggunakan beberapa method JavaScript built-in:
- `Array.map()`: Untuk transformasi data dan parsing
- `String.split()`: Untuk memisahkan string
- `parseInt()`: Untuk mengkonversi string ke integer
- `Array.sort()`: Untuk mengurutkan array objek
- `Array.join()`: Untuk menggabungkan array menjadi string
- **Destructuring Assignment**: `const [name, weight] = piece.split('-')`
