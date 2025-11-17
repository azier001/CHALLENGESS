# 📦 Moving Box Filter by Route Cities

## Tingkat Kesulitan
🔶 **Medium**

---

## 🎯 Tujuan

Buatlah function `filterItemsByRoute` yang memfilter item dari moving boxes berdasarkan nama kota dalam rute perjalanan ke barat. Function ini harus menyimpan hanya item yang namanya mengandung nama kota sebagai substring.

---

## 📋 Function Signature

```javascript
function filterItemsByRoute(cities, boxes)
```

### Parameters

| Parameter | Type | Deskripsi |
|-----------|------|-----------|
| `cities` | `Array<string>` | Array berisi nama-nama kota sepanjang rute perjalanan |
| `boxes` | `Array<Array<string>>` | Array 2D dimana setiap sub-array berisi nama-nama item |

### Returns

- **Type**: `Array<Array<string>>`
- **Format**: `[["item1", "item2"], ["item3"], []]`
- **Deskripsi**: Array 2D dengan struktur yang sama seperti input, berisi hanya item yang mengandung nama kota sebagai substring

---

## 🔍 Logika yang Diperlukan

Function harus mengikuti langkah-langkah berikut:

1. **Iterasi setiap box** (sub-array) dalam array `boxes`
2. **Periksa setiap nama item** dalam box saat ini
3. **Cek kecocokan substring** (case-insensitive):
   - Tentukan apakah nama item mengandung nama kota dari array `cities`
4. **Simpan item yang cocok** sambil mempertahankan struktur box asli
5. **Return array 2D yang sudah difilter** dengan jumlah box yang sama seperti input

---

## 💡 Poin Penting

- ✅ Pencocokan substring harus **case-insensitive**
- ✅ Pertahankan **struktur box asli** (jumlah box yang sama)
- ✅ Box kosong harus dipertahankan sebagai empty array `[]`
- ✅ Sebuah item cocok jika mengandung **setidaknya satu** nama kota sebagai substring

---

## 📝 Contoh Skenario

Bayangkan Anda sedang pindahan ke barat dan ingin menyimpan hanya item yang terkait dengan kota-kota di rute Anda:

```javascript
const cities = ["Denver", "Vegas", "Phoenix"];
const boxes = [
  ["Denver Broncos Jersey", "Random Book", "Vegas Dice"],
  ["Phoenix Poster", "Coffee Mug"],
  ["Laptop", "Phoenix T-shirt", "Denver Map"]
];

// Expected output:
[
  ["Denver Broncos Jersey", "Vegas Dice"],
  ["Phoenix Poster"],
  ["Phoenix T-shirt", "Denver Map"]
]
```

---

## 🚀 Memulai

Mulailah dengan mempertimbangkan:
- Bagaimana melakukan pencocokan substring yang case-insensitive
- Bagaimana mempertahankan struktur box bahkan ketika box menjadi kosong
- Cara efisien untuk mengecek beberapa nama kota terhadap setiap item

Semangat! 🎉
