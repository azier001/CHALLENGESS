# 🥗 Weekly Protein Intake Calculator

## Challenge Overview

**Difficulty Level:** `Medium` 🟡

---

## 📋 Deskripsi

Buatlah function `calculateDailyProtein` yang memproses grid meal plan mingguan dan menghitung total kandungan protein untuk setiap hari dalam seminggu.

Function ini menganalisis meal plan 7 hari di mana setiap hari berisi hingga 4 meals, menghitung total protein harian dengan memperlakukan missing meals (direpresentasikan sebagai `-1`) sebagai 0 protein.

---

## 🎯 Function Requirements

### Function Signature

```javascript
function calculateDailyProtein(mealPlan)
```

### Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| `mealPlan` | `Array<Array<number>>` | Array 2D berukuran **7×4** di mana:<br>• Setiap **row** merepresentasikan satu hari (7 hari total)<br>• Setiap **column** merepresentasikan satu meal (4 meals per hari)<br>• Values adalah jumlah protein dalam gram<br>• `-1` menandakan tidak ada meal yang direncanakan |

### Returns

**Type:** `Array<number>`

Array berisi 7 integers yang merepresentasikan total asupan protein harian untuk setiap hari dalam seminggu.

**Format:** `[day1Total, day2Total, day3Total, day4Total, day5Total, day6Total, day7Total]`

---

## 🧠 Logic Breakdown

Function harus mengikuti langkah-langkah berikut:

1. **Iterasi setiap hari** (row) dalam meal plan
2. **Untuk setiap hari**, jumlahkan semua nilai protein meal dalam row tersebut
3. **Ganti semua nilai `-1`** dengan `0` sebelum menjumlahkan
4. **Simpan total harian** dan lanjutkan ke hari berikutnya
5. **Return array** dari semua 7 total harian

---

## 💡 Contoh

### Input

```javascript
const mealPlan = [
  [30, 25, -1, 40],  // Day 1
  [20, 30, 35, -1],  // Day 2
  [25, -1, 30, 35],  // Day 3
  [-1, 40, 25, 30],  // Day 4
  [35, 30, -1, 25],  // Day 5
  [30, 25, 40, -1],  // Day 6
  [20, -1, 35, 30]   // Day 7
];
```

### Output

```javascript
[95, 85, 90, 95, 90, 95, 85]
```

### Penjelasan

- **Day 1:** 30 + 25 + 0 + 40 = **95g**
- **Day 2:** 20 + 30 + 35 + 0 = **85g**
- **Day 3:** 25 + 0 + 30 + 35 = **90g**
- **Day 4:** 0 + 40 + 25 + 30 = **95g**
- **Day 5:** 35 + 30 + 0 + 25 = **90g**
- **Day 6:** 30 + 25 + 40 + 0 = **95g**
- **Day 7:** 20 + 0 + 35 + 30 = **85g**

---

## ✅ Poin Penting yang Harus Diingat

- ⚠️ Missing meals ditandai sebagai `-1` dan harus dihitung sebagai `0` protein
- 📊 Setiap hari memiliki tepat 4 slot meal (beberapa mungkin `-1`)
- 🔢 Input selalu berupa grid 7×4 (7 hari, 4 meals per hari)
- 📤 Return array dengan tepat 7 elemen (satu per hari)

---

## 🚀 Tips Implementasi

- Gunakan array methods seperti `map()` dan `reduce()` untuk kode yang lebih bersih
- Handle nilai `-1` dengan menggantinya dengan `0` selama penjumlahan
- Pertimbangkan menggunakan conditional logic atau `Math.max()` untuk handle nilai negatif
- Test edge cases di mana semua meals adalah `-1` untuk hari tertentu

---

**Selamat mengerjakan implementasinya!** 💪
