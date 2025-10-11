# 🍎 Splendiferous Fruit Basket Checker

## Gambaran Challenge

**Tingkat Kesulitan:** `Easy`

Buat sebuah function yang menentukan apakah sebuah fruit basket memenuhi kualifikasi sebagai "splendiferous" berdasarkan kriteria validasi tertentu.

---

## 📋 Deskripsi Challenge

Tugas Anda adalah membuat function bernama `fruitBasketChecker` yang memvalidasi fruit basket sesuai aturan spesifik. Function ini harus memeriksa beberapa kondisi untuk menentukan apakah sebuah basket memenuhi standar "splendiferous".

---

## ✨ Apa yang Membuat Basket Splendiferous?

Sebuah fruit basket dianggap **splendiferous** ketika **SEMUA** kondisi berikut terpenuhi:

1. ✅ **Nama Buah Valid**  
   Nama buah hanya boleh mengandung huruf dan spasi (tidak boleh angka atau karakter khusus)

2. 🧃 **Buah Juicy**  
   Buah tersebut harus salah satu dari varietas juicy berikut:
   - Apple
   - Orange
   - Pear
   - Peach
   - Watermelon

3. 🔢 **Quantity Valid**  
   Quantity harus berada di antara **1 dan 100** (inklusif)

---

## 🛠️ Langkah-langkah Implementasi

Ikuti langkah-langkah berikut untuk membangun solusi Anda:

| Langkah | Aksi | Deskripsi |
|---------|------|-----------|
| 1 | **Validasi Nama** | Gunakan regular expression untuk memeriksa apakah nama buah hanya mengandung huruf dan spasi |
| 2 | **Normalisasi Input** | Konversi nama buah ke lowercase untuk memudahkan perbandingan |
| 3 | **Periksa Juiciness** | Verifikasi apakah buah ada dalam daftar buah juicy |
| 4 | **Validasi Quantity** | Pastikan quantity berada dalam rentang valid (1-100) |
| 5 | **Gabungkan Kondisi** | Gunakan logical operator untuk memeriksa apakah semua kondisi terpenuhi |
| 6 | **Return Hasil** | Return message yang sesuai berdasarkan hasil validasi |

---

## 📥 Parameter Function

### `fruitBasketChecker(fruitName, quantity)`

| Parameter | Type | Deskripsi |
|-----------|------|-----------|
| `fruitName` | `string` | Nama buah yang akan diperiksa |
| `quantity` | `number` | Jumlah buah dalam basket |

---

## 📤 Return Value

Function harus me-return sebuah **string message** yang menunjukkan apakah fruit basket splendiferous atau tidak.

> **Catatan:** Format message yang tepat harus ditentukan berdasarkan hasil validasi.

---

## 💡 Petunjuk

- Regular expression dapat membantu memvalidasi pola string
- Array method dapat memeriksa apakah sebuah nilai ada dalam list
- Comparison operator dapat memvalidasi rentang numerik
- Logical AND (`&&`) memastikan semua kondisi bernilai true

---

## 🎯 Contoh Penggunaan

```javascript
fruitBasketChecker("Apple", 50)
// Harus memeriksa: nama valid ✓, buah juicy ✓, quantity valid ✓

fruitBasketChecker("Banana", 10)
// Harus gagal: bukan buah juicy ✗

fruitBasketChecker("Orange123", 20)
// Harus gagal: nama tidak valid (mengandung angka) ✗

fruitBasketChecker("Watermelon", 150)
// Harus gagal: quantity melebihi maksimum ✗
```

---

## 🏁 Memulai

Mulailah dengan mendefinisikan struktur function Anda dan mengimplementasikan setiap langkah validasi secara sistematis. Ingat untuk menguji function Anda dengan berbagai input untuk memastikan semua kondisi bekerja dengan benar!

```javascript
function fruitBasketChecker(fruitName, quantity) {
  // Implementasi Anda di sini
}
```

Semangat! 🍊🍑🍐
