# 🌿 Tutorial: Menulis Garden Inventory Analyzer dari Nol

> **Real Development Flow**: Kita akan menulis function ini bertahap, seperti developer sebenarnya bekerja - mulai dari kebutuhan sederhana, lalu tambah fitur step-by-step!

---

## 🎯 Apa yang Akan Kita Buat?

Function yang menganalisis data tanaman dan supplies, lalu memberikan laporan:
- Berapa tanaman spesial (Helichrysum/Acanthus)
- Berapa item stock rendah (≤5)
- Berapa item harga tinggi (>50)
- Total nilai inventory

---

## 📦 Step 1: Setup Data Testing

Sebelum menulis function, siapkan data untuk testing.

```javascript
// Data tanaman
const plantRecords = [
    { name: 'Helichrysum Italicum', type: 'herb' },
    { name: 'Acanthus Mollis', type: 'perennial' },
    { name: 'Rose Bush', type: 'shrub' },
    { name: 'Lavender', type: 'herb' }
];

// Data supplies
const supplyRecords = [
    { item: 'Fertilizer Premium', qty: 3, price: 75 },
    { item: 'Garden Hose', qty: 10, price: 25 },
    { item: 'Pruning Shears', qty: 2, price: 60 },
    { item: 'Compost Bag', qty: 20, price: 15 }
];
```

✅ **Test**: Copy-paste di console browser, tekan Enter. Tidak ada error = berhasil!

---

## 🔧 Step 2: Buat Function Skeleton

Mulai dengan function kosong yang akan kita isi bertahap.

```javascript
function analyzeGardenInventory(plantRecords, supplyRecords) {
    // Nanti diisi step-by-step
}
```

✅ **Test**: 
```javascript
const result = analyzeGardenInventory(plantRecords, supplyRecords);
console.log(result);
```

**Expected**: `undefined` (normal, karena function belum return apa-apa)

---

## 🌱 Step 3: Analisis Tanaman Spesial - Iterasi 1 (Basic Loop)

> **Kenapa mulai dari sini?** Paling sederhana - cuma perlu loop dan counter!

```javascript
function analyzeGardenInventory(plantRecords, supplyRecords) {
    let specialtyPlants = 0;
    
    // Loop semua tanaman
    for (let plant of plantRecords) {
        console.log('Checking:', plant.name);
    }
    
    return {
        specialtyPlants: specialtyPlants
    };
}
```

✅ **Test**:
```javascript
const result = analyzeGardenInventory(plantRecords, supplyRecords);
```

**Expected Output di Console**:
```
Checking: Helichrysum Italicum
Checking: Acanthus Mollis
Checking: Rose Bush
Checking: Lavender
```

---

## 🌱 Step 4: Analisis Tanaman Spesial - Iterasi 2 (Cek Nama)

Sekarang kita cek apakah nama mengandung kata kunci spesial.

```javascript
function analyzeGardenInventory(plantRecords, supplyRecords) {
    let specialtyPlants = 0;
    
    for (let plant of plantRecords) {
        const plantName = plant.name.toLowerCase();
        console.log('Lowercase name:', plantName);
    }
    
    return {
        specialtyPlants: specialtyPlants
    };
}
```

✅ **Test**:
```javascript
const result = analyzeGardenInventory(plantRecords, supplyRecords);
```

**Expected Output**:
```
Lowercase name: helichrysum italicum
Lowercase name: acanthus mollis
Lowercase name: rose bush
Lowercase name: lavender
```

> 💡 **Kenapa `.toLowerCase()`?** Biar 'HELICHRYSUM', 'Helichrysum', atau 'helichrysum' semua terdeteksi!

---

## 🌱 Step 5: Analisis Tanaman Spesial - Iterasi 3 (Complete Logic)

Tambahkan pengecekan keyword dan increment counter.

```javascript
function analyzeGardenInventory(plantRecords, supplyRecords) {
    let specialtyPlants = 0;
    
    for (let plant of plantRecords) {
        const plantName = plant.name.toLowerCase();
        
        if (plantName.includes('helichrysum') || plantName.includes('acanthus')) {
            specialtyPlants++;
            console.log('✅ Found specialty plant:', plant.name);
        }
    }
    
    return {
        specialtyPlants: specialtyPlants
    };
}
```

✅ **Test**:
```javascript
const result = analyzeGardenInventory(plantRecords, supplyRecords);
console.log('Total specialty plants:', result.specialtyPlants);
```

**Expected Output**:
```
✅ Found specialty plant: Helichrysum Italicum
✅ Found specialty plant: Acanthus Mollis
Total specialty plants: 2
```

