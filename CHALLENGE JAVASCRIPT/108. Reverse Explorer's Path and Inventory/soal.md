# 🧭 Reverse Explorer's Path and Inventory

## 📋 Deskripsi Challenge

**Tingkat Kesulitan:** `Easy` 🟢

Buat sebuah function yang membantu seorang explorer untuk menelusuri kembali langkah mereka dan kembali dengan aman ke titik awal. Challenge ini menggabungkan manipulasi string dan operasi array untuk mensimulasikan skenario navigasi dunia nyata.

---

## 🎯 Tujuan

Implementasikan function bernama `reverseExplorerPath` yang memproses data perjalanan explorer dan menyediakan path terbalik untuk pulang beserta inventory yang direorganisasi.

### 📥 Function Signature

```javascript
function reverseExplorerPath(path, inventory)
```

---

## 🔧 Parameter

### `path` (string)
- **Deskripsi:** Rangkaian perintah arah
- **Format:** Karakter tunggal yang merepresentasikan arah mata angin
  - `'N'` → North ⬆️
  - `'S'` → South ⬇️  
  - `'E'` → East ➡️
  - `'W'` → West ⬅️
- **Batasan:** 
  - Panjang: 1 hingga 10 karakter
  - Hanya berisi huruf arah yang valid

### `inventory` (array of strings)
- **Deskripsi:** Koleksi item yang dikumpulkan selama eksplorasi
- **Format:** Array nama item
- **Batasan:**
  - Ukuran: 0 hingga 5 elemen
  - Setiap item: maksimal 10 huruf kecil
  - Contoh: `["compass", "map", "torch"]`

---

## 📤 Return Value

Function mengembalikan sebuah **array** dengan tepat **dua elemen**:

```javascript
[reversedPath, reversedInventory]
```

1. **`reversedPath`** (string): Path asli yang dibalik karakter demi karakter
2. **`reversedInventory`** (array): Inventory asli dengan urutan item yang dibalik

---

## 💡 Contoh Penggunaan

```javascript
// Contoh 1: Eksplorasi dasar
const path1 = "NEW";
const inventory1 = ["rope", "food", "water"];
const result1 = reverseExplorerPath(path1, inventory1);
// Returns: ["WEN", ["water", "food", "rope"]]

// Contoh 2: Inventory kosong
const path2 = "NSEW";
const inventory2 = [];
const result2 = reverseExplorerPath(path2, inventory2);
// Returns: ["WESN", []]

// Contoh 3: Arah tunggal
const path3 = "N";
const inventory3 = ["key"];
const result3 = reverseExplorerPath(path3, inventory3);
// Returns: ["N", ["key"]]
```

---

## 🧠 Petunjuk Algorithm

### Untuk Path Reversal:
- Gunakan method string seperti `split()`, `reverse()`, dan `join()`
- Atau iterasi melalui string secara mundur

### Untuk Inventory Reversal:
- Gunakan method array `reverse()`
- Atau buat array baru dengan iterasi mundur

### Pendekatan Implementasi:
```javascript
function reverseExplorerPath(path, inventory) {
    // Step 1: Reverse path string
    // Step 2: Reverse inventory array
    // Step 3: Return kedua hasil sebagai array
}
```

---

## ✅ Kriteria Sukses

- [x] Function dengan benar membalik path string
- [x] Function dengan benar membalik inventory array  
- [x] Mengembalikan hasil dalam format yang ditentukan `[string, array]`
- [x] Menangani edge case (inventory kosong, path karakter tunggal)
- [x] Mengikuti semua batasan parameter

---

## 🔍 Edge Cases yang Perlu Dipertimbangkan

- **Inventory kosong:** `inventory = []`
- **Arah tunggal:** `path = "N"`
- **Path maksimum:** `path = "NEWSNEWSNE"` (10 karakter)
- **Inventory maksimum:** 5 item dengan masing-masing 10 karakter

---

*Happy coding, explorer! 🗺️✨*
