# 🧺 Tantangan Inventori Keranjang Piknik

## 📋 Gambaran Umum Tantangan
**Tingkat Kesulitan:** `Mudah` 🟢  
**Topik:** Manipulasi String & Loop  
**Estimasi Waktu:** 10-15 menit

---

## 🎯 Apa yang Akan Dipelajari
- Bekerja dengan penggabungan string
- Menggunakan loop untuk menghasilkan data berurutan
- Menangani parameter fungsi
- Formatting dan pemisahan string

---

## 📝 Deskripsi Masalah

Bayangkan kamu sedang mengorganisir piknik dan perlu melacak barang-barang di keranjang! Kamu sudah memiliki beberapa barang, tetapi ingin menambahkan lebih banyak barang dengan penamaan yang sistematis.

Tugasmu adalah membuat fungsi bernama `preparePicnicBasket` yang:
- Menerima barang-barang keranjang saat ini
- Menambahkan sejumlah barang baru yang ditentukan
- Mengembalikan daftar inventori lengkap

---

## 🔧 Spesifikasi Fungsi

### Function Signature
```javascript
function preparePicnicBasket(currentItems, itemsToAdd)
```

### Parameter
| Parameter | Type | Deskripsi |
|-----------|------|-----------|
| `currentItems` | `string` | Barang-barang yang saat ini ada di keranjang, dipisahkan dengan `", "` |
| `itemsToAdd` | `number` | Jumlah barang tambahan yang akan ditambahkan ke keranjang |

### Return Value
- **Type:** `string`
- **Format:** Semua barang dipisahkan dengan `", "` (koma + spasi)

---

## 🎯 Checklist Persyaratan

- [ ] Buat fungsi bernama `preparePicnicBasket`
- [ ] Terima dua parameter: `currentItems` dan `itemsToAdd`
- [ ] Gunakan **loop** untuk menghasilkan barang baru
- [ ] Barang baru harus mengikuti pola: `"item1"`, `"item2"`, `"item3"`, dll.
- [ ] Gabungkan barang saat ini dengan barang baru
- [ ] Return semua sebagai string tunggal dengan pemisah koma-spasi yang tepat

---

## 💡 Contoh Langkah Demi Langkah

### 📥 Input
```javascript
currentItems = "apel, pisang, sandwich"
itemsToAdd = 3
```

### 🔄 Proses
1. Mulai dengan barang yang ada: `"apel, pisang, sandwich"`
2. Tambahkan `item1` → `"apel, pisang, sandwich, item1"`
3. Tambahkan `item2` → `"apel, pisang, sandwich, item1, item2"`
4. Tambahkan `item3` → `"apel, pisang, sandwich, item1, item2, item3"`

### 📤 Output yang Diharapkan
```javascript
"apel, pisang, sandwich, item1, item2, item3"
```

---

## 🧪 Test Cases

### Test Case 1: Penambahan Dasar
```javascript
Input: currentItems = "air, keripik", itemsToAdd = 2
Expected: "air, keripik, item1, item2"
```

### Test Case 2: Keranjang Kosong
```javascript
Input: currentItems = "", itemsToAdd = 3
Expected: "item1, item2, item3"
```

### Test Case 3: Tidak Ada Barang Baru
```javascript
Input: currentItems = "apel, jeruk", itemsToAdd = 0
Expected: "apel, jeruk"
```

---

## 🛠️ Petunjuk Implementasi

### Untuk Pemula:
1. **Mulai Sederhana:** Pertama, pahami cara menggabungkan dua string
2. **Gunakan Loop:** Pikirkan tentang loop `for` - mereka sempurna untuk menghitung!
3. **Membangun String:** Pertimbangkan cara membangun hasil string langkah demi langkah
4. **Edge Cases:** Apa yang terjadi jika `itemsToAdd` adalah 0? Bagaimana jika `currentItems` kosong?

### Konsep Kunci yang Perlu Diingat:
- **String Concatenation:** Menggabungkan string bersama-sama
- **Loop Iteration:** Mengulangi kode sejumlah kali tertentu
- **Template Literals:** Menggunakan backticks untuk string dinamis (opsional tapi membantu)

---

## 🎨 Template Struktur Kode

```javascript
function preparePicnicBasket(currentItems, itemsToAdd) {
    // Kode Anda di sini
    // 1. Tangani barang-barang saat ini
    // 2. Gunakan loop untuk menambahkan barang baru
    // 3. Return inventori keranjang lengkap
}
```

---

## 🏆 Kriteria Keberhasilan

Solusi Anda harus:
- ✅ Lulus semua test cases
- ✅ Menggunakan struktur loop
- ✅ Menangani edge cases dengan baik
- ✅ Mengembalikan string yang diformat dengan benar
- ✅ Mengikuti konvensi penamaan yang tepat untuk barang baru

---

## 🚀 Siap untuk Coding?

Sekarang setelah kamu memahami persyaratannya, saatnya untuk mengimplementasikan solusimu! Ingat untuk menguji fungsimu dengan input yang berbeda untuk memastikan berfungsi dengan benar.

Semoga berhasil dengan sistem inventori keranjang piknikmu! 🎉
