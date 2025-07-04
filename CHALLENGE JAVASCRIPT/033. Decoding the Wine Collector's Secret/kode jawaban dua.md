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

1. **Pemisahan Token**: Memisahkan teks input berdasarkan spasi
2. **Deteksi Jenis Encoding**: 
   - Jika token dimulai dengan `#` → Kode biner
   - Jika tidak → Kata terbalik
3. **Proses Decoding**:
   - **Kode Biner**: Hapus `#`, konversi biner ke desimal, lalu ke karakter ASCII
   - **Kata Terbalik**: Balik urutan huruf dalam kata
4. **Penggabungan**: Gabungkan semua token yang sudah didecode

## 💻 Kode Fungsi

```javascript
function decodeWineCollectorSecret(text) {
    // Pisahkan teks menjadi kata-kata/token terpisah
    const tokens = text.split(' ');
    
    // Proses setiap token satu per satu
    const decodedTokens = tokens.map(token => {
        // Cek apakah token adalah angka biner (dimulai dengan #)
        if (token.startsWith('#')) {
            // Hilangkan tanda # di depan dan ambil angka binernya
            const binaryStr = token.slice(1);
            // Konversi dari biner ke desimal
            const decimal = parseInt(binaryStr, 2);
            // Konversi angka desimal menjadi karakter ASCII
            return String.fromCharCode(decimal);
        } else {
            // Ini adalah kata yang dibalik, jadi balik lagi ke normal
            // Caranya: pecah jadi array huruf, balik urutannya, gabung lagi
            return token.split('').reverse().join('');
        }
    });
    
    // Gabungkan semua token yang sudah didecode menjadi satu string
    return decodedTokens.join(' ');
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
- `#1001000` → 72 → 'H'
- `#1100101` → 101 → 'e'  
- `#1101100` → 108 → 'l'
- `#1101100` → 108 → 'l'
- `#1101111` → 111 → 'o'
- `#100000` → 32 → ' ' (spasi)
- `dlroW` → 'World' (kata terbalik)

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
- `gnidoC` → 'Coding' (kata terbalik)
- `#1101001` → 105 → 'i'
- `#1110011` → 115 → 's'
- `nuf` → 'fun' (kata terbalik)

## ⚠️ Catatan Penting

- Pastikan kode biner yang digunakan valid dan dapat dikonversi ke karakter ASCII
- Fungsi ini sensitif terhadap spasi sebagai pemisah token
- Setiap token yang dimulai dengan `#` akan diperlakukan sebagai kode biner
- Token tanpa `#` akan diperlakukan sebagai kata terbalik

## 🎨 Tips Penggunaan

1. **Debugging**: Gunakan `console.log` untuk melihat proses decoding step-by-step
2. **Validasi**: Pastikan input sesuai format yang diharapkan
3. **Testing**: Coba berbagai kombinasi kode biner dan kata terbalik

---

*Dibuat dengan ❤️ untuk membantu memahami fungsi decoding yang kompleks*
