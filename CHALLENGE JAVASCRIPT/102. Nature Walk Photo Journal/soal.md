# 🌲 Nature Walk Photo Journal

## 📸 Deskripsi Challenge

**Tingkat Kesulitan:** `Easy` 🟢

Buatlah sebuah function yang membantu mengorganisir koleksi foto alam dengan mengkategorikan foto berdasarkan tag lingkungannya.

---

## 🎯 Tujuan

Kembangkan function bernama `organizePhotos` yang secara efisien mengurutkan dan mengelompokkan foto-foto alam sesuai dengan tag lokasinya, sehingga memudahkan untuk menjelajahi koleksi berdasarkan environment tertentu.

---

## 📋 Spesifikasi Function

### Nama Function
```javascript
organizePhotos(tags, photos)
```

### Parameter

| Parameter | Type | Deskripsi |
|-----------|------|-----------|
| `tags` | Array of Strings | Berisi tag environment untuk setiap foto |
| `photos` | Array of Strings | Berisi nama file foto yang sesuai |

> **Catatan:** Foto pada index `i` di array `photos` sesuai dengan tag pada index `i` di array `tags`.

### Tag yang Diharapkan
- 🌲 `'forest'` - Lingkungan hutan dan pepohonan
- 🏞️ `'lake'` - Pemandangan danau atau badan air besar
- 🪷 `'pond'` - Lingkungan kolam atau badan air kecil

---

## ✅ Requirements

Function harus:

1. **Memproses Input Array**: Menerima dua array dengan panjang yang sama berisi tags dan nama foto
2. **Mengelompokkan berdasarkan Tags**: Membuat kategori berdasarkan tag environment yang unik
3. **Mengembalikan Data Terorganisir**: Menghasilkan struktur dictionary/object dimana:
   - **Keys** = Tag unik dari input
   - **Values** = Array nama foto yang terkait dengan setiap tag

---

## 📤 Output yang Diharapkan

Function mengembalikan sebuah **Object** (dictionary) dengan struktur berikut:

```javascript
{
  "forest": ["photo1.jpg", "photo3.jpg"],
  "lake": ["photo2.jpg", "photo5.jpg"],
  "pond": ["photo4.jpg"]
}
```

---

## 💡 Contoh Penggunaan

```javascript
// Input arrays
const tags = ['forest', 'lake', 'forest', 'pond', 'lake'];
const photos = ['sunrise_trees.jpg', 'lake_reflection.jpg', 'autumn_path.jpg', 'lily_pond.jpg', 'sunset_water.jpg'];

// Function call
const organized = organizePhotos(tags, photos);

// Expected result
console.log(organized);
/*
{
  "forest": ["sunrise_trees.jpg", "autumn_path.jpg"],
  "lake": ["lake_reflection.jpg", "sunset_water.jpg"], 
  "pond": ["lily_pond.jpg"]
}
*/
```

---

## 🏆 Kriteria Sukses

- ✅ Function dengan benar mengelompokkan foto berdasarkan tag yang sesuai
- ✅ Semua tag unik muncul sebagai keys di object hasil
- ✅ Array foto berisi nama file yang benar untuk setiap tag
- ✅ Tidak ada foto yang hilang atau terduplikasi dalam proses pengorganisasian

---

*Selamat coding dan selamat mengorganisir koleksi foto alam Anda! 📷🌿*
