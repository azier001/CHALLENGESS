# 🎒 Dokumentasi Fungsi `canFitInBag`

## 📝 Deskripsi

Fungsi `canFitInBag` digunakan untuk mengecek apakah semua item dapat muat dalam tas berdasarkan ukuran tas yang dipilih. Fungsi ini sangat berguna untuk aplikasi e-commerce, travel planner, atau sistem inventory yang perlu memvalidasi kapasitas penyimpanan.

## 🔧 Sintaks

```javascript
canFitInBag(items, bagSize)
```

## 📋 Parameter

| Parameter | Tipe | Deskripsi | Wajib |
|-----------|------|-----------|-------|
| `items` | Array | Array yang berisi daftar item yang ingin dimasukkan ke dalam tas | ✅ Ya |
| `bagSize` | String | Ukuran tas yang tersedia (`"small"`, `"medium"`, atau `"large"`) | ✅ Ya |

## 📏 Kapasitas Tas

| Ukuran Tas | Emoji | Kapasitas Maximum | Deskripsi |
|------------|-------|-------------------|-----------|
| `"small"` | 🎒 | 3 item | Tas kecil untuk keperluan ringan |
| `"medium"` | 🎓 | 5 item | Tas sedang untuk keperluan sehari-hari |
| `"large"` | 🧳 | 7 item | Tas besar untuk perjalanan atau keperluan banyak |

## 🔄 Return Value

- **Tipe**: `Boolean`
- **`true`**: Jika jumlah item ≤ kapasitas tas
- **`false`**: Jika jumlah item > kapasitas tas

## 💻 Code Asli

```javascript
function canFitInBag(items, bagSize) {
    let capacity; // Variabel untuk menyimpan kapasitas tas
    
    // Menentukan kapasitas berdasarkan ukuran tas
    if (bagSize === "small") {
        capacity = 3; // Tas kecil: maksimal 3 item
    } else if (bagSize === "medium") {
        capacity = 5; // Tas sedang: maksimal 5 item
    } else if (bagSize === "large") {
        capacity = 7; // Tas besar: maksimal 7 item
    }
    
    // Mengecek apakah jumlah item tidak melebihi kapasitas
    return items.length <= capacity;
}
```

## 🎯 Contoh Penggunaan

### ✅ Contoh 1: Item Muat dalam Tas

```javascript
const myItems = ["buku", "pensil", "penghapus"];
const result = canFitInBag(myItems, "small");
console.log(result);
// Output: true
// Penjelasan: 3 item dapat muat dalam tas kecil (kapasitas 3)
```

### ❌ Contoh 2: Item Tidak Muat dalam Tas

```javascript
const myItems = ["laptop", "mouse", "keyboard", "charger", "headphone"];
const result = canFitInBag(myItems, "small");
console.log(result);
// Output: false
// Penjelasan: 5 item tidak dapat muat dalam tas kecil (kapasitas hanya 3)
```

### ✅ Contoh 3: Menggunakan Tas Medium

```javascript
const travelItems = ["baju", "celana", "sepatu", "shampo"];
const result = canFitInBag(travelItems, "medium");
console.log(result);
// Output: true
// Penjelasan: 4 item dapat muat dalam tas medium (kapasitas 5)
```

### ✅ Contoh 4: Menggunakan Tas Large

```javascript
const campingGear = ["tenda", "sleeping bag", "kompor", "panci", "senter", "makanan", "air"];
const result = canFitInBag(campingGear, "large");
console.log(result);
// Output: true
// Penjelasan: 7 item tepat muat dalam tas large (kapasitas 7)
```

## ⚠️ Catatan Penting

1. **Case Sensitive**: Ukuran tas harus ditulis dalam huruf kecil (`"small"`, bukan `"Small"`)
2. **Validation**: Fungsi tidak memiliki validasi untuk ukuran tas yang tidak dikenal
3. **Array Kosong**: Array kosong (`[]`) akan selalu return `true` untuk semua ukuran tas
4. **Ukuran Item**: Fungsi hanya menghitung jumlah item, tidak mempertimbangkan ukuran fisik item

## 🔨 Saran Pengembangan

Untuk pengembangan selanjutnya, pertimbangkan menambahkan:
- Validasi input untuk `bagSize`
- Support untuk ukuran tas custom
- Penanganan error untuk input yang tidak valid
- Pertimbangan bobot atau volume item

---

*Dibuat dengan ❤️ untuk memudahkan pemahaman fungsi JavaScript*
