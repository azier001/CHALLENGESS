# 🕯️ Dokumentasi Fungsi `banquetBinaryCandles`

## 📝 Deskripsi

Fungsi `banquetBinaryCandles` digunakan untuk menghitung jumlah lilin yang menyala dalam sebuah perjamuan berdasarkan representasi biner dari angka desimal. Fungsi ini mengkonversi angka desimal menjadi biner, kemudian menghitung berapa banyak angka `1` yang muncul dalam representasi biner tersebut.

Secara sederhana, fungsi ini menghitung **berapa banyak bit yang bernilai 1** dalam representasi biner sebuah angka.

---

## 🎯 Kegunaan

- Menghitung jumlah bit aktif (1) dalam representasi biner
- Berguna untuk perhitungan matematis yang melibatkan sistem biner
- Dapat digunakan dalam masalah pemrograman yang berkaitan dengan bit manipulation

---

## 📋 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `decimalCandles` | `Number` | Angka desimal (bilangan bulat positif) yang akan dikonversi ke biner untuk dihitung jumlah bit 1-nya |

---

## 🔙 Return Value

| Tipe | Deskripsi |
|------|-----------|
| `Number` | Jumlah angka `1` dalam representasi biner dari input |

---

## 💻 Kode Fungsi

```javascript
function banquetBinaryCandles(decimalCandles) {
  // Konversi angka desimal ke string biner (contoh: 5 menjadi "101")
  const binaryCandles = decimalCandles.toString(2);
  
  // Pisahkan setiap karakter, filter hanya yang bernilai '1', lalu hitung jumlahnya
  const litCandles = binaryCandles.split('').filter(candle => candle === '1').length;
  
  // Kembalikan jumlah lilin yang menyala (jumlah bit 1)
  return litCandles;
}
```

---

## 🔍 Cara Kerja

1. **Konversi ke Biner**: Menggunakan `toString(2)` untuk mengubah angka desimal menjadi string biner
2. **Split String**: Memisahkan string biner menjadi array karakter dengan `split('')`
3. **Filter Karakter '1'**: Menggunakan `filter()` untuk menyaring hanya karakter yang bernilai `'1'`
4. **Hitung Panjang Array**: Menggunakan `.length` untuk menghitung jumlah karakter `'1'` yang tersaring

### 📊 Contoh Proses:
- Input: `5` (desimal)
- Biner: `"101"`
- Split: `["1", "0", "1"]`
- Filter: `["1", "1"]`
- Length: `2` ✅

---

## 📊 Tabel Contoh Konversi

| Desimal | Biner | Array Split | Array Filter | Jumlah '1' |
|---------|-------|-------------|--------------|------------|
| 0 | `0` | `["0"]` | `[]` | 0 |
| 1 | `1` | `["1"]` | `["1"]` | 1 |
| 5 | `101` | `["1","0","1"]` | `["1","1"]` | 2 |
| 7 | `111` | `["1","1","1"]` | `["1","1","1"]` | 3 |
| 10 | `1010` | `["1","0","1","0"]` | `["1","1"]` | 2 |
| 15 | `1111` | `["1","1","1","1"]` | `["1","1","1","1"]` | 4 |
| 255 | `11111111` | `["1","1",..."1"]` | `["1","1",..."1"]` | 8 |

---

## 🎮 Contoh Penggunaan

```javascript
// Contoh 1: Menghitung lilin untuk angka 5
console.log(banquetBinaryCandles(5));
// Output: 2
// Penjelasan: 5 dalam biner = 101 (ada 2 angka '1')

// Contoh 2: Menghitung lilin untuk angka 7
console.log(banquetBinaryCandles(7));
// Output: 3
// Penjelasan: 7 dalam biner = 111 (ada 3 angka '1')

// Contoh 3: Menghitung lilin untuk angka 10
console.log(banquetBinaryCandles(10));
// Output: 2
// Penjelasan: 10 dalam biner = 1010 (ada 2 angka '1')

// Contoh 4: Menghitung lilin untuk angka 15
console.log(banquetBinaryCandles(15));
// Output: 4
// Penjelasan: 15 dalam biner = 1111 (ada 4 angka '1')

// Contoh 5: Menghitung lilin untuk angka 0
console.log(banquetBinaryCandles(0));
// Output: 0
// Penjelasan: 0 dalam biner = 0 (tidak ada angka '1')

// Contoh 6: Menghitung lilin untuk angka 255
console.log(banquetBinaryCandles(255));
// Output: 8
// Penjelasan: 255 dalam biner = 11111111 (ada 8 angka '1')
```

---

## 🔄 Perbandingan dengan Metode Lain

### Metode 1: Split & Filter (Kode di atas)
```javascript
const litCandles = decimalCandles.toString(2).split('').filter(c => c === '1').length;
```
✅ **Kelebihan**: Lebih mudah dibaca dan dipahami pemula  
✅ **Cocok untuk**: Pembelajaran dan kode yang mengutamakan kejelasan

### Metode 2: Split by '1'
```javascript
const litCandles = decimalCandles.toString(2).split('1').length - 1;
```
✅ **Kelebihan**: Lebih singkat dan efisien  
✅ **Cocok untuk**: Kode production yang mengutamakan performa

---

## 💡 Tips & Catatan

- Fungsi ini menggunakan pendekatan yang lebih eksplisit dan mudah dipahami
- Method `filter()` membuat kode lebih readable karena jelas terlihat kita sedang mencari karakter '1'
- Cocok untuk pembelajaran karena setiap langkah pemrosesan terlihat jelas
- Semakin besar angka desimal, semakin panjang representasi binernya

---

## ⚡ Kompleksitas

- **Time Complexity**: O(log n) - dimana n adalah nilai input, karena panjang representasi biner adalah log₂(n)
- **Space Complexity**: O(log n) - untuk menyimpan string biner dan array hasil split

---

## ⚠️ Perhatian

- Pastikan input adalah angka desimal yang valid
- Untuk angka negatif, JavaScript akan menghasilkan representasi biner dengan tanda minus yang mungkin tidak sesuai ekspektasi
- Fungsi ini tidak melakukan validasi input, jadi pastikan data yang dikirim sudah benar
- Jika performa menjadi prioritas untuk data besar, pertimbangkan menggunakan bit manipulation dengan operator `&` (AND)

---

## 🎓 Penjelasan untuk Pemula

### Apa itu Biner?
Sistem biner adalah sistem bilangan yang hanya menggunakan dua angka: `0` dan `1`. Komputer menggunakan sistem ini untuk menyimpan dan memproses data.

### Contoh Sederhana:
- Angka **5** dalam desimal = **101** dalam biner
  - 1 × 2² + 0 × 2¹ + 1 × 2⁰ = 4 + 0 + 1 = 5

### Mengapa Menghitung Angka '1'?
Dalam banyak kasus pemrograman, kita perlu tahu berapa banyak bit yang "aktif" (bernilai 1) dalam sebuah angka. Ini berguna untuk:
- Optimasi memori
- Algoritma encoding/decoding
- Perhitungan matematika khusus
- Puzzle dan problem solving

---

## 📚 Referensi

- [MDN - toString()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/toString)
- [MDN - split()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/split)
- [MDN - filter()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter)
- [Binary Number System](https://en.wikipedia.org/wiki/Binary_number)
