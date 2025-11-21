# 📦 Dokumentasi Fungsi `reorganizeInventory`

## 📋 Deskripsi

Fungsi `reorganizeInventory` digunakan untuk **membalik urutan** item dalam array inventory. Fungsi ini akan mengubah urutan elemen dari yang terakhir menjadi yang pertama, dan sebaliknya.

> ⚠️ **Perhatian**: Fungsi ini akan **memodifikasi array asli** (mutable operation) karena menggunakan method `.reverse()`.

---

## 🔧 Sintaks

```javascript
reorganizeInventory(inventory)
```

---

## 📥 Parameter

| Parameter | Tipe | Wajib | Deskripsi |
|-----------|------|-------|-----------|
| `inventory` | Array | ✅ Ya | Array yang berisi daftar item inventory yang akan dibalik urutannya |

### Detail Parameter:

- **inventory**: Bisa berisi array dengan tipe data apapun (string, number, object, dll.)
- Array akan dimodifikasi secara langsung (in-place)

---

## 📤 Return Value

| Tipe | Deskripsi |
|------|-----------|
| Array | Array yang sudah dibalik urutannya (sama dengan array input yang sudah dimodifikasi) |

---

## 💻 Kode Fungsi

```javascript
/**
 * Fungsi untuk membalik urutan item dalam inventory
 * @param {Array} inventory - Array berisi daftar item inventory
 * @returns {Array} - Array dengan urutan yang sudah dibalik
 */
function reorganizeInventory(inventory) {
    // Membalik urutan elemen dalam array
    return inventory.reverse();
}
```

---

## 📖 Contoh Penggunaan

### Contoh 1: Array String (Daftar Produk)

```javascript
let products = ["Laptop", "Mouse", "Keyboard", "Monitor"];

console.log("Sebelum:", products);
// Output: ["Laptop", "Mouse", "Keyboard", "Monitor"]

let reorganized = reorganizeInventory(products);

console.log("Sesudah:", reorganized);
// Output: ["Monitor", "Keyboard", "Mouse", "Laptop"]

console.log("Array asli:", products);
// Output: ["Monitor", "Keyboard", "Mouse", "Laptop"]
// Perhatikan: array asli juga berubah!
```

### Contoh 2: Array Number (Kode Barang)

```javascript
let itemCodes = [101, 102, 103, 104, 105];

let result = reorganizeInventory(itemCodes);

console.log(result);
// Output: [105, 104, 103, 102, 101]
```

### Contoh 3: Array Object (Inventory Detail)

```javascript
let inventory = [
    { id: 1, name: "Buku", stock: 50 },
    { id: 2, name: "Pensil", stock: 100 },
    { id: 3, name: "Penghapus", stock: 75 }
];

let reversed = reorganizeInventory(inventory);

console.log(reversed);
/* Output:
[
    { id: 3, name: "Penghapus", stock: 75 },
    { id: 2, name: "Pensil", stock: 100 },
    { id: 1, name: "Buku", stock: 50 }
]
*/
```

---

## ⚡ Cara Kerja

1. Fungsi menerima parameter `inventory` berupa array
2. Method `.reverse()` dipanggil pada array tersebut
3. Array dibalik urutannya secara langsung (in-place)
4. Array yang sudah dibalik dikembalikan sebagai return value

---

## ⚠️ Hal Penting yang Perlu Diperhatikan

### 🔴 Modifikasi Array Asli

Fungsi ini **mengubah array asli**. Jika Anda ingin mempertahankan array asli, buat salinan terlebih dahulu:

```javascript
// Cara aman: membuat salinan array terlebih dahulu
let originalInventory = ["A", "B", "C"];
let copyInventory = [...originalInventory]; // spread operator untuk copy

reorganizeInventory(copyInventory);

console.log("Original:", originalInventory); // ["A", "B", "C"] - tidak berubah
console.log("Copy:", copyInventory);         // ["C", "B", "A"] - berubah
```

### ✅ Array Kosong

Fungsi tetap bekerja dengan array kosong:

```javascript
let empty = [];
console.log(reorganizeInventory(empty)); // Output: []
```

### ✅ Array dengan 1 Elemen

```javascript
let single = ["Satu"];
console.log(reorganizeInventory(single)); // Output: ["Satu"]
```

---

## 🎯 Kapan Menggunakan Fungsi Ini?

- ✅ Menampilkan item terbaru terlebih dahulu (LIFO - Last In First Out)
- ✅ Membalik urutan prioritas
- ✅ Mengubah urutan tampilan dari ascending ke descending atau sebaliknya
- ✅ Reorganisasi data untuk keperluan presentasi

---

## 📚 Referensi

- [MDN Web Docs - Array.prototype.reverse()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/reverse)

---

## 📝 Catatan Tambahan

Jika Anda membutuhkan fungsi yang **tidak mengubah array asli**, Anda bisa memodifikasi fungsi menjadi:

```javascript
function reorganizeInventory(inventory) {
    // Membuat salinan array terlebih dahulu
    return [...inventory].reverse();
}
```

Atau menggunakan `slice()`:

```javascript
function reorganizeInventory(inventory) {
    return inventory.slice().reverse();
}
```

---

**Dibuat dengan ❤️ untuk memudahkan pemahaman dokumentasi kode**
