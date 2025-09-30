# 🕯️ Banquet Binary Candles

## 📋 Ringkasan Challenge

**Tingkat Kesulitan:** `Easy`

Buat sebuah function yang menentukan berapa banyak lilin yang perlu dinyalakan untuk merepresentasikan angka desimal dalam format binary.

---

## 🎯 Objektif

Implementasikan function bernama `banquetBinaryCandles` yang menghitung jumlah lilin yang menyala untuk menampilkan angka desimal dalam representasi binary-nya.

---

## 💡 Konsep

Dalam representasi binary:
- **`1`** merepresentasikan **lilin yang menyala** 🕯️
- **`0`** merepresentasikan **lilin yang tidak menyala**

Challenge ini adalah menghitung berapa banyak `1` yang muncul dalam bentuk binary dari angka desimal.

### Contoh

```
Desimal: 13
Binary:  1101
Lilin Menyala: 3 (tiga '1')
```

---

## 🔧 Spesifikasi Function

### Nama Function
```javascript
banquetBinaryCandles(decimalCandles)
```

### Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `decimalCandles` | `number` | Angka desimal yang akan dikonversi ke format binary |

### Return Value

- **Tipe:** `number` (integer)
- **Deskripsi:** Jumlah lilin yang menyala (jumlah `1` dalam representasi binary)

---

## 📝 Langkah Implementasi

1. **Konversi** angka desimal ke format binary
2. **Hitung** jumlah `1` dalam representasi binary
3. **Return** hasil hitungan tersebut

---

## 🧪 Test Cases

| Input Desimal | Binary | Lilin Menyala | Output yang Diharapkan |
|---------------|--------|---------------|------------------------|
| 0 | 0 | 0 | `0` |
| 1 | 1 | 1 | `1` |
| 7 | 111 | 3 | `3` |
| 8 | 1000 | 1 | `1` |
| 15 | 1111 | 4 | `4` |
| 13 | 1101 | 3 | `3` |

---

## 💻 Contoh Penggunaan

```javascript
banquetBinaryCandles(13);  // Returns: 3
banquetBinaryCandles(7);   // Returns: 3
banquetBinaryCandles(8);   // Returns: 1
banquetBinaryCandles(0);   // Returns: 0
```

---

## 🔑 Poin Penting

- ✅ Function harus dapat menangani semua integer non-negatif
- ✅ Konversi binary adalah operasi inti
- ✅ Menghitung `1` sama dengan menghitung set bits
- ✅ Return value harus berupa integer

---

## 🚀 Petunjuk

- Pertimbangkan menggunakan method bawaan JavaScript `toString(2)` untuk konversi binary
- Method string dapat membantu menghitung kemunculan `'1'`
- Alternatifnya, eksplor operasi bitwise untuk solusi yang lebih optimal

---

**Selamat mengerjakan! 🎉**
