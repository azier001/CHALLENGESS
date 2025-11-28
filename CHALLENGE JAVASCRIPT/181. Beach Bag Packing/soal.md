# 🏖️ Beach Bag Packing Challenge

<div align="center">

**Tingkat Kesulitan:** `Medium` 🌊

</div>

---

## 📋 Deskripsi Challenge

Buat sebuah function bernama `packBeachBag` yang mengelola daftar barang untuk perjalanan ke pantai dengan menggabungkan rekomendasi item, menghapus duplikat, dan menyesuaikan dengan kondisi cuaca.

---

## 🎯 Function Signature

```javascript
packBeachBag(initialItems, friendRecommendations, weatherCondition)
```

---

## 📝 Langkah-Langkah Implementasi

### Langkah 1️⃣: Gabungkan Daftar Item
Gabungkan `initialItems` dan `friendRecommendations` menjadi satu array.

### Langkah 2️⃣: Hapus Duplikat
Filter item yang duplikat, simpan hanya item yang unik.

### Langkah 3️⃣: Terapkan Logika Berdasarkan Cuaca
Sesuaikan daftar packing berdasarkan `weatherCondition`:

#### ☀️ **Cuaca Cerah (Sunny)**
- Tambahkan `"sunscreen"` jika belum ada dalam list

#### 💨 **Cuaca Berangin (Windy)**
- Pastikan `"hat"` ada dalam list

#### 🌧️ **Cuaca Hujan (Rainy)**
- Tambahkan `"umbrella"` ke dalam list
- Hapus item yang tidak tahan air:
  - `"camera"`
  - `"book"`

### Langkah 4️⃣: Urutkan Secara Alfabetis
Susun semua item secara alfabetis (A-Z).

### Langkah 5️⃣: Return List Final
Return array yang telah diproses dan diurutkan.

---

## 📥 Parameter

| Parameter | Type | Deskripsi |
|-----------|------|-----------|
| `initialItems` | `array` | Item yang awalnya direncanakan untuk dibawa |
| `friendRecommendations` | `array` | Item yang direkomendasikan oleh teman |
| `weatherCondition` | `string` | Kondisi cuaca: `"sunny"`, `"windy"`, atau `"rainy"` |

---

## 📤 Return Value

**Type:** `array`

Mengembalikan sorted array berisi string yang merepresentasikan list final item yang akan dibawa, disusun secara alfabetis.

---

## 💡 Contoh Penggunaan

```javascript
const initial = ["towel", "sunglasses", "book"];
const recommendations = ["water bottle", "sunglasses", "camera"];
const weather = "sunny";

const packedBag = packBeachBag(initial, recommendations, weather);
// Expected output: ["book", "camera", "sunglasses", "sunscreen", "towel", "water bottle"]
```

---

## ✅ Persyaratan Utama

- ✨ **Item unik saja** - tidak ada duplikat
- 🌤️ **Menyesuaikan cuaca** - beradaptasi dengan kondisi
- 🔤 **Terurut alfabetis** - mudah dibaca
- 🎒 **Filter pintar** - menghapus item yang tidak sesuai untuk cuaca hujan

---

<div align="center">

**Selamat Coding!** 🚀

</div>
