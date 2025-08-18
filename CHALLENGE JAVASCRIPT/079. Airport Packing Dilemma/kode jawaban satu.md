# 🎒 Fungsi canFitInBag

## 📝 Deskripsi

Fungsi `canFitInBag` adalah sebuah utility function yang digunakan untuk memeriksa apakah sejumlah item dapat muat dalam tas berdasarkan ukuran tas yang dipilih. Fungsi ini sangat berguna untuk aplikasi e-commerce, sistem inventory, atau game yang memiliki sistem tas/storage.

## 🔧 Parameter

| Parameter | Tipe | Deskripsi | Wajib |
|-----------|------|-----------|--------|
| `items` | Array | Array yang berisi item-item yang akan dimasukkan ke dalam tas | ✅ Ya |
| `bagSize` | String | Ukuran tas yang tersedia: "small", "medium", atau "large" | ✅ Ya |

## 📊 Kapasitas Tas

| Ukuran Tas | Kapasitas Maximum | Emoji |
|------------|-------------------|-------|
| `"small"` | 3 item | 🎒 |
| `"medium"` | 5 item | 🎒🎒 |
| `"large"` | 7 item | 🎒🎒🎒 |

## 📤 Return Value

- **`true`**: Jika jumlah item dapat muat dalam tas
- **`false`**: Jika jumlah item melebihi kapasitas tas atau ukuran tas tidak valid

## 💻 Source Code

```javascript
function canFitInBag(items, bagSize) {
  let capacity;
  
  // Tentukan kapasitas berdasarkan ukuran tas
  switch (bagSize) {
    case "small":
      capacity = 3;  // Tas kecil maksimal 3 item
      break;
    case "medium":
      capacity = 5;  // Tas sedang maksimal 5 item
      break;
    case "large":
      capacity = 7;  // Tas besar maksimal 7 item
      break;
    default:
      return false;  // Ukuran tas tidak valid
  }
  
  // Periksa apakah jumlah item tidak melebihi kapasitas
  return items.length <= capacity;
}
```

## 🚀 Contoh Penggunaan

### ✅ Contoh Berhasil

```javascript
// Tas kecil dengan 2 item - MUAT ✅
const items1 = ["buku", "pulpen"];
console.log(canFitInBag(items1, "small")); 
// Output: true

// Tas sedang dengan 4 item - MUAT ✅
const items2 = ["laptop", "mouse", "charger", "notebook"];
console.log(canFitInBag(items2, "medium")); 
// Output: true

// Tas besar dengan 6 item - MUAT ✅
const items3 = ["baju1", "baju2", "celana1", "celana2", "kaos kaki", "topi"];
console.log(canFitInBag(items3, "large")); 
// Output: true
```

### ❌ Contoh Gagal

```javascript
// Tas kecil dengan 4 item - TIDAK MUAT ❌
const items4 = ["item1", "item2", "item3", "item4"];
console.log(canFitInBag(items4, "small")); 
// Output: false

// Tas sedang dengan 6 item - TIDAK MUAT ❌
const items5 = ["a", "b", "c", "d", "e", "f"];
console.log(canFitInBag(items5, "medium")); 
// Output: false

// Ukuran tas tidak valid - ERROR ❌
const items6 = ["item1"];
console.log(canFitInBag(items6, "extra-large")); 
// Output: false
```

## 🎯 Use Case

Fungsi ini cocok digunakan untuk:

- **🛒 E-commerce**: Validasi shopping cart berdasarkan jenis pengiriman
- **🎮 Game Development**: Sistem inventory dengan batasan kapasitas
- **📦 Logistics App**: Penentuan jenis kemasan berdasarkan jumlah barang
- **🎒 Travel App**: Rekomendasi ukuran tas berdasarkan barang bawaan

## 💡 Tips Penggunaan

1. **Validasi Input**: Pastikan parameter `items` adalah array yang valid
2. **Case Sensitivity**: Ukuran tas harus dalam huruf kecil ("small", bukan "Small")
3. **Error Handling**: Fungsi mengembalikan `false` untuk input yang tidak valid
4. **Performance**: Fungsi hanya mengecek `length` dari array, bukan isi item

## ⚠️ Catatan Penting

- Fungsi ini hanya menghitung **jumlah item**, bukan ukuran atau berat item
- Ukuran tas harus tepat sesuai dengan yang didefinisikan (case-sensitive)
- Array kosong (`[]`) akan selalu mengembalikan `true` untuk semua ukuran tas yang valid
