# 📝 Dokumentasi Fungsi `decodeMessage`

## 🎯 Deskripsi Fungsi

Fungsi `decodeMessage` adalah sebuah fungsi JavaScript yang digunakan untuk **mendekode pesan biner** menjadi teks yang dapat dibaca. Fungsi ini mengubah deretan angka biner (0 dan 1) yang dipisahkan dengan spasi menjadi huruf-huruf alfabet atau spasi menggunakan pendekatan **functional programming** dengan metode `map()` dan `join()`.

## 📋 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `binaryMessage` | `string` | String yang berisi pesan biner dengan setiap angka biner dipisahkan oleh spasi |

## 🔄 Cara Kerja

1. **Pemisahan**: Memisahkan pesan biner berdasarkan spasi untuk mendapatkan array angka biner
2. **Konversi Biner ke Desimal**: Mengubah setiap angka biner dalam array menjadi angka desimal
3. **Konversi ke Karakter**: Mengubah setiap angka desimal menjadi karakter (spasi untuk 32, huruf untuk 1-26)
4. **Penggabungan**: Menggabungkan semua karakter menjadi satu string pesan

## 📊 Tabel Konversi Karakter

| Angka Desimal | Biner | Karakter |
|---------------|-------|----------|
| 1 | 1 | A |
| 2 | 10 | B |
| 3 | 11 | C |
| ... | ... | ... |
| 26 | 11010 | Z |
| 32 | 100000 | (spasi) |

## 💻 Kode Fungsi

```javascript
function decodeMessage(binaryMessage) {
  // Pisahkan pesan biner berdasarkan spasi menjadi array angka biner
  const binaryNumbers = binaryMessage.split(' ');
  
  // Konversi setiap angka biner menjadi desimal menggunakan map()
  const decimalNumbers = binaryNumbers.map(binary => parseInt(binary, 2));
  
  // Konversi setiap angka desimal menjadi karakter yang sesuai
  const decodedLetters = decimalNumbers.map(decimal => {
    if (decimal === 32) {
      // Jika desimal = 32, kembalikan spasi
      return ' ';
    } else {
      // Konversi desimal ke huruf (1=A, 2=B, ..., 26=Z)
      return String.fromCharCode(decimal + 64); // 64 + 1 = 65 (ASCII untuk 'A')
    }
  });
  
  // Gabungkan semua karakter menjadi satu string pesan
  const decodedMessage = decodedLetters.join('');
  
  return decodedMessage;
}
```

## 🚀 Contoh Penggunaan

### Contoh 1: Pesan Sederhana

```javascript
// Input: pesan biner untuk "HELLO"
const binaryInput1 = "1000 101 1100 1100 1111";
const result1 = decodeMessage(binaryInput1);
console.log(result1); // Output: "HELLO"
```

**Proses step-by-step:**
- `binaryNumbers`: `["1000", "101", "1100", "1100", "1111"]`
- `decimalNumbers`: `[8, 5, 12, 12, 15]`
- `decodedLetters`: `["H", "E", "L", "L", "O"]`
- `decodedMessage`: `"HELLO"`

### Contoh 2: Pesan dengan Spasi

```javascript
// Input: pesan biner untuk "HI WORLD"
const binaryInput2 = "1000 1001 100000 10111 1111 10010 1100 100";
const result2 = decodeMessage(binaryInput2);
console.log(result2); // Output: "HI WORLD"
```

**Proses step-by-step:**
- `binaryNumbers`: `["1000", "1001", "100000", "10111", "1111", "10010", "1100", "100"]`
- `decimalNumbers`: `[8, 9, 32, 23, 15, 18, 12, 4]`
- `decodedLetters`: `["H", "I", " ", "W", "O", "R", "L", "D"]`
- `decodedMessage`: `"HI WORLD"`

### Contoh 3: Pesan Panjang

```javascript
// Input: pesan biner untuk "CODE"
const binaryInput3 = "11 1111 100 101";
const result3 = decodeMessage(binaryInput3);
console.log(result3); // Output: "CODE"
```

**Proses step-by-step:**
- `binaryNumbers`: `["11", "1111", "100", "101"]`
- `decimalNumbers`: `[3, 15, 4, 5]`
- `decodedLetters`: `["C", "O", "D", "E"]`
- `decodedMessage`: `"CODE"`

## 📤 Output

Fungsi ini mengembalikan sebuah **string** yang berisi pesan yang telah didekode dari format biner ke teks yang dapat dibaca.

## 🛠️ Keunggulan Implementasi

### ✨ Functional Programming Style
- Menggunakan metode `map()` untuk transformasi data
- Kode lebih bersih dan mudah dibaca
- Setiap langkah terpisah dengan jelas

### 🔍 Struktur yang Jelas
- **Step 1**: Split → Array biner
- **Step 2**: Map biner → Array desimal  
- **Step 3**: Map desimal → Array karakter
- **Step 4**: Join → String final

## ⚠️ Catatan Penting

- Pastikan setiap angka biner dalam input dipisahkan oleh **satu spasi**
- Fungsi ini menggunakan konversi khusus dimana:
  - Angka 1-26 diubah menjadi huruf A-Z
  - Angka 32 diubah menjadi spasi
- Input yang tidak valid (seperti angka > 26 kecuali 32) akan menghasilkan karakter ASCII yang mungkin tidak diinginkan

## 🔧 Pengembangan Lebih Lanjut

Fungsi ini dapat dikembangkan dengan menambahkan:
- Validasi input untuk memastikan format biner yang benar
- Penanganan error untuk input yang tidak valid
- Dukungan untuk huruf kecil (a-z)
- Dukungan untuk angka dan simbol lainnya
- Method chaining untuk kode yang lebih ringkas
