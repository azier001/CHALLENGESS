# 🌿 Analisis Inventori Garden Center

## Level Challenge
**Medium** 🟡

---

## 📋 Gambaran Umum

Buatlah sebuah function `analyzeGardenInventory` yang memproses data tanaman dan perlengkapan untuk menghasilkan analisis inventori yang komprehensif untuk sebuah community garden center.

Function ini harus mengidentifikasi tanaman spesial, menandai masalah inventori, dan menghitung total nilai inventori.

---

## 🎯 Tujuan

Buat sebuah function yang menganalisis data tanaman dan perlengkapan untuk menyediakan:
- Identifikasi varietas tanaman spesial
- Peringatan status inventori (low stock dan high cost items)
- Kalkulasi total nilai inventori
- Ringkasan statistik dari item yang ditandai

---

## 🔧 Function Signature

```javascript
function analyzeGardenInventory(plantRecords, supplyRecords)
```

---

## 📥 Parameters

### `plantRecords` (Array)
Sebuah array berisi object yang merepresentasikan inventori tanaman.

**Struktur:**
- `name` (string) - Nama varietas tanaman
- `count` (number) - Jumlah stok yang tersedia

**Contoh:**
```javascript
[
  { name: "Helichrysum Silver", count: 12 },
  { name: "Acanthus Mollis", count: 8 },
  { name: "Lavender", count: 25 }
]
```

### `supplyRecords` (Array)
Sebuah array berisi object yang merepresentasikan perlengkapan berkebun.

**Struktur:**
- `item` (string) - Nama barang perlengkapan
- `qty` (number) - Jumlah yang tersedia
- `price` (number) - Harga per unit

**Contoh:**
```javascript
[
  { item: "Fertilizer", qty: 3, price: 25 },
  { item: "Garden Hose", qty: 10, price: 75 },
  { item: "Pruning Shears", qty: 15, price: 30 }
]
```

---

## 📤 Return Value

Mengembalikan sebuah **object** yang berisi hasil analisis inventori.

**Struktur:**
```javascript
{
  specialtyPlants: number,
  lowStockItems: number,
  highCostItems: number,
  totalValue: number
}
```

### Penjelasan Properties

| Property | Type | Deskripsi |
|----------|------|-----------|
| `specialtyPlants` | number | Jumlah tanaman yang mengandung "Helichrysum" atau "Acanthus" |
| `lowStockItems` | number | Jumlah perlengkapan dengan quantity ≤ 5 |
| `highCostItems` | number | Jumlah perlengkapan dengan price > 50 |
| `totalValue` | number | Total dari semua nilai perlengkapan (qty × price) |

---

## 🧮 Persyaratan Logic

### 1. **Identifikasi Tanaman Spesial**
- Cari nama tanaman yang mengandung `"Helichrysum"` atau `"Acanthus"`
- Pencocokan harus **case-insensitive**
- Hitung semua tanaman yang cocok

### 2. **Deteksi Low Stock**
- Tandai perlengkapan dimana `qty ≤ 5`
- Hitung semua item yang ditandai

### 3. **Deteksi High Cost**
- Tandai perlengkapan dimana `price > 50`
- Hitung semua item yang ditandai

### 4. **Kalkulasi Total Value**
- Untuk setiap perlengkapan: hitung `qty × price`
- Jumlahkan semua nilai untuk mendapatkan total nilai inventori

---

## 💡 Contoh Penggunaan

```javascript
const plants = [
  { name: "Helichrysum Italicum", count: 15 },
  { name: "Acanthus Spinosus", count: 7 },
  { name: "Rose Bush", count: 20 },
  { name: "helichrysum bracteatum", count: 10 }
];

const supplies = [
  { item: "Premium Soil", qty: 3, price: 40 },
  { item: "Watering Can", qty: 8, price: 65 },
  { item: "Hand Trowel", qty: 2, price: 15 },
  { item: "Garden Gloves", qty: 20, price: 12 }
];

const result = analyzeGardenInventory(plants, supplies);

console.log(result);
// Output:
// {
//   specialtyPlants: 3,
//   lowStockItems: 2,
//   highCostItems: 1,
//   totalValue: 1070
// }
```

---

## ✅ Poin-Poin Penting yang Perlu Diingat

- ✨ Deteksi tanaman spesial bersifat **case-insensitive**
- ⚠️ Threshold low stock adalah **≤ 5** (inklusif)
- 💰 Threshold high cost adalah **> 50** (eksklusif)
- 🧾 Total value mencakup **semua perlengkapan**, bukan hanya yang ditandai
- 📊 Sebuah perlengkapan bisa menjadi low-stock **dan** high-cost sekaligus

---

## 🎓 Kemampuan yang Diuji

- Manipulasi dan iterasi Array
- Akses property Object
- String matching (case-insensitive)
- Logic kondisional
- Kalkulasi matematika
- Agregasi data

---

**Semangat untuk implementasinya! 🌱**
