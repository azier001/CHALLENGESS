# 🎯 Tutorial: Build Shop Orders Processor dari Nol

> **Goal**: Membuat function yang menghitung sandwich orders dan menemukan meja available

---

## 📋 Setup Awal

Kita akan membuat function yang menerima 2 input:
- `orders`: Array berisi nama sandwich yang dipesan
- `tableStatuses`: Array berisi status meja ('available' atau 'occupied')

### Step 1: Buat Function Skeleton

```javascript
function processShopOrders(orders, tableStatuses) {
    
}
```

**Test:**
```javascript
const orders = ['BLT', 'Club', 'BLT', 'Tuna'];
const tables = ['occupied', 'available', 'available', 'occupied'];

console.log(processShopOrders(orders, tables));
// Output: undefined
```

---

## 🥪 Part 1: Counting Sandwiches

### Step 2: Siapkan Object untuk Counting

```javascript
function processShopOrders(orders, tableStatuses) {
    const sandwichCounts = {};
}
```

> **💡 Why Object?** Kita butuh pasangan nama-jumlah. Object perfect untuk ini: `{nama: jumlah}`

---

### Step 3: Loop Through Orders (Iterasi Pertama - Basic Count)

```javascript
function processShopOrders(orders, tableStatuses) {
    const sandwichCounts = {};
    
    for (const sandwich of orders) {
        sandwichCounts[sandwich] = 1;
    }
}
```

**Test:**
```javascript
const orders = ['BLT', 'Club', 'BLT'];
processShopOrders(orders, []);

// Cek isi sandwichCounts (tambahkan console.log temporary):
console.log(sandwichCounts);
// Output: { BLT: 1, Club: 1 } ❌ BLT harusnya 2!
```

---

### Step 4: Fix Counting Logic - Handle Duplicate

```javascript
function processShopOrders(orders, tableStatuses) {
    const sandwichCounts = {};
    
    for (const sandwich of orders) {
        if (sandwichCounts[sandwich]) {
            sandwichCounts[sandwich] = sandwichCounts[sandwich] + 1;
        } else {
            sandwichCounts[sandwich] = 1;
        }
    }
}
```

**Test:**
```javascript
const orders = ['BLT', 'Club', 'BLT'];
processShopOrders(orders, []);

console.log(sandwichCounts);
// Output: { BLT: 2, Club: 1 } ✅
```

---

### Step 5: Refactor dengan Operator ||

```javascript
function processShopOrders(orders, tableStatuses) {
    const sandwichCounts = {};
    
    for (const sandwich of orders) {
        sandwichCounts[sandwich] = (sandwichCounts[sandwich] || 0) + 1;
    }
}
```

> **💡 Shortcut Explained:**  
> `sandwichCounts[sandwich] || 0` artinya:
> - Kalau `sandwichCounts[sandwich]` ada (truthy) → pakai nilai itu
> - Kalau belum ada (undefined) → pakai 0

**Test (sama seperti step 4):**
```javascript
const orders = ['BLT', 'Club', 'BLT', 'Tuna', 'BLT'];
processShopOrders(orders, []);

console.log(sandwichCounts);
// Output: { BLT: 3, Club: 1, Tuna: 1 } ✅
```

---

## 🪑 Part 2: Finding Available Tables

### Step 6: Siapkan Array untuk Available Tables

```javascript
function processShopOrders(orders, tableStatuses) {
    const sandwichCounts = {};
    
    for (const sandwich of orders) {
        sandwichCounts[sandwich] = (sandwichCounts[sandwich] || 0) + 1;
    }
    
    const availableTables = [];
}
```

---

### Step 7: Loop Through Table Statuses

```javascript
function processShopOrders(orders, tableStatuses) {
    const sandwichCounts = {};
    
    for (const sandwich of orders) {
        sandwichCounts[sandwich] = (sandwichCounts[sandwich] || 0) + 1;
    }
    
    const availableTables = [];
    
    for (let i = 0; i < tableStatuses.length; i++) {
        console.log(i, tableStatuses[i]); // Debug: lihat index dan status
    }
}
```

> **🔧 Why for loop biasa?** Karena kita butuh **index** untuk numbering meja

**Test:**
```javascript
const tables = ['occupied', 'available', 'available', 'occupied'];
processShopOrders([], tables);

// Output console:
// 0 'occupied'
// 1 'available'
// 2 'available'
// 3 'occupied'
```

---

### Step 8: Filter Available Tables (Array Index)

```javascript
function processShopOrders(orders, tableStatuses) {
    const sandwichCounts = {};
    
    for (const sandwich of orders) {
        sandwichCounts[sandwich] = (sandwichCounts[sandwich] || 0) + 1;
    }
    
    const availableTables = [];
    
    for (let i = 0; i < tableStatuses.length; i++) {
        if (tableStatuses[i] === 'available') {
            availableTables.push(i);
        }
    }
}
```

