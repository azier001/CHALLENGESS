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
    // Mengembalikan string dengan format "Lift order: " diikuti urutan potongan
    return "Lift order: " + pieces
        
        // Mengurutkan array berdasarkan berat (angka setelah tanda '-')
        .sort((a, b) => {
            // Memisahkan string berdasarkan '-' dan mengambil bagian kedua (berat)
            const beratA = parseInt(a.split('-')[1]);
            const beratB = parseInt(b.split('-')[1]);
            
            // Mengurutkan dari yang paling ringan ke paling berat
            return beratA - beratB;
        })
        
        // Mengubah setiap elemen menjadi format "nomor. nama"
        .map((piece, index) => {
            const namaPiece = piece.split('-')[0]; // Mengambil nama piece
            const nomorUrut = index + 1; // Membuat nomor urut mulai dari 1
            
            return `${nomorUrut}. ${namaPiece}`;
        })
        
        // Menggabungkan semua elemen dengan koma dan spasi
        .join(', ');
}
```

## 🔍 Cara Kerja Fungsi

1. **Parsing Input**: Fungsi menerima array string dengan format `"nama-berat"`
2. **Sorting**: Mengurutkan berdasarkan berat (angka setelah tanda `-`) dari ringan ke berat
3. **Mapping**: Mengubah format menjadi numbered list dengan nama piece saja
4. **Formatting**: Menggabungkan hasil dengan format yang mudah dibaca

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

## 📈 Tabel Contoh Input/Output

| Input | Berat (kg) | Urutan | Output |
|-------|------------|---------|---------|
| aluminum-20 | 20 | 1 | 1. aluminum |
| copper-35 | 35 | 2 | 2. copper |
| steel-45 | 45 | 3 | 3. steel |

## ⚠️ Catatan Penting

- **Format Input**: Pastikan setiap string menggunakan format `"nama-angka"`
- **Tipe Data**: Bagian berat harus berupa angka yang valid
- **Separator**: Gunakan tanda `-` sebagai pemisah antara nama dan berat
- **Case Sensitive**: Nama material akan ditampilkan persis seperti input

## 🎯 Use Case Praktis

Fungsi ini sangat berguna untuk:
- **Perencanaan Crane**: Menentukan urutan optimal pengangkatan material
- **Optimasi Workflow**: Mengatur urutan kerja berdasarkan beban
- **Safety Planning**: Memulai dari material paling ringan untuk keamanan
- **Inventory Management**: Mengatur prioritas handling material

## 🔧 Tips Penggunaan

1. **Validasi Input**: Selalu pastikan format input sesuai sebelum memanggil fungsi
2. **Konsistensi Unit**: Gunakan satuan berat yang sama untuk semua item
3. **Penamaan**: Gunakan nama yang deskriptif untuk memudahkan identifikasi

## 📚 Referensi Method JavaScript

Fungsi ini menggunakan beberapa method JavaScript built-in:
- `Array.sort()`: Untuk mengurutkan array
- `String.split()`: Untuk memisahkan string
- `parseInt()`: Untuk mengkonversi string ke integer
- `Array.map()`: Untuk transformasi data
- `Array.join()`: Untuk menggabungkan array menjadi string
