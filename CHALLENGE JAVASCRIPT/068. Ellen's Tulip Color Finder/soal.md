# 🌷 Ellen's Tulip Color Finder

## 📋 Challenge Overview

**Difficulty Level:** `Easy`

Ellen sedang merawat kebun tulip berwarna-warni di sore hari yang cerah. Dia ingin mengidentifikasi warna tulip tertentu di kebunnya. Tugas Anda adalah membuat function yang akan membantu Ellen menemukan warna tulip pada posisi yang diberikan.

---

## 🎯 Objective

Buat function dengan nama `findTulipColor` yang menerima dua parameter dan membantu Ellen mengidentifikasi warna tulip di kebunnya.

### Function Signature
```javascript
function findTulipColor(garden, position)
```

---

## 📥 Parameters

| Parameter | Type | Deskripsi |
|-----------|------|-----------|
| `garden` | `Array<string>` | Array string yang merepresentasikan warna-warna tulip di kebun Ellen |
| `position` | `number` | Integer yang merepresentasikan posisi tulip yang ingin Ellen periksa (**1-based index**) |

---

## 📤 Return Value

Function mengembalikan **string** dengan salah satu hasil berikut:

### ✅ Posisi Valid
- Mengembalikan **warna** tulip pada posisi yang ditentukan

### ❌ Kasus Posisi Invalid
- **Position < 1:** `"Oh no! That's not a valid tulip position, Ellen!"`
- **Position > panjang garden:** `"Oops! Your garden isn't that big, Ellen!"`

---

## 📏 Aturan Validasi

> ⚠️ **Penting:** Posisi menggunakan **1-based indexing** (tulip pertama berada di posisi 1, bukan 0)

1. **Posisi terlalu rendah** (`position < 1`)
   - Return: `"Oh no! That's not a valid tulip position, Ellen!"`

2. **Posisi terlalu tinggi** (`position > garden.length`)
   - Return: `"Oops! Your garden isn't that big, Ellen!"`

3. **Posisi valid** (`1 ≤ position ≤ garden.length`)
   - Return: Warna tulip pada posisi tersebut

---

## 💡 Contoh Penggunaan

```javascript
// Contoh garden
const garden = ["red", "yellow", "pink", "purple", "white"];

// Test cases
findTulipColor(garden, 1);    // Returns: "red"
findTulipColor(garden, 3);    // Returns: "pink"
findTulipColor(garden, 0);    // Returns: "Oh no! That's not a valid tulip position, Ellen!"
findTulipColor(garden, 6);    // Returns: "Oops! Your garden isn't that big, Ellen!"
```

---

## 🧠 Poin Penting yang Perlu Diingat

- 🔢 **1-based indexing:** Posisi 1 sesuai dengan `garden[0]`
- 🌷 **Array garden:** Berisi warna tulip sebagai string
- ✅ **Validasi terlebih dahulu:** Selalu periksa validitas posisi sebelum mengakses array
- 📝 **Message yang tepat:** Gunakan pesan error yang ditentukan persis seperti yang tertulis

---

## 🎨 Representasi Visual

```
Kebun Ellen (1-based indexing):
Position:  1      2        3       4         5
Garden:  ["red", "yellow", "pink", "purple", "white"]
Index:     0      1        2       3         4
```

*Selamat coding! Bantu Ellen menemukan tulip-tulip cantiknya! 🌷*
