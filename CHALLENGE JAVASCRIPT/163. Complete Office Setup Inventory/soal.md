# 📦 Complete Office Setup Inventory

## Gambaran Challenge

**Difficulty Level:** `Easy` 🟢

---

## 🎯 Deskripsi Masalah

Kamu sedang menyiapkan workspace kantor di rumah dan perlu membuat inventory lengkap dengan menggabungkan perlengkapan yang sudah ada dengan pembelian baru.

Tulis sebuah function yang menggabungkan perlengkapan kantor yang sudah ada dengan item yang baru dibeli untuk menjaga daftar inventory tetap terorganisir.

---

## 📋 Spesifikasi Function

### Nama Function
```javascript
combineOfficeSupplies(existingItems, newItems)
```

### Parameters

| Parameter | Type | Deskripsi |
|-----------|------|-----------|
| `existingItems` | `array` | Perlengkapan kantor yang sudah kamu miliki |
| `newItems` | `array` | Perlengkapan baru yang baru saja dibeli |

### Return Value

**Type:** `array`

**Format:** `['item1', 'item2', 'item3']`

**Deskripsi:** Array gabungan dengan item yang sudah ada di urutan pertama, diikuti oleh item baru.

---

## 💡 Contoh Penggunaan

```javascript
// Contoh 1: Kombinasi dasar
const existing = ['pen', 'notebook', 'stapler'];
const newPurchases = ['printer paper', 'markers', 'sticky notes'];

combineOfficeSupplies(existing, newPurchases);
// Returns: ['pen', 'notebook', 'stapler', 'printer paper', 'markers', 'sticky notes']
```

```javascript
// Contoh 2: Inventory existing kosong
const existing = [];
const newPurchases = ['desk lamp', 'mouse pad'];

combineOfficeSupplies(existing, newPurchases);
// Returns: ['desk lamp', 'mouse pad']
```

```javascript
// Contoh 3: Tidak ada pembelian baru
const existing = ['keyboard', 'monitor'];
const newPurchases = [];

combineOfficeSupplies(existing, newPurchases);
// Returns: ['keyboard', 'monitor']
```

---

## ✅ Requirements

- ✓ Item existing harus muncul **pertama** dalam array gabungan
- ✓ Item baru harus muncul **setelah** semua item existing
- ✓ Pertahankan urutan asli item dalam setiap kategori
- ✓ Tangani array kosong dengan baik

---

## 🚀 Memulai

Mulailah dengan memikirkan:
- Bagaimana cara menggabungkan dua array di JavaScript
- Method array apa saja yang tersedia untuk menggabungkan array
- Bagaimana mempertahankan urutan yang benar

Selamat mengerjakan system inventory kantor kamu! 🎉
