# 🍎 Reorganize Fruit Stand Inventory

## 📋 Ringkasan Challenge

**Tingkat Kesulitan:** `Easy`

---

## 🎯 Deskripsi Soal

Buatlah sebuah function `reorganizeInventory` yang menerima array inventory dan mengembalikan 2D array dengan baris yang dibalik urutannya.

Kamu sedang membantu mengatur ulang tampilan stand buah dengan **membalik inventory dari urutan rak bawah ke rak atas**.

---

## 📥 Parameter

### `inventory` *(array)*
- Sebuah **2D array** di mana setiap baris berisi:
  - `[nama buah, jumlah]`
  
**Contoh struktur:**
```javascript
[
  ["apple", 10],
  ["banana", 5],
  ["orange", 8]
]
```

---

## 📤 Return Value

Sebuah **2D array** dengan baris dalam urutan terbalik.

**Format:** `[["fruit", quantity], ["fruit", quantity], ...]`

**Contoh output:**
```javascript
[
  ["orange", 8],
  ["banana", 5],
  ["apple", 10]
]
```

---

## 💡 Function Signature

```javascript
function reorganizeInventory(inventory) {
  // Tulis kode di sini
}
```

---

## 🧪 Contoh Penggunaan

### Input:
```javascript
const inventory = [
  ["apple", 10],
  ["banana", 5],
  ["orange", 8]
];

reorganizeInventory(inventory);
```

### Output:
```javascript
[
  ["orange", 8],
  ["banana", 5],
  ["apple", 10]
]
```

---

## 🔑 Poin Penting

- ✅ Balik urutan **baris** (bukan elemen individual)
- ✅ Pertahankan struktur setiap baris `[fruit, quantity]`
- ✅ Jangan modifikasi array asli (best practice opsional)

---

## 🚀 Mulai Mengerjakan

Pikirkan tentang JavaScript array methods yang dapat membantu kamu membalik urutan elemen. Pertimbangkan method seperti `.reverse()` atau teknik iterasi!

Semangat! 🎉
