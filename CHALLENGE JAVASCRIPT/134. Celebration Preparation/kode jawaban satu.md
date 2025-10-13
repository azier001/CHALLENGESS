# 📚 Dokumentasi Fungsi `celebrationPrep()`

## 🎯 Deskripsi Fungsi

Fungsi `celebrationPrep()` adalah fungsi yang mengubah array berisi bilangan biner (binary) menjadi bilangan desimal, kemudian mengurutkannya dari nilai terkecil ke terbesar. Fungsi ini berguna ketika Anda perlu mengonversi dan mengurutkan data biner secara efisien.

---

## 📋 Parameter

| Parameter | Tipe Data | Deskripsi |
|-----------|-----------|-----------|
| `binaryNumbers` | Array (String) | Array yang berisi bilangan dalam format biner sebagai string. Contoh: `["101", "11", "1000"]` |

---

## 💻 Kode Fungsi

```javascript
function celebrationPrep(binaryNumbers) {
  // Mengubah setiap bilangan biner menjadi desimal, kemudian mengurutkan
  return binaryNumbers
    .map(binary => parseInt(binary, 2))      // Konversi biner ke desimal
    .sort((a, b) => a - b);                  // Urutkan dari kecil ke besar
}
```

---

## 🔍 Penjelasan Kode

### Baris per Baris

1. **`.map(binary => parseInt(binary, 2))`**
   - Menggunakan method `.map()` untuk mengubah setiap elemen array
   - `parseInt(binary, 2)` mengonversi string biner menjadi bilangan desimal
   - Parameter `2` menunjukkan bahwa input adalah bilangan biner (basis 2)

2. **`.sort((a, b) => a - b)`**
   - Menggunakan method `.sort()` untuk mengurutkan hasil konversi
   - `(a, b) => a - b` mengurutkan dari nilai terkecil ke terbesar
   - Jika `a - b` bernilai negatif, `a` berada di depan `b`

---

## 📊 Tabel Konversi Biner ke Desimal

Berikut beberapa contoh konversi bilangan biner ke desimal:

| Bilangan Biner | Perhitungan | Bilangan Desimal |
|---|---|---|
| `1` | 1 × 2⁰ | 1 |
| `10` | 1 × 2¹ + 0 × 2⁰ | 2 |
| `11` | 1 × 2¹ + 1 × 2⁰ | 3 |
| `100` | 1 × 2² + 0 × 2¹ + 0 × 2⁰ | 4 |
| `101` | 1 × 2² + 0 × 2¹ + 1 × 2⁰ | 5 |
| `1000` | 1 × 2³ | 8 |
| `1111` | 1 × 2³ + 1 × 2² + 1 × 2¹ + 1 × 2⁰ | 15 |

---

## 📝 Contoh Penggunaan

### Contoh 1️⃣ : Array Biner Acak

```javascript
const inputBiner1 = ["1010", "11", "1111", "100"];

const hasil1 = celebrationPrep(inputBiner1);

console.log(hasil1);
// Output: [3, 4, 10, 15]
```

**Penjelasan:**
- `"1010"` → 10 (desimal)
- `"11"` → 3 (desimal)
- `"1111"` → 15 (desimal)
- `"100"` → 4 (desimal)
- Setelah diurutkan: `[3, 4, 10, 15]`

---

### Contoh 2️⃣ : Array Biner dengan Nilai Kecil

```javascript
const inputBiner2 = ["1", "0", "11", "10"];

const hasil2 = celebrationPrep(inputBiner2);

console.log(hasil2);
// Output: [0, 1, 2, 3]
```

**Penjelasan:**
- `"1"` → 1 (desimal)
- `"0"` → 0 (desimal)
- `"11"` → 3 (desimal)
- `"10"` → 2 (desimal)
- Setelah diurutkan: `[0, 1, 2, 3]`

---

### Contoh 3️⃣ : Array Biner Besar

```javascript
const inputBiner3 = ["11111111", "10101010", "11110000", "10001000"];

const hasil3 = celebrationPrep(inputBiner3);

console.log(hasil3);
// Output: [136, 170, 240, 255]
```

**Penjelasan:**
- `"11111111"` → 255 (desimal)
- `"10101010"` → 170 (desimal)
- `"11110000"` → 240 (desimal)
- `"10001000"` → 136 (desimal)
- Setelah diurutkan: `[136, 170, 240, 255]`

---

## ✅ Kegunaan Fungsi

- ✨ Mengonversi data biner menjadi desimal untuk proses selanjutnya
- 📊 Mengurutkan data numerik dari terkecil ke terbesar
- 🎯 Menyiapkan data untuk algoritma atau visualisasi
- 💡 Berguna dalam pemrograman sistem, operasi bit, atau data processing

---

## ⚠️ Catatan Penting

- Pastikan semua elemen dalam array adalah string bilangan biner yang valid
- Elemen harus hanya berisi karakter `0` dan `1`
- Jika ada elemen non-biner, hasil mungkin tidak sesuai harapan

---

## 🎓 Kesimpulan

Fungsi `celebrationPrep()` adalah cara yang elegan untuk mengonversi dan mengurutkan array bilangan biner sekaligus menggunakan method chaining yang membuat kode lebih ringkas dan mudah dibaca.
