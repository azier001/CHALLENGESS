# 🔍 Dokumentasi Fungsi `findLostItem`

## 📝 Deskripsi

Fungsi `findLostItem` adalah sebuah utility function yang digunakan untuk mencari apakah suatu item tertentu ada dalam sebuah daftar/array. Fungsi ini sangat berguna ketika Anda ingin mengecek keberadaan suatu barang dalam koleksi data.

## 🎯 Kegunaan

- Mencari item dalam array
- Validasi keberadaan data
- Filtering dan pencarian sederhana
- Debugging untuk mengecek apakah nilai ada dalam dataset

## 📋 Parameter

| Parameter | Tipe | Deskripsi | Wajib |
|-----------|------|-----------|-------|
| `items` | Array | Daftar item yang akan dicari | ✅ Ya |
| `searchItem` | Any | Item yang ingin dicari dalam daftar | ✅ Ya |

### Penjelasan Parameter:

- **`items`**: Array yang berisi kumpulan data/item. Bisa berupa array string, number, atau tipe data lainnya.
- **`searchItem`**: Nilai yang ingin dicari. Tipe data harus sesuai dengan tipe data yang ada dalam array `items`.

## 📤 Return Value

| Return Value | Tipe | Kondisi |
|--------------|------|---------|
| `"Item found!"` | String | Ketika item ditemukan dalam array |
| `"Item not found!"` | String | Ketika item tidak ditemukan dalam array |

## 💻 Source Code

```javascript
function findLostItem(items, searchItem) {
    // Menggunakan method includes() untuk mencari item dalam array
    // Jika item ditemukan, return "Item found!", jika tidak return "Item not found!"
    return items.includes(searchItem) ? "Item found!" : "Item not found!";
}
```

## 🚀 Contoh Penggunaan

### Contoh 1: Mencari Item dalam Array String

```javascript
const daftarBuah = ["apel", "jeruk", "mangga", "pisang"];
const hasilPencarian = findLostItem(daftarBuah, "mangga");

console.log(hasilPencarian);
// Output: "Item found!"
```

### Contoh 2: Mencari Item yang Tidak Ada

```javascript
const daftarWarna = ["merah", "biru", "hijau"];
const hasilPencarian = findLostItem(daftarWarna, "kuning");

console.log(hasilPencarian);
// Output: "Item not found!"
```

### Contoh 3: Mencari Angka dalam Array

```javascript
const daftarAngka = [1, 5, 10, 15, 20];
const hasilPencarian = findLostItem(daftarAngka, 10);

console.log(hasilPencarian);
// Output: "Item found!"
```

### Contoh 4: Array Kosong

```javascript
const arrayKosong = [];
const hasilPencarian = findLostItem(arrayKosong, "apapun");

console.log(hasilPencarian);
// Output: "Item not found!"
```

## ⚠️ Catatan Penting

1. **Case Sensitive**: Pencarian string bersifat case-sensitive
   ```javascript
   findLostItem(["Apple"], "apple"); // "Item not found!"
   findLostItem(["Apple"], "Apple"); // "Item found!"
   ```

2. **Tipe Data**: Pastikan tipe data yang dicari sesuai dengan tipe data dalam array
   ```javascript
   findLostItem([1, 2, 3], "1"); // "Item not found!" (number vs string)
   findLostItem([1, 2, 3], 1);   // "Item found!"
   ```

3. **Array Kosong**: Fungsi akan selalu return "Item not found!" untuk array kosong

## 🛠️ Cara Menggunakan

1. **Panggil fungsi** dengan 2 parameter: array dan item yang dicari
2. **Terima hasil** berupa string konfirmasi
3. **Gunakan hasil** untuk logika selanjutnya dalam aplikasi Anda

```javascript
// Contoh implementasi dalam aplikasi
const inventory = ["laptop", "mouse", "keyboard", "monitor"];
const itemDicari = "mouse";

const status = findLostItem(inventory, itemDicari);

if (status === "Item found!") {
    console.log(`✅ ${itemDicari} tersedia di inventory`);
} else {
    console.log(`❌ ${itemDicari} tidak tersedia di inventory`);
}
```

## 🔧 Alternatif Pengembangan

Anda bisa mengembangkan fungsi ini untuk kebutuhan yang lebih kompleks:

```javascript
// Versi yang mengembalikan boolean
function isItemExists(items, searchItem) {
    return items.includes(searchItem);
}

// Versi yang mengembalikan index
function findItemIndex(items, searchItem) {
    return items.indexOf(searchItem);
}
```

---

*Dokumentasi ini dibuat untuk membantu pemula memahami cara kerja dan penggunaan fungsi `findLostItem`* 📚
