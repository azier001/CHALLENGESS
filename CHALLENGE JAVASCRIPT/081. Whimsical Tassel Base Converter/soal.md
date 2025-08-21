# 🎨 Whimsical Tassel Base Converter

## 📋 Ringkasan Challenge

**Level Kesulitan:** `Easy` 🟢

Buat sebuah function yang mengkonversi bilangan desimal ke base yang berbeda berdasarkan warna tassel yang ajaib! Setiap warna tassel merepresentasikan sistem bilangan yang unik, menjadikan ini perjalanan penuh warna melalui konversi base yang berbeda.

---

## 🎯 Spesifikasi Function

### Nama Function
```javascript
tasselBaseConverter(tasselColor, number)
```

### 🌈 Pemetaan Warna Tassel

Warna tassel menentukan target base untuk konversi:

| Warna Tassel | Sistem Base | Nomor Base |
|--------------|-------------|------------|
| 🔴 **red**   | Binary      | Base 2     |
| 🔵 **blue**  | Hexadecimal | Base 16    |
| 🟢 **green** | Octal       | Base 8     |

---

## 📝 Parameter

### `tasselColor` (string)
- **Deskripsi:** Warna tassel yang menentukan target base
- **Nilai Valid:** 
  - `"red"` - untuk konversi binary
  - `"blue"` - untuk konversi hexadecimal  
  - `"green"` - untuk konversi octal
- **Type:** String

### `number` (string)
- **Deskripsi:** Bilangan desimal yang akan dikonversi
- **Range:** 0 sampai 10,000 (inklusif)
- **Type:** String
- **Format:** Representasi desimal

---

## 📤 Return Value

- **Type:** String
- **Deskripsi:** Bilangan yang telah dikonversi dalam base yang sesuai dengan `tasselColor`
- **Format:** Representasi string dari bilangan dalam target base

---

## 💡 Contoh

```javascript
// Konversi Binary (tassel red)
tasselBaseConverter("red", "10")    // Returns: "1010"
tasselBaseConverter("red", "255")   // Returns: "11111111"

// Konversi Hexadecimal (tassel blue)
tasselBaseConverter("blue", "255")  // Returns: "ff"
tasselBaseConverter("blue", "4096") // Returns: "1000"

// Konversi Octal (tassel green)
tasselBaseConverter("green", "64")  // Returns: "100"
tasselBaseConverter("green", "512") // Returns: "1000"
```

---

## ✨ Fitur Utama

- 🎨 **Pemilihan base berdasarkan warna** - Pemetaan intuitif dari warna ke sistem bilangan
- 🔢 **Support multiple base** - Konversi Binary, Octal, dan Hexadecimal
- 📊 **Support range luas** - Menangani bilangan dari 0 sampai 10,000
- 🎯 **Interface sederhana** - Function yang mudah digunakan dengan parameter yang jelas

---

## 🚀 Memulai

1. Implementasikan function `tasselBaseConverter`
2. Handle ketiga warna tassel: red, blue, dan green
3. Konversi input desimal ke base yang sesuai
4. Return hasil sebagai string
5. Test dengan berbagai kombinasi input!

> **Catatan:** Challenge ini fokus pada pemahaman sistem base bilangan yang berbeda sambil menambahkan sentuhan whimsical dengan tassel berwarna-warni! 🎭
