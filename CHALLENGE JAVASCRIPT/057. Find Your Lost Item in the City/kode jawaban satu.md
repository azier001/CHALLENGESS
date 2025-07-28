# 🔍 Dokumentasi Fungsi `findLostItem`

## 📝 Deskripsi

Fungsi `findLostItem` adalah sebuah utility function yang digunakan untuk mencari apakah suatu item tertentu ada dalam sebuah daftar/array. Fungsi ini sangat berguna ketika Anda ingin mengecek keberadaan suatu barang dalam koleksi data dengan menggunakan struktur kondisional yang jelas dan mudah dipahami.

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
  // Mengecek apakah item yang dicari ada dalam array menggunakan method includes()
  if (items.includes(searchItem)) {
    // Jika item ditemukan, kembalikan pesan sukses
    return "Item found!";
  } else {
    // Jika item tidak ditemukan, kembalikan pesan gagal
    return "Item not found!";
  }
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

### Contoh 5: Penggunaan dalam Kondisi

```javascript
const inventory = ["laptop", "mouse", "keyboard"];
const itemDicari = "tablet";

const status = findLostItem(inventory, itemDicari);

if (status === "Item found!") {
    console.log(`✅ ${itemDicari} tersedia di inventory`);
} else {
    console.log(`❌ ${itemDicari} tidak tersedia, perlu dibeli`);
}
// Output: "❌ tablet tidak tersedia, perlu dibeli"
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

4. **Struktur If-Else**: Fungsi ini menggunakan struktur kondisional yang eksplisit, membuatnya mudah dipahami dan di-debug

## 🔍 Cara Kerja Fungsi

1. **Input Validation**: Fungsi menerima dua parameter (items dan searchItem)
2. **Pencarian**: Menggunakan method `includes()` untuk mencari item dalam array
3. **Kondisi If**: Jika item ditemukan, masuk ke blok `if`
4. **Kondisi Else**: Jika item tidak ditemukan, masuk ke blok `else`
5. **Return**: Mengembalikan string sesuai dengan hasil pencarian

## 🛠️ Cara Menggunakan

1. **Siapkan array** yang berisi daftar item
2. **Tentukan item** yang ingin dicari
3. **Panggil fungsi** dengan kedua parameter tersebut
4. **Terima dan gunakan** hasil pencarian

```javascript
// Langkah-langkah penggunaan
const daftarMakanan = ["nasi", "ayam", "sayur", "buah"];  // 1. Siapkan array
const makananDicari = "ayam";                             // 2. Tentukan item

const hasil = findLostItem(daftarMakanan, makananDicari); // 3. Panggil fungsi

console.log(`Status pencarian: ${hasil}`);               // 4. Gunakan hasil
// Output: "Status pencarian: Item found!"
```

## 🔧 Variasi dan Pengembangan

Anda bisa mengembangkan fungsi ini untuk kebutuhan yang lebih spesifik:

```javascript
// Versi yang mengembalikan boolean
function isItemExists(items, searchItem) {
  if (items.includes(searchItem)) {
    return true;
  } else {
    return false;
  }
}

// Versi yang mengembalikan posisi item
function findItemPosition(items, searchItem) {
  if (items.includes(searchItem)) {
    return items.indexOf(searchItem);
  } else {
    return -1;
  }
}

// Versi dengan pesan kustom
function findItemCustomMessage(items, searchItem, foundMsg, notFoundMsg) {
  if (items.includes(searchItem)) {
    return foundMsg;
  } else {
    return notFoundMsg;
  }
}
```

## 🎓 Tips untuk Pemula

- **Pahami Method `includes()`**: Method ini mengembalikan `true` jika item ditemukan, `false` jika tidak
- **Gunakan Console.log**: Untuk debugging, tambahkan `console.log()` di dalam blok if-else
- **Test Edge Cases**: Selalu test dengan array kosong, item yang tidak ada, dan tipe data berbeda
- **Consistent Naming**: Gunakan nama variabel yang deskriptif dan konsisten

---

*Dokumentasi ini dibuat untuk membantu pemula memahami cara kerja dan penggunaan fungsi `findLostItem` dengan struktur kondisional yang jelas* 📚
