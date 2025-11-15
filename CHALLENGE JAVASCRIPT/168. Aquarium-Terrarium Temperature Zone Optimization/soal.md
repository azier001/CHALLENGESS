# 🌡️ Aquarium-Terrarium Temperature Zone Optimization

## 📊 Tingkat Challenge
**Medium** ⭐⭐

---

## 🎯 Deskripsi Masalah

Anda sedang menyiapkan tampilan aquarium-terrarium campuran dengan beberapa seksi habitat, masing-masing dipantau oleh sensor suhu. Tugas Anda adalah memproses data sensor untuk memastikan keseimbangan lingkungan yang optimal di semua habitat.

Buatlah sebuah function **`calculateOptimalZones`** yang menganalisis pembacaan suhu dari berbagai seksi habitat dan mengembalikan rata-rata matematis dari setiap array suhu yang telah dibalik.

---

## 🔧 Spesifikasi Function

### Nama Function
```javascript
calculateOptimalZones(temperatureReadings)
```

### Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `temperatureReadings` | `Array<Array<number>>` | Array 2D dimana setiap sub-array berisi pembacaan suhu dari seksi habitat |

**Contoh Input:**
```javascript
[
  [20.5, 21.0, 22.3, 23.1],
  [25.0, 26.5, 27.2],
  [19.8, 20.1, 21.5, 22.0, 22.8]
]
```

### Return

**Tipe:** `Array<number>`

Sebuah array berisi rata-rata suhu untuk setiap seksi setelah dibalik, dibulatkan hingga 2 desimal.

**Contoh Output:**
```javascript
[23.45, 26.78, 21.33]
```

---

## 📋 Logika Pemrosesan

Function harus melakukan langkah-langkah berikut:

1. **🔄 Membalik Setiap Array Suhu**
   - Gunakan algoritma pembalikan yang optimal
   - Proses pembacaan setiap seksi habitat secara independen

2. **🧮 Menghitung Rata-rata Matematis**
   - Hitung rata-rata dari setiap array yang telah dibalik
   - Formula: `mean = jumlah semua nilai / jumlah data`

3. **✨ Format Hasil**
   - Bulatkan setiap mean hingga **2 desimal**
   - Return sebagai array berisi angka

---

## 💡 Contoh Penjelasan Langkah demi Langkah

### Input:
```javascript
temperatureReadings = [
  [20.0, 21.0, 22.0],
  [25.0, 26.0, 27.0, 28.0]
]
```

### Proses Step-by-Step:

#### Seksi 1: `[20.0, 21.0, 22.0]`
- **Reversed:** `[22.0, 21.0, 20.0]`
- **Mean:** `(22.0 + 21.0 + 20.0) / 3 = 21.00`

#### Seksi 2: `[25.0, 26.0, 27.0, 28.0]`
- **Reversed:** `[28.0, 27.0, 26.0, 25.0]`
- **Mean:** `(28.0 + 27.0 + 26.0 + 25.0) / 4 = 26.50`

### Output:
```javascript
[21.00, 26.50]
```

---

## ✅ Checklist Persyaratan

- [ ] Membalik setiap array suhu secara efisien
- [ ] Menghitung mean matematis yang akurat untuk setiap seksi
- [ ] Membulatkan hasil hingga tepat 2 desimal
- [ ] Return hasil sebagai array berisi angka
- [ ] Menangani array kosong dengan tepat (jika diperlukan)

---

## 🚀 Memulai

```javascript
function calculateOptimalZones(temperatureReadings) {
  // Implementasi Anda di sini
}

// Test function Anda
const readings = [
  [20.5, 21.0, 22.3, 23.1],
  [25.0, 26.5, 27.2],
  [19.8, 20.1, 21.5, 22.0, 22.8]
];

console.log(calculateOptimalZones(readings));
// Expected output: [23.45, 26.78, 21.33]
```

---

## 🏆 Kriteria Keberhasilan

Solusi Anda harus:
- ✨ Menghasilkan nilai mean yang benar untuk semua test case
- 🎯 Menangani array dengan panjang yang bervariasi
- 💯 Mempertahankan presisi dengan 2 desimal
- ⚡ Menggunakan teknik manipulasi array yang efisien

---

*Semoga berhasil dengan optimasi habitat Anda! 🐠🌿*
