# 🏖️ Reversing Beach Day Memories

## 📋 Gambaran Challenge

**Tingkat Kesulitan:** `Easy`

Buat sebuah function yang membalikkan urutan elemen array dan karakter string, mensimulasikan proses mengingat kembali kenangan hari di pantai secara terbalik.

---

## 🎯 Tujuan

Implementasikan sebuah function bernama `reverseBeachDay` yang menerima array items dan sebuah phrase, kemudian mengembalikan keduanya dalam urutan terbalik.

---

## 📝 Spesifikasi Function

### Nama Function
```javascript
reverseBeachDay(items, phrase)
```

### Parameter

| Parameter | Type | Deskripsi | Batasan |
|-----------|------|-----------|---------|
| `items` | `Array<string>` | Array string yang merepresentasikan barang-barang hari pantai | 1-10 items, setiap item 1-100 karakter |
| `phrase` | `string` | String yang merepresentasikan kalimat hari pantai | 1-100 karakter |

### Return Value

**Type:** `Array`

**Struktur:** `[reversedItems, reversedPhrase]`
- **Elemen pertama:** Array `items` dengan urutan elemen yang dibalik
- **Elemen kedua:** String `phrase` dengan urutan karakter yang dibalik

---

## 💡 Panduan Implementasi

### Untuk Membalik Array
- Gunakan method built-in `reverse()` untuk membalik urutan elemen dalam array `items`

### Untuk Membalik String
1. Konversi string menjadi array karakter
2. Balikkan array karakter tersebut
3. Join kembali karakter-karakter menjadi string

---

## 📚 Contoh Penggunaan

```javascript
// Contoh 1
const items = ["sunscreen", "towel", "beach ball"];
const phrase = "sunny day";
const result = reverseBeachDay(items, phrase);
// Expected output: [["beach ball", "towel", "sunscreen"], "yad ynnus"]

// Contoh 2
const items = ["sandcastle", "seashells"];
const phrase = "ocean waves";
const result = reverseBeachDay(items, phrase);
// Expected output: [["seashells", "sandcastle"], "sevaw naeco"]
```

---

## ✅ Kriteria Keberhasilan

- [ ] Function berhasil membalik urutan elemen array
- [ ] Function berhasil membalik urutan karakter string
- [ ] Function mengembalikan array dengan tepat dua elemen
- [ ] Function menangani edge case (array satu item, string satu karakter)
- [ ] Function mematuhi batasan parameter

---

## 🔧 Catatan Teknis

> **Catatan:** Method `reverse()` memodifikasi array asli. Pertimbangkan apakah Anda perlu membuat copy dari array asli sebelum membalikkannya, tergantung pada kebutuhan implementasi Anda.

> **Tips:** Untuk membalik string, Anda dapat menggunakan method chain berikut:
> ```javascript
> string.split('').reverse().join('')
> ```

---

*Selamat coding! 🏖️✨*
