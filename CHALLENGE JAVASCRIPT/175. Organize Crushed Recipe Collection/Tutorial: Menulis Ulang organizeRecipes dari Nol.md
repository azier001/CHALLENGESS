# 📚 Tutorial: Menulis Ulang `organizeRecipes` dari Nol

> **Level: SIMPLE** | **Waktu: 10 menit** | **Untuk: Pemula**

---

## 🎯 Apa yang Akan Kita Buat?

Fungsi yang **mengelompokkan resep berdasarkan tipe** dan memberikan nilai default untuk `cookingTime` jika tidak ada.

**Input:**
```javascript
[
  { name: "Nasi Goreng", type: "main", cookingTime: 20 },
  { name: "Es Teh", type: "drink" },
  { name: "Rendang", type: "main", cookingTime: 120 }
]
```

**Output:**
```javascript
{
  main: ["Nasi Goreng", "Rendang"],
  drink: ["Es Teh"]
}
```

---

## 📋 Langkah 1: Setup Fungsi & Object Kosong

### ✍️ Code

```javascript
function organizeRecipes(recipes) {
  const result = {};
  
  return result;
}
```

### 🧪 Test

```javascript
const test1 = organizeRecipes([]);
console.log(test1);
```

### ✅ Expected Output
```javascript
{}
```

**Penjelasan:** Object `result` akan menyimpan semua tipe resep sebagai key, dan array nama resep sebagai value.

---

## 📋 Langkah 2: Loop Melalui Semua Resep

### ✍️ Code

```javascript
function organizeRecipes(recipes) {
  const result = {};
  
  for (const recipe of recipes) {
    // Akan kita isi di langkah berikutnya
  }
  
  return result;
}
```

### 🧪 Test

```javascript
const test2 = organizeRecipes([
  { name: "Nasi Goreng", type: "main", cookingTime: 20 }
]);
console.log(test2);
```

### ✅ Expected Output
```javascript
{}
```

**Penjelasan:** Loop `for...of` membaca setiap resep satu per satu. Sekarang masih kosong karena belum ada proses di dalam loop.

---

## 📋 Langkah 3: Set Default `cookingTime`

### ✍️ Code

```javascript
function organizeRecipes(recipes) {
  const result = {};
  
  for (const recipe of recipes) {
    if (recipe.cookingTime === undefined) {
      recipe.cookingTime = 30;
    }
  }
  
  return result;
}
```

### 🧪 Test

```javascript
const test3 = [
  { name: "Es Teh", type: "drink" }
];
organizeRecipes(test3);
console.log(test3[0].cookingTime);
```

### ✅ Expected Output
```javascript
30
```

**Penjelasan:** Jika `cookingTime` tidak ada (undefined), kita set menjadi 30 menit sebagai default.

---

## 📋 Langkah 4: Buat Array untuk Tipe Baru

### ✍️ Code

```javascript
function organizeRecipes(recipes) {
  const result = {};
  
  for (const recipe of recipes) {
    if (recipe.cookingTime === undefined) {
      recipe.cookingTime = 30;
    }
    
    if (!result[recipe.type]) {
      result[recipe.type] = [];
    }
  }
  
  return result;
}
```

### 🧪 Test

```javascript
const test4 = organizeRecipes([
  { name: "Nasi Goreng", type: "main", cookingTime: 20 },
  { name: "Es Teh", type: "drink" }
]);
console.log(test4);
```

### ✅ Expected Output
```javascript
{
  main: [],
  drink: []
}
```

**💡 WHY:** Kita perlu cek dulu apakah tipe sudah ada di `result`. Jika belum, buat array kosong. Tanpa ini, `push()` di langkah berikutnya akan error.

---

## 📋 Langkah 5: Masukkan Nama Resep ke Array

### ✍️ Code

```javascript
function organizeRecipes(recipes) {
  const result = {};
  
  for (const recipe of recipes) {
    if (recipe.cookingTime === undefined) {
      recipe.cookingTime = 30;
    }
    
    if (!result[recipe.type]) {
      result[recipe.type] = [];
    }
    
    result[recipe.type].push(recipe.name);
  }
  
  return result;
}
```

### 🧪 Test

```javascript
const test5 = organizeRecipes([
  { name: "Nasi Goreng", type: "main", cookingTime: 20 },
  { name: "Rendang", type: "main", cookingTime: 120 },
  { name: "Es Teh", type: "drink" }
]);
console.log(test5);
```

### ✅ Expected Output
```javascript
{
  main: ["Nasi Goreng", "Rendang"],
  drink: ["Es Teh"]
}
```

**Penjelasan:** `push()` menambahkan nama resep ke array yang sesuai dengan tipenya.

---

## ⚠️ Common Mistakes

### 1. Lupa Cek Array Sebelum Push

❌ **SALAH:**
```javascript
result[recipe.type].push(recipe.name);
// Error: Cannot read property 'push' of undefined
```

✅ **BENAR:**
```javascript
if (!result[recipe.type]) {
  result[recipe.type] = [];
}
result[recipe.type].push(recipe.name);
```

**Kenapa:** Jika tipe belum ada di object, maka `result[recipe.type]` bernilai `undefined`, dan kita tidak bisa push ke undefined.

---

### 2. Pakai `==` Instead of `===`

❌ **SALAH:**
```javascript
if (recipe.cookingTime == undefined) {
  // Ini juga true untuk null
}
```

✅ **BENAR:**
```javascript
if (recipe.cookingTime === undefined) {
  // Hanya true untuk undefined
}
```

**Kenapa:** Gunakan `===` untuk strict comparison. Dengan `==`, nilai `null` juga akan dianggap sama dengan `undefined`.

---

### 3. Modifikasi Data Original Tanpa Sadar

❌ **SALAH:**
```javascript
recipe.cookingTime = 30;
// Ini mengubah object asli di array recipes!
```

✅ **ALTERNATIF (jika tidak ingin ubah original):**
```javascript
const cookingTime = recipe.cookingTime ?? 30;
// Gunakan nilai ini tanpa modifikasi object asli
```

**Kenapa:** Kode original memang mengubah data input. Jika tidak diinginkan, gunakan operator `??` (nullish coalescing) untuk membuat nilai baru tanpa modifikasi.

---

## 🎴 Quick Reference Card

```javascript
// TEMPLATE DASAR
function organizeRecipes(recipes) {
  const result = {};                          // 1. Siapkan object hasil
  
  for (const recipe of recipes) {             // 2. Loop setiap resep
    
    if (recipe.cookingTime === undefined) {   // 3. Set default value
      recipe.cookingTime = 30;
    }
    
    if (!result[recipe.type]) {               // 4. Cek & buat array baru
      result[recipe.type] = [];
    }
    
    result[recipe.type].push(recipe.name);    // 5. Masukkan nama ke array
  }
  
  return result;                              // 6. Return hasil
}
```

### 📌 Konsep Kunci

| Konsep | Kegunaan |
|--------|----------|
| `const result = {}` | Membuat object kosong sebagai container |
| `for...of` | Loop melalui array |
| `recipe.cookingTime === undefined` | Cek apakah property tidak ada |
| `!result[recipe.type]` | Cek apakah key belum ada di object |
| `result[key] = []` | Membuat array baru di object |
| `.push()` | Menambahkan item ke array |

---

## 🎉 Selesai!

Kamu sekarang bisa:
- ✅ Mengelompokkan data array ke dalam object
- ✅ Memberikan nilai default untuk property yang hilang
- ✅ Membuat struktur data dinamis dengan loop

**Next Step:** Coba tambahkan fitur untuk mengurutkan nama resep secara alfabetis di setiap kategori!
