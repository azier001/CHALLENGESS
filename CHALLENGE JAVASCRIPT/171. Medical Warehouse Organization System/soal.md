# 🏥 Sistem Organisasi Warehouse Medis Challenge

**Level:** `Medium` | **Kategori:** `Data Structure & Algorithm`

---

## 📌 Pernyataan Masalah

Desain dan implementasikan sebuah function `organizeWarehouse` yang memproses data inventory supply medis. Function ini harus mengorganisir supplies ke dalam laporan warehouse management yang efisien dengan mengelompokkan items berdasarkan type, mengurutkan berdasarkan lot numbers, dan menghasilkan formatted storage labels dengan shelf positions.

---

## 🎯 Objektif

Buat sistem organisasi warehouse yang komprehensif untuk mengubah data supply mentah menjadi laporan terstruktur dan actionable untuk inventory management dan shelf positioning.

---

## 🔍 Logika Pemrosesan

Function harus mengeksekusi operasi-operasi berikut secara berurutan:

1. **Kelompokkan supplies berdasarkan type** — Kumpulkan semua items ke dalam kategori berdasarkan property `type`
2. **Urutkan dalam group** — Atur items dalam setiap group berdasarkan `lotNumber` dalam urutan ascending
3. **Hitung metrics** — Untuk setiap type group:
   - Jumlahkan semua units untuk mendapatkan `totalUnits`
   - Tetapkan nilai `shelfPosition` secara sequential (dimulai dari 1)
4. **Generate labels** — Buat formatted labels sebagai `TYPE_LOTNUMBER`:
   - Konversi type ke UPPERCASE
   - Append lot number
5. **Build report** — Kombinasikan semua informasi ke dalam structure return object

---

## 📊 Function Signature

```javascript
function organizeWarehouse(supplies) {
  // Implementasi di sini
}
```

---

## 📥 Input: Parameter `supplies`

**Type:** Array of Objects

**Structure Object:**
```javascript
{
  name: String,        // Nama display dari supply item
  type: String,        // Kategori/klasifikasi supply
  lotNumber: Number,   // Lot identifier (nomor tracking unik)
  units: Number        // Jumlah dalam inventory
}
```

**Contoh Input:**
```javascript
[
  { name: "Amitriptyline", type: "tricyclic_antidepressant", lotNumber: 89, units: 75 },
  { name: "Nortriptyline", type: "tricyclic_antidepressant", lotNumber: 92, units: 75 },
  { name: "Penicillin", type: "antibiotic", lotNumber: 45, units: 100 },
  { name: "Amoxicillin", type: "antibiotic", lotNumber: 67, units: 100 }
]
```

---

## 📤 Output: Return Value

**Type:** Object (Dictionary/Map)

**Structure:**
- **Key:** Nama type (string) dari supplies
- **Value:** Object yang berisi:
  - `totalUnits` (Number) — Jumlah total units untuk type ini
  - `shelfPosition` (Number) — Sequential position assignment (1, 2, 3, ...)
  - `labels` (Array) — Formatted storage labels untuk setiap lot

**Contoh Output:**
```javascript
{
  "tricyclic_antidepressant": {
    "totalUnits": 150,
    "shelfPosition": 1,
    "labels": [
      "TRICYCLIC_ANTIDEPRESSANT_LOT89",
      "TRICYCLIC_ANTIDEPRESSANT_LOT92"
    ]
  },
  "antibiotic": {
    "totalUnits": 200,
    "shelfPosition": 2,
    "labels": [
      "ANTIBIOTIC_LOT45",
      "ANTIBIOTIC_LOT67"
    ]
  }
}
```

---

## ✅ Daftar Requirement

- [ ] Kelompokkan items berdasarkan property `type`
- [ ] Urutkan lot numbers secara ascending numerik (bukan lexicographic)
- [ ] Hitung total units yang benar per type group
- [ ] Tetapkan shelf positions secara sequential dimulai dari 1
- [ ] Format labels sebagai `TYPE_LOTNUMBER` dengan type uppercase
- [ ] Return object terstruktur dengan ketiga field yang diperlukan
- [ ] Handle edge cases (empty arrays, single items, duplicate types)

---

## 💭 Pertimbangan Implementasi

| Aspek | Catatan |
|-------|---------|
| **Grouping** | Gunakan `reduce()`, `Object.groupBy()`, atau method serupa untuk organize berdasarkan type |
| **Sorting** | Urutkan secara numerik (gunakan `(a, b) => a - b`), bukan alphabetically |
| **Type Case** | Konversi semua type names ke UPPERCASE hanya untuk labels |
| **Shelf Order** | Pertahankan urutan type sesuai kemunculannya pertama kali dalam grouped data |
| **Label Format** | Kombinasikan uppercase type + `_LOT` + lot number (e.g., `ANTIBIOTIC_LOT45`) |

---

## 🧪 Contoh Test Case

**Input:**
```javascript
const supplies = [
  { name: "Imipramine", type: "tricyclic_antidepressant", lotNumber: 92, units: 60 },
  { name: "Doxepin", type: "tricyclic_antidepressant", lotNumber: 89, units: 90 },
  { name: "Cephalexin", type: "antibiotic", lotNumber: 67, units: 150 },
  { name: "Ciprofloxacin", type: "antibiotic", lotNumber: 45, units: 100 }
];

organizeWarehouse(supplies);
```

**Expected Output:**
```javascript
{
  "tricyclic_antidepressant": {
    "totalUnits": 150,
    "shelfPosition": 1,
    "labels": [
      "TRICYCLIC_ANTIDEPRESSANT_LOT89",
      "TRICYCLIC_ANTIDEPRESSANT_LOT92"
    ]
  },
  "antibiotic": {
    "totalUnits": 250,
    "shelfPosition": 2,
    "labels": [
      "ANTIBIOTIC_LOT45",
      "ANTIBIOTIC_LOT67"
    ]
  }
}
```

---

## 🚀 Bonus Challenges

- Handle duplicate lot numbers dalam type yang sama
- Tambahkan validation untuk missing atau invalid properties
- Implementasikan maximum shelf capacity constraints
- Tambahkan filtering capability untuk specific supply types
