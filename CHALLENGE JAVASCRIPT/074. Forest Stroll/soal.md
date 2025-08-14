# 🌲 Forest Stroll Challenge

## 📋 Gambaran Umum

**Tingkat Kesulitan:** `Easy`

Buat sebuah function yang mensimulasikan perjalanan menawan melalui hutan mistis, di mana setiap langkah membawa pertemuan baru dengan makhluk-makhluk hutan!

---

## 🎯 Deskripsi Challenge

Implementasikan function bernama **`forestStroll`** yang menerima parameter `n` dan mensimulasikan perjalanan damai melalui hutan. Selama perjalanan ini:

- Setiap **langkah** direpresentasikan oleh asterisk (`*`)
- **Pertemuan dengan hewan** direpresentasikan oleh huruf-huruf spesifik
- Jalur ditentukan oleh pola matematis berdasarkan nomor langkah

---

## 🐾 Aturan Pertemuan Hewan

Petualangan hutan Anda mengikuti pola pertemuan magis berikut:

| Kondisi Langkah | Hewan yang Ditemui | Symbol | Deskripsi |
|---|---|---|---|
| **Habis dibagi 3** | Rusa | `d` | 🦌 Penghuni hutan yang anggun |
| **Habis dibagi 5** | Kelinci | `r` | 🐰 Pelompat hutan yang cepat |
| **Habis dibagi 3 DAN 5** | Beruang | `b` | 🐻 Penjaga hutan yang perkasa |
| **Langkah lainnya** | Langkah biasa | `*` | ⭐ Berjalan dengan damai |

> **Catatan:** Ketika suatu langkah habis dibagi 3 dan 5 sekaligus (yaitu, habis dibagi 15), Anda bertemu beruang, yang mengambil alih pertemuan rusa dan kelinci.

---

## 🔧 Spesifikasi Function

### Function Signature
```javascript
function forestStroll(n)
```

### Parameter
- **`n`** *(integer)*: Jumlah total langkah yang diambil selama perjalanan hutan
  - Harus berupa integer positif
  - Merepresentasikan panjang perjalanan Anda

### Return Value
- **Type:** `string`
- **Content:** String yang merepresentasikan jalur lengkap petualangan hutan Anda
- **Format:** Setiap karakter merepresentasikan langkah (`*`) atau pertemuan hewan (`d`, `r`, atau `b`)

---

## 📝 Contoh

### Contoh 1: Perjalanan Singkat
```javascript
forestStroll(5)
// Output yang diharapkan: "*d**r"
// Langkah 1: * (tidak habis dibagi 3 atau 5)
// Langkah 2: * (tidak habis dibagi 3 atau 5) 
// Langkah 3: d (habis dibagi 3 - pertemuan rusa)
// Langkah 4: * (tidak habis dibagi 3 atau 5)
// Langkah 5: r (habis dibagi 5 - pertemuan kelinci)
```

### Contoh 2: Perjalanan Panjang
```javascript
forestStroll(15)
// Output yang diharapkan: "*d*r*d**rd**r*b"
// Pertemuan penting:
// Langkah 3, 6, 9, 12: rusa (d)
// Langkah 5, 10: kelinci (r) 
// Langkah 15: beruang (b) - habis dibagi 3 dan 5
```

---

## 💡 Petunjuk Implementasi

1. **Loop melalui langkah:** Iterasi dari 1 sampai `n` (inklusif)
2. **Cek pembagian:** Gunakan operator modulo (`%`) untuk menguji habis dibagi
3. **Urutan prioritas:** Ingat bahwa pertemuan beruang (habis dibagi 15) mengabaikan aturan rusa/kelinci individual
4. **String building:** Gabungkan karakter untuk membangun string jalur final

---

## 🎨 Representasi Visual

```
Langkah: 1  2  3  4  5  6  7  8  9  10 11 12 13 14 15
Jalur:   *  *  d  *  r  d  *  *  d  r  *  d  *  *  b
```

Selamat coding, dan nikmati petualangan hutan Anda! 🌟
