# 🐟 Tantangan Sorting Fish by Size

## 📋 Ringkasan Challenge
**Tingkat Kesulitan:** `Easy`

Buat sebuah function yang mengurutkan nama-nama ikan berdasarkan kategori ukuran alami mereka, dari yang terkecil hingga terbesar.

---

## 🎯 Tujuan
Implementasikan function bernama `sortFishBySize` yang mengorganisir array nama-nama ikan sesuai dengan hierarki ukuran mereka.

---

## 📏 Kategori Ukuran Fish

Sorting harus mengikuti urutan ukuran ini (ascending):

| Kategori Ukuran | Jenis Fish | Symbol |
|-----------------|------------|---------|
| **Small** | Sardine | 🐟 |
| **Medium** | Trout | 🐠 |
| **Large** | Salmon | 🎣 |
| **Extra Large** | Tuna | 🐋 |

---

## 🔧 Spesifikasi Function

### Function Signature
```javascript
function sortFishBySize(fishList)
```

### Parameter
- **`fishList`** *(array)*: Sebuah array berisi string nama-nama ikan
  - Nilai yang diterima: `"Sardine"`, `"Trout"`, `"Salmon"`, `"Tuna"`

### Return Value
- **Returns:** Array baru dengan nama-nama ikan yang diurutkan berdasarkan ukuran (small → extra large)

---

## 📝 Contoh Penggunaan

```javascript
// Contoh input
const fishArray = ["Tuna", "Sardine", "Salmon", "Trout"];

// Output yang diharapkan
const sortedFish = sortFishBySize(fishArray);
console.log(sortedFish);
// Output: ["Sardine", "Trout", "Salmon", "Tuna"]
```

---

## ✅ Ringkasan Requirements

- [x] Nama function harus tepat `sortFishBySize`
- [x] Menerima satu parameter: `fishList` (array)
- [x] Mengurutkan fish berdasarkan ukuran: Sardine → Trout → Salmon → Tuna
- [x] Mengembalikan array yang sudah diurutkan
- [x] Mempertahankan urutan ascending (terkecil ke terbesar)

---

## 🎪 Tag Challenge
`#Array` `#Sorting` `#String-Manipulation` `#Easy-Level`
