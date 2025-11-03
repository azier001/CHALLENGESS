# 🧺 Picnic Park Geometry Challenge

> **Tingkat Kesulitan:** `Hard` 🔴

---

## 📋 Deskripsi Challenge

Buat sebuah function bernama **`arrangePicnic`** yang mengatur item-item piknik (direpresentasikan sebagai bentuk geometris) pada grid 2D. Function ini menerapkan transformasi yang ditentukan ke setiap item dan mendeteksi overlapping (tumpang tindih) di antara mereka.

---

## 🎯 Function Signature

```javascript
function arrangePicnic(items, transformation)
```

### Parameters

| Parameter | Type | Deskripsi |
|-----------|------|-------------|
| `items` | `string[]` | Array of strings yang merepresentasikan item piknik dan dimensinya |
| `transformation` | `string` | String yang menentukan transformasi yang akan diterapkan ke semua item |

### Returns

- **Type:** `boolean[]`
- **Deskripsi:** Array yang menunjukkan apakah setiap item overlap dengan item lain setelah transformasi
- `true` = item overlap dengan setidaknya satu item lain
- `false` = item tidak overlap dengan item lain manapun

---

## 🔷 Supported Shapes

Function ini mendukung tiga bentuk geometris, masing-masing dengan parameter dimensi spesifik:

### 1. **Triangle**
```
Format: "triangle,side1,side2,side3"
Contoh: "triangle,3,4,5"
```
- Memerlukan tiga panjang sisi

### 2. **Circle**
```
Format: "circle,radius"
Contoh: "circle,5"
```
- Memerlukan satu nilai radius

### 3. **Rectangle**
```
Format: "rectangle,width,height"
Contoh: "rectangle,4,6"
```
- Memerlukan dimensi width dan height

---

## 🔄 Supported Transformations

Function ini mendukung dua jenis transformasi geometris:

### 1. **Rotation**
```
Format: "rotate,degrees"
Contoh: "rotate,90"
```
- Memutar shape sebesar sudut yang ditentukan (dalam derajat)

### 2. **Scaling**
```
Format: "scale,factor"
Contoh: "scale,2"
```
- Menskala shape dengan faktor yang ditentukan (mengalikan dimensi)

---

## ⚙️ Langkah-langkah Implementasi

1. **Parse Item Strings**
   - Ekstrak tipe shape dan dimensi dari setiap item string
   - Validasi format shape dan parameter

2. **Apply Transformation**
   - Terapkan transformasi yang ditentukan ke setiap item yang sudah di-parse
   - Update koordinat dan dimensi sesuai transformasi

3. **Detect Overlaps**
   - Bandingkan koordinat dan dimensi yang sudah ditransformasi dari semua item
   - Tentukan item mana yang overlap satu sama lain

4. **Return Results**
   - Generate boolean array yang menunjukkan status overlap untuk setiap item

---

## 💡 Contoh Penggunaan

```javascript
const items = [
  "triangle,3,4,5",
  "circle,5",
  "rectangle,4,6"
];

const transformation = "scale,2";

const result = arrangePicnic(items, transformation);
// Returns: [boolean, boolean, boolean]
```

---

## 🎓 Pertimbangan Penting

- ⚠️ Pastikan parsing item strings dilakukan dengan benar
- 🔍 Kalkulasi geometris yang akurat untuk deteksi overlap
- 📐 Penerapan transformasi yang benar (rotation/scaling)
- 🔢 Handle edge cases (input tidak valid, dimensi nol, dll.)
- 🎯 Algoritma efisien untuk membandingkan multiple items

---

## 🏆 Kriteria Sukses

Implementasi Anda harus:

✅ Mem-parse semua format shape yang didukung dengan benar  
✅ Menerapkan transformasi secara akurat  
✅ Mendeteksi overlap antara kombinasi shape apapun  
✅ Mengembalikan boolean array yang benar  
✅ Menangani edge cases dengan baik  

---

Semoga berhasil dengan implementasi Anda! 🚀
