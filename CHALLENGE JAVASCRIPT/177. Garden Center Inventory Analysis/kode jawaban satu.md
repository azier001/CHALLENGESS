# 🌿 Dokumentasi Fungsi `analyzeGardenInventory`

## 📋 Deskripsi

Fungsi `analyzeGardenInventory` adalah sebuah fungsi yang digunakan untuk menganalisis inventori taman (garden). Fungsi ini akan memproses dua jenis data yaitu:
1. **Data tanaman** (plant records) - untuk menghitung jumlah tanaman spesial
2. **Data persediaan** (supply records) - untuk menganalisis stok barang, harga, dan total nilai inventori

Fungsi ini sangat berguna untuk mengelola inventori taman, mengidentifikasi item yang perlu direstock, dan menghitung nilai total aset persediaan.

---

## 🔧 Sintaks

```javascript
analyzeGardenInventory(plantRecords, supplyRecords)
```

---

## 📥 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `plantRecords` | Array of Objects | Array yang berisi daftar tanaman. Setiap objek harus memiliki properti `name` (string) yang berisi nama tanaman |
| `supplyRecords` | Array of Objects | Array yang berisi daftar persediaan. Setiap objek harus memiliki properti `qty` (number) untuk jumlah stok dan `price` (number) untuk harga per unit |

### Struktur Data Parameter

**plantRecords:**
```javascript
[
  { name: "Helichrysum Italicum" },
  { name: "Acanthus Mollis" },
  { name: "Rose Garden" }
]
```

**supplyRecords:**
```javascript
[
  { qty: 10, price: 25 },
  { qty: 3, price: 75 },
  { qty: 20, price: 15 }
]
```

---

## 📤 Return Value

Fungsi ini mengembalikan sebuah **objek** dengan 4 properti:

| Properti | Tipe | Deskripsi |
|----------|------|-----------|
| `specialtyPlants` | Number | Jumlah tanaman spesial (Helichrysum atau Acanthus) yang ditemukan |
| `lowStockItems` | Number | Jumlah item persediaan dengan stok ≤ 5 unit |
| `highCostItems` | Number | Jumlah item persediaan dengan harga > $50 per unit |
| `totalValue` | Number | Total nilai seluruh persediaan (qty × price untuk semua item) |

---

## 🌱 Tanaman Spesial

Fungsi ini mengenali dua jenis tanaman spesial:

| Nama Tanaman | Keterangan |
|--------------|------------|
| 🌼 **Helichrysum** | Tanaman abadi dengan bunga kering yang populer |
| 🌿 **Acanthus** | Tanaman hias dengan daun besar dan bunga yang indah |

> **Catatan:** Pencocokan nama tanaman tidak case-sensitive (huruf besar/kecil tidak berpengaruh)

---

## 💻 Kode Lengkap

```javascript
function analyzeGardenInventory(plantRecords, supplyRecords) {
    
    let specialtyPlants = 0;
    let lowStockItems = 0;
    let highCostItems = 0;
    let totalValue = 0;
    
    
    // Cek tanaman spesial
    for (let plant of plantRecords) {
        const plantName = plant.name.toLowerCase();
        
        // Jika nama tanaman mengandung 'helichrysum' atau 'acanthus'
        if (plantName.includes('helichrysum') || plantName.includes('acanthus')) {
            specialtyPlants++;
        }
    }
    
    
    // Analisis persediaan
    for (let supply of supplyRecords) {
        
        // Cek stok rendah (≤ 5 unit)
        if (supply.qty <= 5) {
            lowStockItems++;
        }
        
        // Cek harga tinggi (> $50)
        if (supply.price > 50) {
            highCostItems++;
        }
        
        // Hitung total nilai (jumlah × harga)
        totalValue += supply.qty * supply.price;
    }
    
    
    // Kembalikan hasil analisis
    return {
        specialtyPlants: specialtyPlants,
        lowStockItems: lowStockItems,
        highCostItems: highCostItems,
        totalValue: totalValue
    };
}
```

---

## 📖 Contoh Penggunaan

### Contoh 1: Analisis Inventori Lengkap

```javascript
// Data tanaman
const plants = [
  { name: "Helichrysum Italicum" },
  { name: "Acanthus Mollis" },
  { name: "Rose Garden" },
  { name: "Lavender" },
  { name: "Helichrysum Stoechas" }
];

// Data persediaan
const supplies = [
  { qty: 10, price: 25 },
  { qty: 3, price: 75 },
  { qty: 20, price: 15 },
  { qty: 5, price: 60 },
  { qty: 2, price: 40 }
];

// Panggil fungsi
const result = analyzeGardenInventory(plants, supplies);
console.log(result);
```

**Output:**
```javascript
{
  specialtyPlants: 3,    // Helichrysum Italicum, Acanthus Mollis, Helichrysum Stoechas
  lowStockItems: 3,      // Item dengan qty: 3, 5, 2
  highCostItems: 2,      // Item dengan harga: 75, 60
  totalValue: 785        // (10×25) + (3×75) + (20×15) + (5×60) + (2×40)
}
```

### Contoh 2: Inventori Sederhana

```javascript
const plants = [
  { name: "Tulip" },
  { name: "Daisy" }
];

const supplies = [
  { qty: 50, price: 10 },
  { qty: 8, price: 20 }
];

const result = analyzeGardenInventory(plants, supplies);
console.log(result);
```

**Output:**
```javascript
{
  specialtyPlants: 0,    // Tidak ada tanaman spesial
  lowStockItems: 0,      // Semua stok di atas 5
  highCostItems: 0,      // Tidak ada harga di atas $50
  totalValue: 660        // (50×10) + (8×20)
}
```

---

## ⚠️ Catatan Penting

1. **Case Insensitive**: Pencocokan nama tanaman tidak membedakan huruf besar/kecil
2. **Low Stock Threshold**: Item dianggap stok rendah jika jumlahnya ≤ 5 unit
3. **High Cost Threshold**: Item dianggap harga tinggi jika harganya > $50
4. **Total Value**: Dihitung dengan mengalikan qty × price untuk setiap item lalu dijumlahkan

---

## 🎯 Use Case

Fungsi ini cocok digunakan untuk:
- 📊 Dashboard manajemen inventori taman
- 🔔 Sistem notifikasi restock otomatis
- 💰 Perhitungan nilai aset persediaan
- 📈 Laporan analisis inventori berkala

---

## 🤝 Tips Penggunaan

- Pastikan setiap objek di `plantRecords` memiliki properti `name`
- Pastikan setiap objek di `supplyRecords` memiliki properti `qty` dan `price`
- Gunakan fungsi ini secara berkala untuk monitoring inventori
- Kombinasikan dengan sistem alert untuk item low-stock

---

**Dibuat dengan 💚 untuk pengelolaan taman yang lebih baik**
