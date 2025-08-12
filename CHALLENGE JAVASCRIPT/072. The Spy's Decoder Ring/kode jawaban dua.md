# 📝 Dokumentasi Fungsi `decodeMessage`

## 🎯 Deskripsi Fungsi

Fungsi `decodeMessage` adalah sebuah fungsi JavaScript yang digunakan untuk **mendekode pesan biner** menjadi teks yang dapat dibaca. Fungsi ini mengubah deretan angka biner (0 dan 1) yang dipisahkan dengan spasi menjadi huruf-huruf alfabet atau spasi.

## 📋 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `binaryMessage` | `string` | String yang berisi pesan biner dengan setiap angka biner dipisahkan oleh spasi |

## 🔄 Cara Kerja

1. **Pemisahan**: Memisahkan pesan biner berdasarkan spasi untuk mendapatkan angka biner individual
2. **Konversi Biner ke Desimal**: Mengubah setiap angka biner menjadi angka desimal
3. **Pengecekan Spasi**: Jika angka desimal adalah 32 (kode ASCII untuk spasi), maka ditambahkan spasi
4. **Konversi ke Huruf**: Jika bukan spasi, angka desimal diubah menjadi huruf (1=A, 2=B, dst.)

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
    // Pisahkan pesan biner berdasarkan spasi untuk mendapatkan angka biner individual
    const binaryNumbers = binaryMessage.split(' ');
    
    let decodedMessage = '';
    
    // Loop untuk setiap angka biner
    for (let binary of binaryNumbers) {
        // Konversi biner ke desimal
        const decimal = parseInt(binary, 2);
        
        // Cek apakah ini adalah spasi (32 dalam ASCII)
        if (decimal === 32) {
            decodedMessage += ' ';
        } else {
            // Konversi desimal ke huruf yang sesuai (1=A, 2=B, ..., 26=Z)
            const letter = String.fromCharCode(decimal + 64); // 64 + 1 = 65 (ASCII untuk 'A')
            decodedMessage += letter;
        }
    }
    
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

### Contoh 2: Pesan dengan Spasi

```javascript
// Input: pesan biner untuk "HI WORLD"
const binaryInput2 = "1000 1001 100000 10111 1111 10010 1100 100";
const result2 = decodeMessage(binaryInput2);
console.log(result2); // Output: "HI WORLD"
```

### Contoh 3: Pesan Panjang

```javascript
// Input: pesan biner untuk "CODE"
const binaryInput3 = "11 1111 100 101";
const result3 = decodeMessage(binaryInput3);
console.log(result3); // Output: "CODE"
```

## 📤 Output

Fungsi ini mengembalikan sebuah **string** yang berisi pesan yang telah didekode dari format biner ke teks yang dapat dibaca.

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
