# 🍷 Memecahkan Rahasia Wine Collector

## 📋 Gambaran Umum Tantangan

**Tingkat Kesulitan:** `Mudah`

Buat sebuah function yang dapat memecahkan pesan rahasia terenkripsi dari seorang wine collector. Tantangan ini menggabungkan manipulasi string, konversi binary, dan decoding ASCII untuk mengungkap pesan tersembunyi.

---

## 🎯 Tujuan

Implementasikan function bernama `decodeWineCollectorSecret` yang memproses pesan terenkode dengan format campuran yang mengandung:
- **Kata-kata terbalik** (perlu dibalik kembali)
- **Angka binary** dengan prefix `#` (perlu konversi ke karakter ASCII)

---

## 🔧 Spesifikasi Function

### Function Signature
```javascript
function decodeWineCollectorSecret(text)
```

### Parameter
| Parameter | Type | Deskripsi |
|-----------|------|-----------|
| `text` | `string` | Input string yang berisi kata-kata terbalik dan angka binary yang diberi prefix "#" |

### Return Value
- **Type:** `string`
- **Deskripsi:** Pesan yang telah didecode secara lengkap

---

## 📖 Algoritma Decoding

Proses decoding mengikuti langkah-langkah berikut:

1. **🔄 Membalik Kata**: Identifikasi dan balik kata-kata yang terbalik dalam pesan
2. **🔢 Binary ke Decimal**: Konversi angka binary (dengan prefix `#`) ke format decimal
3. **📝 Decimal ke ASCII**: Transformasi angka decimal menjadi karakter ASCII yang sesuai

---

## 💡 Contoh

### Input
```
"yenw yessalm #01001000 #01100101 #01101100 #01101100 #01101111"
```

### Langkah-langkah Pemrosesan
1. **Membalik kata:**
   - `yenw` → `wine`
   - `yessalm` → `malmsey`

2. **Konversi binary ke decimal:**
   - `#01001000` → `72`
   - `#01100101` → `101`
   - `#01101100` → `108`
   - `#01101100` → `108`
   - `#01101111` → `111`

3. **Konversi decimal ke ASCII:**
   - `72` → `H`
   - `101` → `e`
   - `108` → `l`
   - `108` → `l`
   - `111` → `o`

### Output
```
"wine malmsey Hello"
```

---

## 🎨 Tips Implementasi

- Split input string untuk memproses token individual
- Gunakan metode pembalikan string untuk kata-kata terbalik
- Implementasikan konversi binary-ke-decimal untuk token dengan prefix `#`
- Gunakan function konversi ASCII untuk mendapatkan karakter dari nilai decimal
- Gabungkan semua elemen yang diproses dengan spasi

---

## 🏆 Kriteria Keberhasilan

Function Anda harus berhasil:
- ✅ Mengidentifikasi dan membalik semua kata terbalik
- ✅ Mendeteksi angka binary dengan prefix `#`
- ✅ Mengkonversi binary ke decimal dengan benar
- ✅ Mentransformasi decimal ke karakter ASCII
- ✅ Mengembalikan pesan yang didecode secara lengkap sebagai string

---

## 🔍 Edge Cases yang Perlu Dipertimbangkan

- Input string kosong
- String yang hanya berisi kata-kata terbalik
- String yang hanya berisi angka binary
- Skenario mixed case
- Format binary yang tidak valid

---

*Selamat memecahkan rahasia wine collector! 🍾*
