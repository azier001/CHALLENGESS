# 🌿 Organic Ingredient Extractor

## 📋 Gambaran Challenge

**Tingkat Kesulitan:** `Easy`

Buat sebuah function yang memfilter dan mengekstrak organic ingredients dari daftar ingredients yang diberikan.

---

## 🎯 Tujuan

Implementasikan function bernama `getOrganicIngredients` yang memproses string ingredients dan mengembalikan hanya yang ditandai sebagai organic.

## 📝 Spesifikasi Function

### Nama Function
```javascript
getOrganicIngredients(ingredientsList)
```

### Parameter

| Parameter | Type | Deskripsi |
|-----------|------|-----------|
| `ingredientsList` | `string` | Daftar ingredients yang dipisahkan dengan koma dan spasi |

### Return Value

- **Type:** `string`
- **Deskripsi:** Organic ingredients yang dipisahkan dengan koma dan spasi
- **Edge Case:** Mengembalikan string kosong jika tidak ada organic ingredients

---

## 🔍 Requirements

### ✅ Core Logic

1. **Split** string `ingredientsList` menjadi array
2. **Filter** ingredients yang dimulai dengan "organic"
3. **Kumpulkan** ingredients yang cocok ke dalam array baru
4. **Join** hasil dengan separator koma dan spasi
5. **Return** string final

### 📋 Format Input/Output

- **Format Input:** `"ingredient1, ingredient2, organic ingredient3, ..."`
- **Format Output:** `"organic ingredient3, organic ingredient4, ..."`
- **Hasil Kosong:** `""` (empty string)

---

## 💡 Implementation Hints

- Gunakan string methods seperti `split()` untuk mengkonversi string ke array
- Periksa apakah setiap ingredient dimulai dengan kata "organic"
- Pertimbangkan case sensitivity ketika memeriksa prefix "organic"
- Gunakan array methods untuk filter dan join hasil
- Handle edge cases dimana tidak ada organic ingredients

---

## 🧪 Contoh Test Cases

```javascript
// Contoh 1: Mixed ingredients
getOrganicIngredients("flour, organic tomatoes, sugar, organic lettuce")
// Expected: "organic tomatoes, organic lettuce"

// Contoh 2: Tidak ada organic ingredients
getOrganicIngredients("flour, sugar, salt")
// Expected: ""

// Contoh 3: Semua organic ingredients
getOrganicIngredients("organic flour, organic sugar, organic salt")
// Expected: "organic flour, organic sugar, organic salt"
```

---

## 🏆 Kriteria Sukses

Function Anda harus:
- ✅ Mengidentifikasi dengan benar ingredients yang dimulai dengan "organic"
- ✅ Mempertahankan format asli dari organic ingredients
- ✅ Mengembalikan hasil dalam format yang ditentukan
- ✅ Menangani hasil kosong dengan baik
- ✅ Memproses input string dengan akurat

---

*Selamat coding! 🚀*
