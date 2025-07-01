# 🥪 Two-Decker Sandwich Maker

## 📋 Challenge Overview
**Difficulty:** Easy  
**Goal:** Create a function that validates and builds a two-decker sandwich!

---

## 🎯 Problem Description

Kita akan membuat sebuah function bernama `makeSandwich` yang bertugas untuk:
- ✅ Memvalidasi bahan-bahan sandwich
- 🥪 Membuat sandwich jika semua kriteria terpenuhi
- ❌ Memberikan pesan error jika ada yang salah

---

## 📝 Rules & Requirements

### 🍞 **Bread Rules**
- Top bread harus: `"white"` atau `"wheat"`
- Bottom bread harus: `"white"` atau `"wheat"`
- **PENTING:** Kedua roti harus sama jenisnya!

### 🧀 **Filling Rules** 
Filling yang diperbolehkan:
- `"cheese"` 🧀
- `"ham"` 🥓  
- `"lettuce"` 🥬

### 📤 **Return Messages**
| Kondisi | Return Message |
|---------|----------------|
| ✅ Semua benar | `"Delicious [filling] sandwich on [bread type] bread!"` |
| ❌ Roti tidak sama | `"Mismatched bread types!"` |
| ❌ Jenis roti salah | `"Invalid bread type!"` |
| ❌ Filling salah | `"Invalid filling!"` |

---

## 💻 Solution Code

```javascript
function makeSandwich(topBread, filling, bottomBread) {
    // Array untuk menyimpan jenis roti dan filling yang valid
    const validBreads = ["white", "wheat"];
    const validFillings = ["cheese", "ham", "lettuce"];
    
    // Cek apakah jenis roti valid
    if (!validBreads.includes(topBread) || !validBreads.includes(bottomBread)) {
        return "Invalid bread type!";
    }
    
    // Cek apakah filling valid
    if (!validFillings.includes(filling)) {
        return "Invalid filling!";
    }
    
    // Cek apakah kedua roti sama jenisnya
    if (topBread !== bottomBread) {
        return "Mismatched bread types!";
    }
    
    // Jika semua kondisi terpenuhi, buat sandwich!
    return `Delicious ${filling} sandwich on ${topBread} bread!`;
}
```

---

## 🧠 Step-by-Step Explanation

### Step 1: Define Valid Options
```javascript
const validBreads = ["white", "wheat"];
const validFillings = ["cheese", "ham", "lettuce"];
```
- Kita buat array untuk menyimpan pilihan yang valid
- Ini memudahkan kita untuk mengecek validitas input

### Step 2: Validate Bread Types
```javascript
if (!validBreads.includes(topBread) || !validBreads.includes(bottomBread)) {
    return "Invalid bread type!";
}
```
- `includes()` method mengecek apakah nilai ada dalam array
- `!` artinya "tidak" - jadi kita cek apakah roti TIDAK valid
- `||` artinya "atau" - jika salah satu roti tidak valid, return error

### Step 3: Validate Filling
```javascript
if (!validFillings.includes(filling)) {
    return "Invalid filling!";
}
```
- Mirip dengan validasi roti, tapi untuk filling
- Jika filling tidak ada dalam list yang valid, return error

### Step 4: Check Bread Match
```javascript
if (topBread !== bottomBread) {
    return "Mismatched bread types!";
}
```
- `!==` artinya "tidak sama dengan"
- Jika kedua roti berbeda, return error

### Step 5: Success Case
```javascript
return `Delicious ${filling} sandwich on ${topBread} bread!`;
```
- Jika semua validasi berhasil, buat pesan sukses
- Menggunakan template literal (`${}`) untuk memasukkan variabel ke dalam string

---

## 🧪 Test Cases

```javascript
// ✅ Valid Cases
console.log(makeSandwich("white", "cheese", "white"));
// Output: "Delicious cheese sandwich on white bread!"

console.log(makeSandwich("wheat", "ham", "wheat"));
// Output: "Delicious ham sandwich on wheat bread!"

// ❌ Invalid Cases
console.log(makeSandwich("white", "cheese", "wheat"));
// Output: "Mismatched bread types!"

console.log(makeSandwich("rye", "cheese", "rye"));
// Output: "Invalid bread type!"

console.log(makeSandwich("white", "turkey", "white"));
// Output: "Invalid filling!"
```

---

## 🔍 Key Programming Concepts

### 1. **Array Methods**
- `includes()`: Mengecek apakah nilai ada dalam array
- Sangat berguna untuk validasi input

### 2. **Conditional Logic**
- `if-else` statements untuk menangani berbagai kondisi
- Urutan pengecekan penting (bread type → filling → bread match)

### 3. **Template Literals**
- Menggunakan backticks (\`) dan `${}` untuk string interpolation
- Lebih mudah dibaca daripada string concatenation

### 4. **Logical Operators**
- `||` (OR): Salah satu kondisi true = hasil true
- `!` (NOT): Membalik nilai boolean
- `!==` (Strict inequality): Tidak sama dengan (type dan value)

---

## 💡 Tips untuk Pemula

1. **Selalu validasi input terlebih dahulu** sebelum memproses data
2. **Gunakan array untuk menyimpan pilihan valid** - lebih mudah maintenance
3. **Urutan pengecekan matters** - cek yang paling fundamental dulu
4. **Gunakan descriptive variable names** agar code mudah dibaca
5. **Test dengan berbagai skenario** - valid dan invalid cases

---

## 🚀 Alternative Solutions

### Versi dengan Switch Statement
```javascript
function makeSandwichSwitch(topBread, filling, bottomBread) {
    // Validasi bread types
    if (!["white", "wheat"].includes(topBread) || 
        !["white", "wheat"].includes(bottomBread)) {
        return "Invalid bread type!";
    }
    
    // Validasi filling dengan switch
    switch (filling) {
        case "cheese":
        case "ham":
        case "lettuce":
            break;
        default:
            return "Invalid filling!";
    }
    
    // Cek bread match
    if (topBread !== bottomBread) {
        return "Mismatched bread types!";
    }
    
    return `Delicious ${filling} sandwich on ${topBread} bread!`;
}
```

### Versi dengan Object Validation
```javascript
function makeSandwichObject(topBread, filling, bottomBread) {
    const validIngredients = {
        breads: new Set(["white", "wheat"]),
        fillings: new Set(["cheese", "ham", "lettuce"])
    };
    
    if (!validIngredients.breads.has(topBread) || 
        !validIngredients.breads.has(bottomBread)) {
        return "Invalid bread type!";
    }
    
    if (!validIngredients.fillings.has(filling)) {
        return "Invalid filling!";
    }
    
    if (topBread !== bottomBread) {
        return "Mismatched bread types!";
    }
    
    return `Delicious ${filling} sandwich on ${topBread} bread!`;
}
```