**Test:**
```javascript
const tables = ['occupied', 'available', 'available', 'occupied'];
processShopOrders([], tables);

console.log(availableTables);
// Output: [1, 2] ❌ Tapi meja di dunia nyata nomor 2 dan 3, bukan 1 dan 2!
```

---

### Step 9: Convert to 1-Indexed Table Numbers

```javascript
function processShopOrders(orders, tableStatuses) {
    const sandwichCounts = {};
    
    for (const sandwich of orders) {
        sandwichCounts[sandwich] = (sandwichCounts[sandwich] || 0) + 1;
    }
    
    const availableTables = [];
    
    for (let i = 0; i < tableStatuses.length; i++) {
        if (tableStatuses[i] === 'available') {
            availableTables.push(i + 1);
        }
    }
}
```

> **💡 Array vs Real World:**
> - Array dimulai dari index 0
> - Nomor meja di resto dimulai dari 1
> - Solusi: `i + 1`

**Test:**
```javascript
const tables = ['occupied', 'available', 'available', 'occupied'];
processShopOrders([], tables);

console.log(availableTables);
// Output: [2, 3] ✅
```

---

## 📦 Part 3: Return Results

### Step 10: Return Object dengan Both Results

```javascript
function processShopOrders(orders, tableStatuses) {
    const sandwichCounts = {};
    
    for (const sandwich of orders) {
        sandwichCounts[sandwich] = (sandwichCounts[sandwich] || 0) + 1;
    }
    
    const availableTables = [];
    
    for (let i = 0; i < tableStatuses.length; i++) {
        if (tableStatuses[i] === 'available') {
            availableTables.push(i + 1);
        }
    }
    
    return {
        sandwichCounts: sandwichCounts,
        availableTables: availableTables
    };
}
```

**Final Test:**
```javascript
const orders = ['BLT', 'Club', 'BLT', 'Tuna', 'Club', 'BLT'];
const tables = ['occupied', 'available', 'available', 'occupied', 'available'];

const result = processShopOrders(orders, tables);
console.log(result);

// Output:
// {
//   sandwichCounts: { BLT: 3, Club: 2, Tuna: 1 },
//   availableTables: [2, 3, 5]
// }
// ✅ Perfect!
```

---

## 🚨 Common Mistakes

| ❌ SALAH | ✅ BENAR | 💡 Kenapa Salah |
|---------|---------|----------------|
| `sandwichCounts[sandwich]++` | `sandwichCounts[sandwich] = (sandwichCounts[sandwich] || 0) + 1` | `++` tidak bisa handle undefined |
| `availableTables.push(i)` | `availableTables.push(i + 1)` | Lupa convert dari 0-indexed |
| `if (tableStatuses[i] == 'available')` | `if (tableStatuses[i] === 'available')` | `==` bisa bikin bug type coercion |
| Return 2 variable terpisah | Return 1 object | Function hanya bisa return 1 value |
| `for (const table of tableStatuses)` | `for (let i = 0; i < tableStatuses.length; i++)` | for...of tidak kasih index |

---

## 📚 Quick Reference

### **Counting Pattern**
```javascript
const counts = {};
for (const item of array) {
    counts[item] = (counts[item] || 0) + 1;
}
```

### **Finding with Index**
```javascript
const results = [];
for (let i = 0; i < array.length; i++) {
    if (condition) {
        results.push(i + 1); // Convert to 1-indexed
    }
}
```

### **Multiple Returns**
```javascript
return {
    result1: value1,
    result2: value2
};
```

---

## ⚡ Visualisasi Flow

```
INPUT:
orders = ['BLT', 'Club', 'BLT']
tables = ['occupied', 'available', 'available']

STEP 1: Count Sandwiches
Loop 1: 'BLT'  → {BLT: 1}
Loop 2: 'Club' → {BLT: 1, Club: 1}
Loop 3: 'BLT'  → {BLT: 2, Club: 1}

STEP 2: Find Available Tables
Loop 1: i=0, 'occupied'  → skip
Loop 2: i=1, 'available' → push(2)
Loop 3: i=2, 'available' → push(3)

OUTPUT:
{
  sandwichCounts: {BLT: 2, Club: 1},
  availableTables: [2, 3]
}
```

---

## 🎓 Kapan Pakai Pattern Ini?

✅ **Gunakan saat:**
- Perlu count occurrences di array
- Perlu filter array tapi butuh position info
- Perlu return multiple hasil dari 1 function

❌ **Jangan pakai saat:**
- Data sudah terstruktur (misal: sudah ada count property)
- Bisa pakai `.filter()` tanpa butuh index
- Cuma butuh 1 hasil sederhana
