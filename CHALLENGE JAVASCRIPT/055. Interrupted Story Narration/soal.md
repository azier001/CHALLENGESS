# 🔍 Challenge Interrupted Story Narration

## 📊 Tingkat Kesulitan
**Easy**

---

## 🎯 Tujuan

Buat sebuah function bernama `findStopWord` yang memproses sebuah array kalimat dan mengembalikan subset berdasarkan kondisi stop word yang ditentukan.

## 📝 Spesifikasi Function

### Nama Function
```javascript
findStopWord(sentences, stopWord)
```

### Parameter

| Parameter | Type | Deskripsi |
|-----------|------|-----------|
| `sentences` | `array` | Sebuah array string dimana setiap string merepresentasikan kalimat dari cerita |
| `stopWord` | `string` | Kata kunci yang memicu penghentian narasi cerita |

### Return Value
- **Type**: `array`
- **Content**: Array string berisi kalimat dari awal hingga `stopWord` ditemukan untuk pertama kalinya
- **Special Case**: Jika `stopWord` tidak ditemukan, mengembalikan array `sentences` yang asli

---

## 🔧 Persyaratan Implementasi

### Logic Utama
1. **Loop through** array kalimat yang diberikan
2. **Periksa setiap kalimat** untuk keberadaan `stopWord`
3. **Terminate immediately** ketika `stopWord` ditemukan menggunakan statement `break`
4. **Return array** berisi semua kalimat hingga dan termasuk kalimat yang mengandung `stopWord`

### Poin Penting
- ✅ Sertakan kalimat yang mengandung `stopWord` dalam hasil
- ✅ Gunakan statement `break` untuk penghentian loop secara langsung
- ✅ Tangani kasus dimana `stopWord` tidak ditemukan (return seluruh array)
- ✅ Proses kalimat secara berurutan dari awal

---

## 💡 Perilaku yang Diharapkan

### Skenario 1: Stop Word Ditemukan
```
Input: ["Once upon a time", "There was a dragon", "The end came quickly"]
Stop Word: "dragon"
Output: ["Once upon a time", "There was a dragon"]
```

### Skenario 2: Stop Word Tidak Ditemukan
```
Input: ["Once upon a time", "There was a princess", "She lived happily"]
Stop Word: "dragon"
Output: ["Once upon a time", "There was a princess", "She lived happily"]
```

---

## 🏷️ Tags
`Array Processing` • `String Manipulation` • `Loop Control` • `Conditional Logic`
