# 🔓 Dokumentasi Fungsi `prisonBreak`

## 📋 Deskripsi

Fungsi `prisonBreak` adalah sebuah algoritma dekripsi sederhana yang mengekstrak bagian tertentu dari pesan terenkripsi berdasarkan nomor sel penjara. Fungsi ini mengambil substring dari posisi tertentu dengan panjang yang sama dengan nomor sel, kemudian menggabungkannya dengan nomor sel untuk membentuk kode pelarian.

## 🎯 Cara Kerja

1. **Ekstraksi Substring**: Mengambil bagian dari pesan mulai dari indeks `cellNumber` dengan panjang sebesar `cellNumber`
2. **Penggabungan**: Menggabungkan substring dengan nomor sel dalam bentuk string
3. **Output**: Mengembalikan kode pelarian sebagai string gabungan

## 📝 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `encodedMessage` | `string` | Pesan terenkripsi yang akan didekripsi |
| `cellNumber` | `number` | Nomor sel penjara (digunakan sebagai indeks dan panjang ekstraksi) |

## 🔧 Kode Fungsi

```javascript
function prisonBreak(encodedMessage, cellNumber) {
    // Extract substring starting at cellNumber index with length of cellNumber
    let substring;
    
    if (cellNumber >= encodedMessage.length) {
        // If cellNumber is greater than or equal to message length, substring is empty
        substring = "";
    } else {
        // Extract substring from cellNumber index with cellNumber length
        substring = encodedMessage.substring(cellNumber, cellNumber + cellNumber);
    }
    
    // Create array with substring and cellNumber as string
    const escapeArray = [substring, cellNumber.toString()];
    
    // Join array elements into single string
    return escapeArray.join('');
}
```

## 💡 Contoh Penggunaan

### Contoh 1: Kasus Normal
```javascript
prisonBreak("ABCDEFGHIJK", 3);
// Output: "DEF3"
```

**Penjelasan:**
- Mulai dari indeks 3 (karakter 'D')
- Ambil 3 karakter: "DEF"
- Gabungkan dengan nomor sel "3"
- Hasil: "DEF3"

### Contoh 2: Nomor Sel Lebih Besar dari Panjang Pesan
```javascript
prisonBreak("HELLO", 10);
// Output: "10"
```

**Penjelasan:**
- Nomor sel (10) ≥ panjang pesan (5)
- Substring menjadi kosong ""
- Gabungkan dengan nomor sel "10"
- Hasil: "10"

### Contoh 3: Nomor Sel di Akhir String
```javascript
prisonBreak("SECRET", 5);
// Output: "T5"
```

**Penjelasan:**
- Mulai dari indeks 5 (karakter 'T')
- Ambil 5 karakter, tetapi hanya tersisa 1 karakter: "T"
- Gabungkan dengan nomor sel "5"
- Hasil: "T5"

## 📊 Tabel Karakter untuk Contoh

| Indeks | 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 |
|--------|---|---|---|---|---|---|---|---|---|---|----| 
| Karakter | A | B | C | D | E | F | G | H | I | J | K |

**Untuk `prisonBreak("ABCDEFGHIJK", 3)`:**
- Mulai dari indeks 3 (D)
- Ambil 3 karakter: D, E, F
- Hasil substring: "DEF"

## ⚠️ Catatan Penting

- Jika `cellNumber` sama dengan atau lebih besar dari panjang pesan, fungsi akan mengembalikan string kosong yang digabung dengan nomor sel
- Fungsi menggunakan `substring()` yang aman dari index overflow
- Output selalu berupa string yang menggabungkan substring dan nomor sel

## 🎮 Skenario Penggunaan

Fungsi ini cocok digunakan untuk:
- 🔐 Sistem dekripsi sederhana
- 🎯 Game puzzle atau teka-teki
- 📱 Aplikasi yang membutuhkan ekstraksi data berdasarkan posisi
- 🔢 Algoritma encoding/decoding custom

## 🧪 Tips untuk Pemula

1. **Pahami Indeks**: Ingat bahwa indeks string dimulai dari 0
2. **Substring vs Slice**: Fungsi ini menggunakan `substring()` yang lebih aman daripada `slice()`
3. **Konversi Tipe**: Nomor sel dikonversi ke string menggunakan `toString()`
4. **Penggabungan Array**: Menggunakan `join('')` untuk menggabungkan elemen array tanpa separator
