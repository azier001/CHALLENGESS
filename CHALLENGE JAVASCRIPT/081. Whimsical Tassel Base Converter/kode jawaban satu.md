# 🎓 Tassel Base Converter

Fungsi JavaScript untuk mengkonversi angka desimal ke sistem bilangan yang berbeda berdasarkan warna tassel (rumbai) yang dipilih.

## 📋 Deskripsi

`tasselBaseConverter` adalah fungsi yang mengubah angka desimal menjadi sistem bilangan lain (binary, hexadecimal, atau octal) berdasarkan warna tassel yang dipilih sebagai parameter. Fungsi ini menggunakan pendekatan object mapping untuk menentukan basis konversi yang lebih efisien dibanding switch-case.

## 🎯 Parameter

| Parameter | Tipe | Deskripsi | Wajib |
|-----------|------|-----------|-------|
| `tasselColor` | String | Warna tassel yang menentukan basis konversi | ✅ |
| `number` | String/Number | Angka yang akan dikonversi | ✅ |

## 🎨 Tabel Warna Tassel

| Warna | Basis | Sistem Bilangan | Format Output |
|-------|-------|-----------------|---------------|
| `"red"` | 2 | Binary | String angka 0 dan 1 |
| `"blue"` | 16 | Hexadecimal | String huruf kapital A-F dan angka 0-9 |
| `"green"` | 8 | Octal | String angka 0-7 |
| Lainnya | - | Error | `undefined` |

## 💻 Kode Fungsi

```javascript
function tasselBaseConverter(tasselColor, number) {
  // Object mapping untuk menentukan basis konversi berdasarkan warna
  const colorToBase = {
    "red": 2,      // Binary (basis 2)
    "blue": 16,    // Hexadecimal (basis 16)
    "green": 8     // Octal (basis 8)
  };
  
  // Ambil basis konversi dari object mapping
  const base = colorToBase[tasselColor];
  
  // Konversi parameter number ke integer dengan basis 10
  const decimalNumber = parseInt(number, 10);
  
  // Kondisi khusus untuk hexadecimal agar menghasilkan huruf kapital
  if (base === 16) {
    return decimalNumber.toString(base).toUpperCase();
  } else {
    // Untuk binary dan octal, langsung konversi tanpa uppercase
    return decimalNumber.toString(base);
  }
}
```

## 🚀 Contoh Penggunaan

```javascript
// Contoh konversi ke binary (merah)
console.log(tasselBaseConverter("red", 10));
// Output: "1010"

// Contoh konversi ke hexadecimal (biru)
console.log(tasselBaseConverter("blue", 255));
// Output: "FF"

// Contoh konversi ke octal (hijau)
console.log(tasselBaseConverter("green", 64));
// Output: "100"

// Contoh input warna yang tidak valid
console.log(tasselBaseConverter("yellow", 10));
// Output: "NaN" (karena base undefined)

// Contoh dengan input string angka
console.log(tasselBaseConverter("red", "42"));
// Output: "101010"
```

## 📊 Contoh Output Lengkap

| Input Number | Red (Binary) | Blue (Hexadecimal) | Green (Octal) |
|--------------|--------------|-------------------|---------------|
| 8 | "1000" | "8" | "10" |
| 15 | "1111" | "F" | "17" |
| 32 | "100000" | "20" | "40" |
| 100 | "1100100" | "64" | "144" |
| 255 | "11111111" | "FF" | "377" |

## 🔧 Keunggulan Implementasi

### ✨ **Object Mapping vs Switch-Case**
- **Lebih ringkas**: Tidak perlu menulis banyak case
- **Mudah diperluas**: Tinggal tambah property baru di object
- **Performa lebih baik**: O(1) lookup time
- **Lebih readable**: Struktur data terpisah dari logic

### 🎯 **parseInt dengan Basis 10**
```javascript
// Lebih eksplisit dan aman
const decimalNumber = parseInt(number, 10);

// vs versi sebelumnya yang bisa ambigu
const num = parseInt(number); // basis bisa auto-detect
```

## ⚠️ Catatan Penting

1. **Parameter `number`**: Menggunakan `parseInt(number, 10)` untuk memastikan parsing dalam basis desimal
2. **Case Sensitive**: Warna tassel harus ditulis dalam huruf kecil (`"red"`, `"blue"`, `"green"`)
3. **Hexadecimal**: Output hexadecimal selalu dalam huruf kapital karena kondisi khusus `base === 16`
4. **Error Handling**: Jika warna tidak dikenali, `base` akan `undefined` dan hasil konversi menjadi `"NaN"`
5. **Object Lookup**: Menggunakan bracket notation `colorToBase[tasselColor]` untuk akses dinamis

## 🐛 Handling Edge Cases

```javascript
// Input warna tidak valid
tasselBaseConverter("purple", 10);  // Output: "NaN"

// Input angka tidak valid
tasselBaseConverter("red", "abc");  // Output: "NaN"

// Input angka negatif
tasselBaseConverter("red", -10);    // Output: "-1010"

// Input angka decimal
tasselBaseConverter("blue", 10.5);  // Output: "A" (parseInt memotong decimal)
```

## 🎓 Penjelasan untuk Pemula

Fungsi ini seperti mesin konverter yang bekerja dengan cara:

1. **Membuat peta warna**: Object `colorToBase` seperti kamus yang menerjemahkan warna ke angka basis
2. **Mencari basis**: Fungsi "membaca" kamus untuk tahu basis konversi apa yang harus digunakan
3. **Konversi angka**: Mengubah input menjadi integer desimal terlebih dahulu
4. **Pengecekan khusus**: Kalau hasilnya hexadecimal, hurufnya dibuat kapital
5. **Mengembalikan hasil**: String hasil konversi

**Analogi sederhana**: Seperti punya mesin translator yang bisa mengubah angka biasa jadi "bahasa komputer" berbeda-beda. Kamu tinggal pilih tombol warna, masukkan angka, dan mesin akan otomatis tahu harus translate ke bahasa apa!

## 🔗 Sistem Bilangan yang Didukung

- **Binary (Basis 2)**: Hanya menggunakan angka 0 dan 1
- **Octal (Basis 8)**: Menggunakan angka 0 sampai 7  
- **Hexadecimal (Basis 16)**: Menggunakan angka 0-9 dan huruf A-F

## 🚨 Perbedaan dari Versi Sebelumnya

| Aspek | Versi Lama (Switch-Case) | Versi Baru (Object Mapping) |
|-------|-------------------------|------------------------------|
| **Struktur** | Switch-case panjang | Object mapping ringkas |
| **Error Handling** | Return string error | Return "NaN" |
| **Ekstensibilitas** | Tambah case baru | Tambah property object |
| **Performance** | O(n) untuk n cases | O(1) lookup |
| **Readability** | Logic dan data tercampur | Data terpisah dari logic |
