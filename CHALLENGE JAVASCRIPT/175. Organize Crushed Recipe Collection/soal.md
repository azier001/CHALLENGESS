# 📚 Organize Crushed Recipe Collection

## Ringkasan Challenge

**Tingkat Kesulitan:** `Easy` 🟢

Koleksi resep kesayangan nenek Anda telah rusak dan perlu diorganisir! Bantu memulihkan keteraturan dengan membuat sistem yang mengelompokkan resep berdasarkan tipe dan memastikan semua resep memiliki waktu memasak yang tepat.

---

## 🎯 Tujuan

Buat function bernama `organizeRecipes` yang memproses koleksi resep dan mengorganisirnya ke dalam format terstruktur berdasarkan tipe resep.

---

## 📋 Spesifikasi Function

### Nama Function
```javascript
organizeRecipes(recipes)
```

### Parameters

| Parameter | Type | Deskripsi |
|-----------|------|-------------|
| `recipes` | `Array<Object>` | Array berisi object resep yang memuat informasi resep |

#### Struktur Recipe Object

Setiap object resep berisi property berikut:

- **`name`** *(string)* - Nama resep
- **`type`** *(string)* - Kategori/tipe resep (contoh: "dessert", "main", "appetizer")
- **`cookingTime`** *(number, optional)* - Waktu memasak dalam menit

---

## 🔄 Aturan Pemrosesan

Function harus melakukan dua operasi utama:

1. **Set Default Cooking Time**: Jika resep tidak memiliki property `cookingTime`, secara otomatis set nilainya menjadi **30 menit**
2. **Group by Type**: Organisir resep berdasarkan `type`, mengumpulkan semua nama resep di bawah setiap kategori

---

## 📤 Return Value

**Type:** `Object`

Return sebuah object di mana:
- **Keys** adalah tipe resep (strings)
- **Values** adalah array nama resep (array of strings)

### Contoh Return Format

```javascript
{
  "dessert": ["Chocolate Cake", "Apple Pie"],
  "main": ["Beef Stew"],
  "appetizer": ["Caesar Salad"]
}
```

---

## 💡 Contoh Penggunaan

### Input
```javascript
const recipes = [
  { name: "Chocolate Cake", type: "dessert", cookingTime: 45 },
  { name: "Apple Pie", type: "dessert" },
  { name: "Beef Stew", type: "main", cookingTime: 120 },
  { name: "Caesar Salad", type: "appetizer" }
];

organizeRecipes(recipes);
```

### Expected Output
```javascript
{
  "dessert": ["Chocolate Cake", "Apple Pie"],
  "main": ["Beef Stew"],
  "appetizer": ["Caesar Salad"]
}
```

> **Catatan:** "Apple Pie" dan "Caesar Salad" tidak memiliki waktu memasak, yang secara otomatis di-set menjadi 30 menit selama pemrosesan (meskipun ini tidak mempengaruhi struktur output).

---

## ✅ Persyaratan Utama

- ✓ Menangani resep dengan nilai `cookingTime` yang hilang
- ✓ Mengelompokkan resep berdasarkan property `type`
- ✓ Mempertahankan semua nama resep dalam array tipe masing-masing
- ✓ Return object yang terstruktur dengan benar

---

## 🚀 Memulai

Pertimbangkan hal berikut:
1. Bagaimana cara melakukan iterasi melalui array resep
2. Bagaimana cara memeriksa property yang hilang dan set default
3. Bagaimana cara membangun dan mengisi result object secara dinamis
4. Pendekatan struktur data terbaik untuk mengelompokkan item

Semoga berhasil mengorganisir koleksi resep! 👩‍🍳👨‍🍳