🎉 **DONE!** Fitur pertama selesai. Hapus `console.log` sebelum lanjut.

---

## 📊 Step 6: Analisis Supplies - Iterasi 1 (Loop Supplies)

Sekarang kita beralih ke supplies. Mulai dengan loop basic.

```javascript
function analyzeGardenInventory(plantRecords, supplyRecords) {
    let specialtyPlants = 0;
    let lowStockItems = 0;
    
    // Analisis tanaman
    for (let plant of plantRecords) {
        const plantName = plant.name.toLowerCase();
        if (plantName.includes('helichrysum') || plantName.includes('acanthus')) {
            specialtyPlants++;
        }
    }
    
    // Analisis supplies - loop dulu
    for (let supply of supplyRecords) {
        console.log('Supply:', supply.item, '| Qty:', supply.qty);
    }
    
    return {
        specialtyPlants: specialtyPlants,
        lowStockItems: lowStockItems
    };
}
```

✅ **Test**:
```javascript
const result = analyzeGardenInventory(plantRecords, supplyRecords);
```

**Expected Output**:
```
Supply: Fertilizer Premium | Qty: 3
Supply: Garden Hose | Qty: 10
Supply: Pruning Shears | Qty: 2
Supply: Compost Bag | Qty: 20
```

---

## 📊 Step 7: Analisis Supplies - Iterasi 2 (Cek Low Stock)

Tambahkan pengecekan stock rendah (qty ≤ 5).

```javascript
function analyzeGardenInventory(plantRecords, supplyRecords) {
    let specialtyPlants = 0;
    let lowStockItems = 0;
    
    // Analisis tanaman
    for (let plant of plantRecords) {
        const plantName = plant.name.toLowerCase();
        if (plantName.includes('helichrysum') || plantName.includes('acanthus')) {
            specialtyPlants++;
        }
    }
    
    // Analisis supplies
    for (let supply of supplyRecords) {
        // Cek low stock
        if (supply.qty <= 5) {
            lowStockItems++;
            console.log('⚠️ Low stock:', supply.item, '(Qty:', supply.qty + ')');
        }
    }
    
    return {
        specialtyPlants: specialtyPlants,
        lowStockItems: lowStockItems
    };
}
```

✅ **Test**:
```javascript
const result = analyzeGardenInventory(plantRecords, supplyRecords);
console.log('Total low stock items:', result.lowStockItems);
```

**Expected Output**:
```
⚠️ Low stock: Fertilizer Premium (Qty: 3)
⚠️ Low stock: Pruning Shears (Qty: 2)
Total low stock items: 2
```

---

## 📊 Step 8: Analisis Supplies - Iterasi 3 (Tambah High Cost)

Tambahkan pengecekan item mahal (price > 50).

```javascript
function analyzeGardenInventory(plantRecords, supplyRecords) {
    let specialtyPlants = 0;
    let lowStockItems = 0;
    let highCostItems = 0;
    
    // Analisis tanaman
    for (let plant of plantRecords) {
        const plantName = plant.name.toLowerCase();
        if (plantName.includes('helichrysum') || plantName.includes('acanthus')) {
            specialtyPlants++;
        }
    }
    
    // Analisis supplies
    for (let supply of supplyRecords) {
        // Cek low stock
        if (supply.qty <= 5) {
            lowStockItems++;
        }
        
        // Cek high cost
        if (supply.price > 50) {
            highCostItems++;
            console.log('💰 High cost item:', supply.item, '($' + supply.price + ')');
        }
    }
    
    return {
        specialtyPlants: specialtyPlants,
        lowStockItems: lowStockItems,
        highCostItems: highCostItems
    };
}
```

✅ **Test**:
```javascript
const result = analyzeGardenInventory(plantRecords, supplyRecords);
console.log('Results:', result);
```

**Expected Output**:
```
💰 High cost item: Fertilizer Premium ($75)
💰 High cost item: Pruning Shears ($60)
Results: {
  specialtyPlants: 2,
  lowStockItems: 2,
  highCostItems: 2
}
```

---

## 📊 Step 9: Analisis Supplies - Iterasi 4 (Hitung Total Value)

Fitur terakhir: hitung total nilai inventory.

