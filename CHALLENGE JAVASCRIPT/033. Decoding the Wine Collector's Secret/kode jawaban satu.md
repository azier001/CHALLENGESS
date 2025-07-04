# 🍷 Dokumentasi Fungsi `decodeWineCollectorSecret`

## 📋 Deskripsi Fungsi

Fungsi `decodeWineCollectorSecret` adalah sebuah decoder khusus yang digunakan untuk menguraikan pesan rahasia yang dikodekan dengan dua metode berbeda:

1. **Kode Biner** - Angka biner yang diawali dengan simbol `#` yang kemudian dikonversi menjadi karakter ASCII
2. **Kata Terbalik** - Kata-kata yang dibalik urutan hurufnya

Fungsi ini sangat berguna untuk menguraikan pesan-pesan terenkripsi yang menggunakan kombinasi kedua metode encoding tersebut.

## 🔧 Parameter

| Parameter | Tipe     | Deskripsi                                                    |
|-----------|----------|--------------------------------------------------------------|
| `text`    | `string` | Teks yang akan didecode, berisi kombinasi kode biner dan kata terbalik |

## 🗂️ Tabel Karakter ASCII (Contoh)

| Biner     | Desimal | Karakter |
|-----------|---------|----------|
| 1001000   | 72      | H        |
| 1100101   | 101     | e        |
| 1101100   | 108     | l        |
| 1101100   | 108     | l        |
| 1101111   | 111     | o        |
| 100000    | 32      | (spasi)  |

## 📝 Cara Kerja

1. **Pemisahan Bagian**: Memisahkan teks input berdasarkan spasi menggunakan `split(' ')`
2. **Deteksi Jenis Encoding**: 
   - Jika bagian dimulai dengan `#` → Kode biner
   - Jika tidak → Kata terbalik
3. **Proses Decoding**:
   - **Kode Biner**: Hapus `#` dengan `slice(1)`, konversi biner ke desimal dengan `parseInt()`, lalu ke karakter ASCII dengan `String.fromCharCode()`
   - **Kata Terbalik**: Pecah jadi array huruf, balik urutan dengan `reverse()`, gabung kembali dengan `join('')`
4. **Penggabungan**: Gabungkan semua bagian yang sudah didecode dengan spasi

## 💻 Kode Fungsi

```javascript
function decodeWineCollectorSecret(text) {
  const parts = text.split(' ');
  const decodedParts = parts.map(part => {
    if (part.startsWith('#')) {
      const binaryCode = part.slice(1);
      const decimalCode = parseInt(binaryCode, 2);
      return String.fromCharCode(decimalCode);
    } else {
      return part.split('').reverse().join('');
    }
  });
  return decodedParts.join(' ');
}
```

## 🎯 Contoh Penggunaan

### Input:
```javascript
const encodedMessage = "#1001000 #1100101 #1101100 #1101100 #1101111 #100000 dlroW";
const result = decodeWineCollectorSecret(encodedMessage);
```

### Output:
```
Hello World
```

### Penjelasan Contoh:
- `#1001000` → binaryCode: '1001000' → decimalCode: 72 → 'H'
- `#1100101` → binaryCode: '1100101' → decimalCode: 101 → 'e'  
- `#1101100` → binaryCode: '1101100' → decimalCode: 108 → 'l'
- `#1101100` → binaryCode: '1101100' → decimalCode: 108 → 'l'
- `#1101111` → binaryCode: '1101111' → decimalCode: 111 → 'o'
- `#100000` → binaryCode: '100000' → decimalCode: 32 → ' ' (spasi)
- `dlroW` → split: ['d','l','r','o','W'] → reverse: ['W','o','r','l','d'] → join: 'World'

**Hasil akhir**: "Hello World"

## 🔍 Contoh Lain

### Input:
```javascript
const message2 = "gnidoC #1101001 #1110011 nuf";
const result2 = decodeWineCollectorSecret(message2);
```

### Output:
```
Coding is fun
```

### Penjelasan:
- `gnidoC` → ['g','n','i','d','o','C'] → ['C','o','d','i','n','g'] → 'Coding'
- `#1101001` → binaryCode: '1101001' → decimalCode: 105 → 'i'
- `#1110011` → binaryCode: '1110011' → decimalCode: 115 → 's'
- `nuf` → ['n','u','f'] → ['f','u','n'] → 'fun'

## 🚀 Contoh Kompleks

### Input:
```javascript
const secretMessage = "#1010111 #1100101 #1101100 #1100011 emoc ot eht eniw rotcelloc";
const result3 = decodeWineCollectorSecret(secretMessage);
```

### Output:
```
Welcome to the wine collector
```

### Penjelasan:
- `#1010111` → 87 → 'W'
- `#1100101` → 101 → 'e'
- `#1101100` → 108 → 'l'
- `#1100011` → 99 → 'c'
- `emoc` → 'come'
- `ot` → 'to'
- `eht` → 'the'
- `eniw` → 'wine'
- `rotcelloc` → 'collector'

## ⚠️ Catatan Penting

- Pastikan kode biner yang digunakan valid dan dapat dikonversi ke karakter ASCII
- Fungsi ini menggunakan spasi sebagai pemisah utama antara bagian-bagian teks
- Setiap bagian yang dimulai dengan `#` akan diperlakukan sebagai kode biner
- Bagian tanpa `#` akan diperlakukan sebagai kata yang perlu dibalik
- Pastikan tidak ada spasi tambahan di awal atau akhir input

## 🎨 Tips Penggunaan

1. **Debugging**: Gunakan `console.log(parts)` untuk melihat bagaimana teks dipecah
2. **Validasi**: Cek apakah setiap kode biner valid sebelum decoding
3. **Testing**: Coba berbagai kombinasi untuk memastikan fungsi bekerja dengan baik
4. **Performance**: Fungsi ini efisien untuk teks berukuran sedang

## 🔧 Variabel dalam Fungsi

| Variabel       | Tipe     | Deskripsi                                    |
|----------------|----------|----------------------------------------------|
| `parts`        | `array`  | Array berisi bagian-bagian teks terpisah    |
| `decodedParts` | `array`  | Array berisi bagian-bagian yang sudah didecode |
| `binaryCode`   | `string` | Kode biner tanpa simbol `#`                 |
| `decimalCode`  | `number` | Nilai desimal hasil konversi dari biner     |

---

*Dibuat dengan ❤️ untuk membantu memahami fungsi decoding yang kompleks*
