# 🎓 Tassel Base Converter

Fungsi JavaScript untuk mengkonversi angka desimal ke sistem bilangan yang berbeda berdasarkan warna tassel (rumbai) yang dipilih.

## 📋 Deskripsi

`tasselBaseConverter` adalah fungsi yang mengubah angka desimal menjadi sistem bilangan lain (binary, hexadecimal, atau octal) berdasarkan warna tassel yang dipilih sebagai parameter. Fungsi ini menggunakan konsep warna sebagai penanda untuk menentukan basis konversi yang diinginkan.

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
| Lainnya | - | Error | "Invalid tassel color" |

## 💻 Kode Fungsi

```javascript
function tasselBaseConverter(tasselColor, number) {
    // Konversi parameter number ke integer
    const num = parseInt(number);
    
    // Switch case berdasarkan warna tassel
    switch (tasselColor) {
        case "red":
            // Konversi ke binary (basis 2)
            return num.toString(2);    
            
        case "blue":
            // Konversi ke hexadecimal (basis 16) dengan huruf kapital
            return num.toString(16).toUpperCase();   
            
        case "green":
            // Konversi ke octal (basis 8)
            return num.toString(8);    
            
        default:
            // Pesan error untuk warna yang tidak valid
            return "Invalid tassel color";
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

// Contoh input yang tidak valid
console.log(tasselBaseConverter("yellow", 10));
// Output: "Invalid tassel color"
```

## 📊 Contoh Output Lengkap

| Input Number | Red (Binary) | Blue (Hexadecimal) | Green (Octal) |
|--------------|--------------|-------------------|---------------|
| 8 | "1000" | "8" | "10" |
| 15 | "1111" | "F" | "17" |
| 32 | "100000" | "20" | "40" |
| 100 | "1100100" | "64" | "144" |
| 255 | "11111111" | "FF" | "377" |

## ⚠️ Catatan Penting

1. **Parameter `number`**: Fungsi menggunakan `parseInt()` untuk mengkonversi input menjadi integer, jadi bisa menerima string maupun number
2. **Case Sensitive**: Warna tassel harus ditulis dalam huruf kecil (`"red"`, `"blue"`, `"green"`)
3. **Hexadecimal**: Output hexadecimal selalu dalam huruf kapital karena menggunakan `.toUpperCase()`
4. **Error Handling**: Jika warna tassel tidak dikenali, akan mengembalikan pesan error

## 🎓 Penjelasan untuk Pemula

Fungsi ini seperti mesin konverter yang:

1. **Menerima dua input**: warna tassel dan angka
2. **Memproses**: Mengubah angka dari sistem desimal (basis 10) ke sistem lain
3. **Mengembalikan**: Hasil konversi dalam bentuk string

**Analogi sederhana**: Bayangkan kamu punya kalkulator ajaib yang bisa mengubah angka biasa menjadi "bahasa" komputer yang berbeda-beda, tergantung tombol warna yang kamu tekan!

## 🔗 Sistem Bilangan yang Didukung

- **Binary (Basis 2)**: Hanya menggunakan angka 0 dan 1
- **Octal (Basis 8)**: Menggunakan angka 0 sampai 7  
- **Hexadecimal (Basis 16)**: Menggunakan angka 0-9 dan huruf A-F
