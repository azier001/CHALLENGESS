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
  // Konversi angka desimal ke string biner, lalu pisahkan berdasarkan karakter '1'
  // Jumlah elemen array dikurangi 1 = jumlah angka '1' dalam biner
  return decimalCandles.toString(2).split('1').length - 1;
}
```

---

## 🔍 Cara Kerja

1. **Konversi ke Biner**: Menggunakan `toString(2)` untuk mengubah angka desimal menjadi string biner
2. **Split Berdasarkan '1'**: Memisahkan string biner menggunakan karakter `'1'` sebagai delimiter
3. **Hitung Jumlah '1'**: Jumlah elemen array hasil split dikurangi 1 sama dengan jumlah karakter `'1'`

### 📊 Contoh Proses:
- Input: `5` (desimal)
- Biner: `"101"`
- Split: `["", "0", ""]` → 3 elemen
- Jumlah '1': `3 - 1 = 2` ✅

---

## 📊 Tabel Contoh Konversi

| Desimal | Biner | Jumlah '1' | Penjelasan |
|---------|-------|------------|------------|
| 0 | `0` | 0 | Tidak ada bit 1 |
| 1 | `1` | 1 | Satu bit 1 |
| 5 | `101` | 2 | Dua bit 1 |
| 7 | `111` | 3 | Tiga bit 1 |
| 10 | `1010` | 2 | Dua bit 1 |
| 15 | `1111` | 4 | Empat bit 1 |
| 255 | `11111111` | 8 | Delapan bit 1 |

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
```

---

## 💡 Tips & Catatan

- Fungsi ini bekerja optimal untuk bilangan bulat positif
- Semakin besar angka desimal, semakin panjang representasi binernya
- Metode ini adalah cara kreatif untuk menghitung bit 1 tanpa menggunakan loop
- Alternatif lain untuk menghitung bit 1 adalah menggunakan bit manipulation dengan operator `&` (AND)

---

## ⚠️ Perhatian

- Pastikan input adalah angka desimal yang valid
- Untuk angka negatif, JavaScript akan menghasilkan representasi biner dengan tanda minus yang mungkin tidak sesuai ekspektasi
- Fungsi ini tidak melakukan validasi input, jadi pastikan data yang dikirim sudah benar

---

## 📚 Referensi

- [MDN - toString()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/toString)
- [MDN - split()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/split)
- [Binary Number System](https://en.wikipedia.org/wiki/Binary_number)
