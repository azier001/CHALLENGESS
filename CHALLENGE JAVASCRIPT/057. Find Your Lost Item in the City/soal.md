# 🔍 Temukan Barang Hilang Anda di Kota

## 📊 Ringkasan Challenge

| Atribut | Detail |
|---------|--------|
| **Tingkat Kesulitan** | `Easy` |
| **Nama Function** | `findLostItem` |
| **Kategori** | Array Searching |

---

## 🎯 Deskripsi Masalah

Buat sebuah function yang membantu menemukan barang hilang dari barang-barang penting sehari-hari. Function ini mensimulasikan skenario umum mencari melalui barang-barang Anda untuk menemukan item tertentu yang hilang.

Function harus secara efisien mencari melalui array dari items dan memberikan feedback yang jelas tentang apakah target item ada dalam koleksi Anda.

---

## 📝 Spesifikasi Function

### Function Signature
```javascript
function findLostItem(items, searchItem)
```

### Parameters

| Parameter | Type | Deskripsi |
|-----------|------|-----------|
| `items` | `Array<string>` | Daftar barang yang biasanya dibawa seseorang |
| `searchItem` | `string` | Item spesifik yang mereka coba temukan |

### Return Value

| Kondisi | Return Value |
|---------|--------------|
| Item ditemukan | `"Item found!"` |
| Item tidak ditemukan | `"Item not found!"` |

---

## 🛠️ Persyaratan Implementasi

### Logic Utama
1. **Array Traversal**: Gunakan method array atau loop melalui array `items`
2. **Perbandingan Item**: Periksa apakah `searchItem` ada dalam array `items`
3. **Conditional Return**: 
   - Jika ditemukan → return `"Item found!"`
   - Jika tidak ditemukan → return `"Item not found!"`

### Pendekatan yang Disarankan
- ✅ Gunakan method `Array.includes()`
- ✅ Gunakan method `Array.indexOf()`
- ✅ Gunakan `for` loop dengan perbandingan manual
- ✅ Gunakan method `Array.find()`

---

## 💡 Contoh Penggunaan

```javascript
// Contoh test cases
const dailyItems = ["dompet", "kunci", "ponsel", "kacamata", "buku"];

console.log(findLostItem(dailyItems, "kunci"));       // "Item found!"
console.log(findLostItem(dailyItems, "headphone"));   // "Item not found!"
console.log(findLostItem(dailyItems, "dompet"));      // "Item found!"
```

---

## 🧪 Skenario Test

| Test Case | Input Items | Search Item | Expected Output |
|-----------|-------------|-------------|-----------------|
| Item ditemukan | `["buku", "pulpen", "laptop"]` | `"pulpen"` | `"Item found!"` |
| Tidak ditemukan | `["buku", "pulpen", "laptop"]` | `"mouse"` | `"Item not found!"` |
| Array kosong | `[]` | `"ponsel"` | `"Item not found!"` |
| Case sensitive | `["Ponsel"]` | `"ponsel"` | `"Item not found!"` |

---

## 🎯 Tujuan Pembelajaran

- 📚 **Array Methods**: Berlatih menggunakan built-in array methods untuk pencarian
- 🔄 **Loops**: Memahami pola iterasi untuk pencarian data
- 🎭 **Conditional Logic**: Mengimplementasikan logic percabangan berdasarkan hasil pencarian
- 📤 **Return Statements**: Berlatih mengembalikan pesan string yang sesuai

---

## ⚡ Catatan Performance

- Time Complexity: `O(n)` dimana n adalah panjang array items
- Space Complexity: `O(1)` penggunaan ruang konstan
- Pendekatan paling efisien: method `Array.includes()`

---

## 🚀 Ide Pengembangan

Setelah Anda menguasai implementasi dasar, pertimbangkan enhancement berikut:

- 🔤 **Pencarian case-insensitive**
- 🔍 **Partial string matching**
- 📊 **Return index item ketika ditemukan**
- 📝 **Support pencarian multiple item**
