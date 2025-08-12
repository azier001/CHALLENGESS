# 🕵️ The Spy's Decoder Ring

## 📋 Overview Challenge

**Tingkat Kesulitan:** `Easy`

Buat sebuah function yang dapat mendekode pesan binary rahasia menggunakan substitution cipher. Asah kemampuan Anda dalam manipulasi binary dan pemrosesan string sambil mengungkap pesan tersembunyi!

---

## 🎯 Objektif

Implementasikan sebuah function bernama `decodeMessage` yang mengkonversi pesan binary-encoded kembali menjadi teks yang dapat dibaca menggunakan alphabet-to-number mapping.

### Function Signature
```javascript
function decodeMessage(binaryMessage) {
    // Implementasi Anda di sini
}
```

---

## 🔧 Cara Kerja

Proses decoding mengikuti substitution cipher khusus dimana:
- Setiap huruf berkorespondensi dengan posisinya di alphabet
- Huruf di-encode sebagai binary numbers
- Spasi memiliki representasi binary khusus

### Referensi Encoding
| Huruf | Nilai Desimal | Ekuivalen Binary |
|-------|---------------|------------------|
| A     | 1             | `1`              |
| B     | 2             | `10`             |
| C     | 3             | `11`             |
| ...   | ...           | ...              |
| Z     | 26            | `11010`          |
| Spasi | 32            | `00100000`       |

---

## 📝 Langkah-langkah Decoding

Ikuti langkah berikut untuk mendekode pesan binary:

1. **🔍 Split Message**
   - Pisahkan pesan binary menjadi binary numbers individual
   - Setiap number merepresentasikan huruf atau spasi

2. **🔢 Konversi Binary ke Desimal**
   - Konversi setiap binary number ke ekuivalen desimalnya
   - Gunakan metode konversi binary-to-decimal standar

3. **📚 Alphabet Mapping**
   - Map nilai desimal ke huruf alphabet yang sesuai
   - Gunakan formula: `1 = A, 2 = B, ..., 26 = Z`
   - Handle spasi dengan nilai desimal `32`

4. **🔗 Concatenate Hasil**
   - Gabungkan semua huruf yang sudah didekode untuk membentuk pesan final
   - Pertahankan spasi untuk pemisahan kata yang tepat

---

## 💡 Kasus Khusus

### Karakter Spasi
- **Representasi Binary:** `00100000`
- **Nilai Desimal:** `32`
- **Output:** Karakter spasi tunggal ` `

---

## 📥 Parameter

| Parameter | Type | Deskripsi |
|-----------|------|-----------|
| `binaryMessage` | `string` | Pesan binary encoded yang akan didekode |

---

## 📤 Return Value

| Type | Deskripsi |
|------|-----------|
| `string` | Pesan yang sudah didekode dalam format teks yang dapat dibaca |

---

## 🧪 Contoh Penggunaan

```javascript
// Contoh input binary (merepresentasikan "HELLO WORLD")
const binaryInput = "1000 101 1100 1100 1111 00100000 10111 1111 10010 1100 100";

const result = decodeMessage(binaryInput);
console.log(result); // Expected output: "HELLO WORLD"
```

---

## ✅ Kriteria Sukses

Solusi Anda harus:
- ✅ Handle semua huruf A-Z dengan benar
- ✅ Memproses spasi dengan tepat
- ✅ Return pesan yang sudah didekode lengkap
- ✅ Bekerja dengan format input binary valid apapun

---

## 🚀 Siap Memulai?

Kenakan topi decoder Anda dan mulai crack pesan binary tersebut! Ingat untuk test function Anda dengan berbagai input untuk memastikan berfungsi dengan benar pada berbagai panjang dan konten pesan.

Good luck, Agent! 🎯
