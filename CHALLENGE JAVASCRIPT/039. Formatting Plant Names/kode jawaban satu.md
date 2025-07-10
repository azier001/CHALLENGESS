# 🌱 Dokumentasi Fungsi `formatPlantName`

## 📝 Deskripsi Fungsi

Fungsi `formatPlantName` digunakan untuk memformat nama tanaman agar setiap kata dimulai dengan huruf kapital (Title Case). Fungsi ini ditulis dalam bentuk one-liner yang sangat efisien dan elegan, cocok untuk menyeragamkan penulisan nama tanaman dalam aplikasi atau database.

## 🎯 Tujuan Penggunaan

- Menyeragamkan format penulisan nama tanaman
- Membuat tampilan nama tanaman lebih profesional
- Menghindari inkonsistensi dalam penulisan nama
- Menggunakan pendekatan functional programming yang bersih

## 📋 Parameter

| Parameter | Tipe | Deskripsi | Contoh |
|-----------|------|-----------|--------|
| `plantName` | String | Nama tanaman yang ingin diformat | `"mawar merah"` |

## 🔧 Cara Kerja

1. **Pemisahan Kata**: `split(' ')` memisahkan string menjadi array berdasarkan spasi
2. **Transformasi**: `map()` mengubah setiap kata dengan format Title Case
3. **Penggabungan**: `join(' ')` menggabungkan kembali array menjadi string

## 💻 Kode Fungsi

### Versi Compact (One-liner)
```javascript
function formatPlantName(plantName) {
  return plantName.split(' ').map(word => word.charAt(0).toUpperCase() + word.slice(1).toLowerCase()).join(' ');
}
```

### Versi dengan Spacing untuk Readability
```javascript
function formatPlantName(plantName) {
  return plantName
    .split(' ')
    .map(word => 
      word.charAt(0).toUpperCase() + word.slice(1).toLowerCase()
    )
    .join(' ');
}
```

### Versi dengan Komentar Bahasa Indonesia
```javascript
function formatPlantName(plantName) {
  return plantName
    .split(' ')                    // Pisahkan kata berdasarkan spasi
    .map(word =>                   // Ubah setiap kata
      word.charAt(0).toUpperCase() + // Huruf pertama menjadi kapital
      word.slice(1).toLowerCase()    // Sisanya menjadi huruf kecil
    )
    .join(' ');                    // Gabungkan kembali dengan spasi
}
```

## 🎨 Contoh Penggunaan

### Input dan Output

| Input | Output |
|-------|--------|
| `"mawar merah"` | `"Mawar Merah"` |
| `"BUNGA MATAHARI"` | `"Bunga Matahari"` |
| `"anggrek bULaN"` | `"Anggrek Bulan"` |
| `"kaktus mini"` | `"Kaktus Mini"` |
| `"pohon mangga"` | `"Pohon Mangga"` |

### Contoh Implementasi

```javascript
// Contoh 1: Nama tanaman dengan huruf kecil
const plant1 = "mawar merah";
console.log(formatPlantName(plant1)); 
// Output: "Mawar Merah"

// Contoh 2: Nama tanaman dengan huruf kapital semua
const plant2 = "BUNGA MATAHARI";
console.log(formatPlantName(plant2)); 
// Output: "Bunga Matahari"

// Contoh 3: Nama tanaman dengan format campuran
const plant3 = "anggrek bULaN";
console.log(formatPlantName(plant3)); 
// Output: "Anggrek Bulan"

// Contoh 4: Penggunaan dalam array
const plants = ["mawar putih", "ANGGREK HITAM", "kaktus MiNi"];
const formattedPlants = plants.map(formatPlantName);
console.log(formattedPlants);
// Output: ["Mawar Putih", "Anggrek Hitam", "Kaktus Mini"]
```

## 📊 Tabel Method yang Digunakan

| Method | Fungsi | Contoh | Hasil |
|--------|--------|--------|-------|
| `split(' ')` | Memisahkan string berdasarkan spasi | `"mawar merah".split(' ')` | `["mawar", "merah"]` |
| `map()` | Mengubah setiap elemen array | `["mawar", "merah"].map(transform)` | `["Mawar", "Merah"]` |
| `charAt(0)` | Mengambil karakter pertama | `"mawar".charAt(0)` | `"m"` |
| `toUpperCase()` | Mengubah menjadi huruf kapital | `"m".toUpperCase()` | `"M"` |
| `slice(1)` | Mengambil substring mulai index 1 | `"mawar".slice(1)` | `"awar"` |
| `toLowerCase()` | Mengubah menjadi huruf kecil | `"awar".toLowerCase()` | `"awar"` |
| `join(' ')` | Menggabungkan array dengan spasi | `["Mawar", "Merah"].join(' ')` | `"Mawar Merah"` |

## ✅ Kelebihan

- **Compact**: Ditulis dalam satu baris yang sangat efisien
- **Functional**: Menggunakan pendekatan functional programming
- **Readable**: Mudah dibaca dan dipahami
- **Chainable**: Menggunakan method chaining yang elegan
- **Immutable**: Tidak mengubah string asli

## ⚙️ Proses Step-by-Step

```javascript
// Input: "mawar merah"
"mawar merah"
  .split(' ')           // ["mawar", "merah"]
  .map(word =>          // Proses setiap kata:
    word.charAt(0)      // "m" → "M", "m" → "M"
    .toUpperCase() +    
    word.slice(1)       // "awar" → "awar", "erah" → "erah"
    .toLowerCase()      
  )                     // ["Mawar", "Merah"]
  .join(' ')            // "Mawar Merah"
```

## ⚠️ Catatan Penting

- Fungsi ini hanya memproses spasi sebagai pemisah kata
- Input harus berupa string yang valid
- Tidak menangani karakter khusus sebagai pemisah (seperti tanda hubung)
- Sangat efisien untuk operasi yang sering dilakukan

## 🚀 Tips Penggunaan

1. **Validasi Input**: Pastikan input adalah string sebelum menggunakan fungsi
2. **Handling Error**: Tambahkan pengecekan untuk input kosong atau null
3. **Performance**: Cocok untuk operasi batch pada banyak nama tanaman
4. **Extensibility**: Dapat diperluas untuk menangani pemisah lain

## 🎯 Return Value

**Tipe**: `String`  
**Deskripsi**: Nama tanaman yang sudah diformat dengan setiap kata diawali huruf kapital

## 💡 Variasi Penggunaan

```javascript
// Untuk menangani input kosong
function formatPlantNameSafe(plantName) {
  if (!plantName || typeof plantName !== 'string') {
    return '';
  }
  
  return plantName
    .split(' ')
    .map(word => word.charAt(0).toUpperCase() + word.slice(1).toLowerCase())
    .join(' ');
}

// Untuk menangani multiple separator
function formatPlantNameAdvanced(plantName) {
  return plantName
    .split(/[\s-_]+/)  // Split berdasarkan spasi, tanda hubung, atau underscore
    .map(word => word.charAt(0).toUpperCase() + word.slice(1).toLowerCase())
    .join(' ');
}
```

---

*Dokumentasi ini dibuat untuk membantu pemula memahami cara kerja dan penggunaan fungsi `formatPlantName` dalam bentuk compact one-liner yang elegan.*