```javascript
function analyzeGardenInventory(plantRecords, supplyRecords) {
    let specialtyPlants = 0;
    let lowStockItems = 0;
    let highCostItems = 0;
    let totalValue = 0;
    
    // Analisis tanaman
    for (let plant of plantRecords) {
        const plantName = plant.name.toLowerCase();
        if (plantName.includes('helichrysum') || plantName.includes('acanthus')) {
            specialtyPlants++;
        }
    }
    
    // Analisis supplies
    for (let supply of supplyRecords) {
        // Cek low stock
        if (supply.qty <= 5) {
            lowStockItems++;
        }
        
        // Cek high cost
        if (supply.price > 50) {
            highCostItems++;
        }
        
        // Hitung total value
        const itemValue = supply.qty * supply.price;
        totalValue += itemValue;
        console.log(supply.item + ':', supply.qty, 'x $' + supply.price, '= $' + itemValue);
    }
    
    return {
        specialtyPlants: specialtyPlants,
        lowStockItems: lowStockItems,
        highCostItems: highCostItems,
        totalValue: totalValue
    };
}
```

✅ **Test**:
```javascript
const result = analyzeGardenInventory(plantRecords, supplyRecords);
console.log('Total inventory value: $' + result.totalValue);
```

**Expected Output**:
```
Fertilizer Premium: 3 x $75 = $225
Garden Hose: 10 x $25 = $250
Pruning Shears: 2 x $60 = $120
Compost Bag: 20 x $15 = $300
Total inventory value: $895
```

---

## ✨ Step 10: Clean Up (Final Version)

Hapus semua `console.log` untuk production code.

```javascript
function analyzeGardenInventory(plantRecords, supplyRecords) {
    let specialtyPlants = 0;
    let lowStockItems = 0;
    let highCostItems = 0;
    let totalValue = 0;
    
    // Check for specialty plants
    for (let plant of plantRecords) {
        const plantName = plant.name.toLowerCase();
        if (plantName.includes('helichrysum') || plantName.includes('acanthus')) {
            specialtyPlants++;
        }
    }
    
    // Analyze supplies
    for (let supply of supplyRecords) {
        // Check for low stock
        if (supply.qty <= 5) {
            lowStockItems++;
        }
        
        // Check for high cost
        if (supply.price > 50) {
            highCostItems++;
        }
        
        // Calculate total value
        totalValue += supply.qty * supply.price;
    }
    
    return {
        specialtyPlants: specialtyPlants,
        lowStockItems: lowStockItems,
        highCostItems: highCostItems,
        totalValue: totalValue
    };
}
```

✅ **Final Test**:
```javascript
const result = analyzeGardenInventory(plantRecords, supplyRecords);
console.log(result);
```

**Expected Output**:
```javascript
{
  specialtyPlants: 2,
  lowStockItems: 2,
  highCostItems: 2,
  totalValue: 895
}
```

🎉 **SELESAI!** Function sudah complete dan siap pakai!

---

## 🚨 Common Mistakes

| ❌ SALAH | ✅ BENAR | Kenapa Salah? |
|---------|---------|---------------|
| `plant.name.includes('Helichrysum')` | `plant.name.toLowerCase().includes('helichrysum')` | Case sensitive - 'helichrysum' tidak akan ketemu |
| `if (supply.qty < 5)` | `if (supply.qty <= 5)` | Qty 5 masih dianggap low stock |
| `totalValue = supply.qty * supply.price` | `totalValue += supply.qty * supply.price` | Pakai `=` akan overwrite, bukan akumulasi |
| `for (let i = 0; i < plantRecords; i++)` | `for (let plant of plantRecords)` | Typo - kurang `.length` |

---

## 📚 Quick Reference Card

### **Function Structure**
```javascript
function analyzeGardenInventory(plantRecords, supplyRecords) {
    // 1. Declare counters
    // 2. Loop plantRecords → count specialty
    // 3. Loop supplyRecords → count low/high/value
    // 4. Return object with results
}
```

### **Key Concepts**
| Konsep | Syntax | Kegunaan |
|--------|--------|----------|
| **for...of loop** | `for (let item of array)` | Loop array tanpa index |
| **String check** | `.toLowerCase().includes('text')` | Cek substring case-insensitive |
| **Accumulate** | `total += value` | Tambahkan ke variable |
| **Multiple conditions** | `if (a \|\| b)` | Salah satu true = execute |

### **Testing Tips**
- ✅ Tambahkan `console.log` sementara untuk debug
- ✅ Test dengan data minimal (2-3 items) dulu
- ✅ Test edge cases: qty = 0, price = 0, empty array
- ✅ Hapus `console.log` sebelum production

---

## 🎯 Development Flow Summary

```
Setup Data → Function Skeleton → Loop Plants (test) 
→ Check Names (test) → Count Specialty (test) 
→ Loop Supplies (test) → Check Low Stock (test) 
→ Check High Cost (test) → Calculate Total (test) 
→ Clean Up → Final Test ✅
```

> 💡 **Key Takeaway**: Jangan tulis full function sekaligus! Build incrementally, test di setiap step, baru lanjut ke fitur berikutnya.
