# 🌞 Dokumentasi Fungsi `sunbathingSpot`

## 📋 Deskripsi Fungsi

Fungsi `sunbathingSpot` adalah sebuah utility function yang membantu menentukan apakah suatu lokasi cocok untuk berjemur berdasarkan dua faktor utama: **suhu** dan **jumlah laba-laba**. Fungsi ini sangat berguna untuk aktivitas outdoor seperti piknik, berjemur, atau sekadar duduk santai di luar ruangan.

Prioritas penilaian:
1. **Jumlah laba-laba** (prioritas utama)
2. **Suhu lingkungan** (prioritas kedua)

---

## 🔧 Parameter Fungsi

| Parameter | Tipe | Deskripsi | Rentang Nilai |
|-----------|------|-----------|---------------|
| `temperature` | `number` | Suhu dalam derajat Celsius | Semua nilai numerik |
| `spiderCount` | `number` | Jumlah laba-laba yang terlihat di lokasi | 0 atau lebih (bilangan bulat) |

---

## 🕷️ Tabel Kondisi Laba-laba

| Jumlah Laba-laba | Status | Output | Keterangan |
|------------------|--------|--------|------------|
| ≥ 3 | 🚫 Berbahaya | `"Find another spot!"` | Terlalu banyak laba-laba, cari tempat lain |
| 1-2 | ⚠️ Hati-hati | `"Be cautious!"` | Ada laba-laba, tetap waspada |
| 0 | ✅ Aman | *Cek suhu* | Tidak ada laba-laba, evaluasi berdasarkan suhu |

---

## 🌡️ Tabel Kondisi Suhu (Ketika Tidak Ada Laba-laba)

| Rentang Suhu | Status | Output | Keterangan |
|--------------|--------|--------|------------|
| > 30°C | 🔥 Terlalu Panas | `"Too hot!"` | Suhu terlalu tinggi untuk berjemur |
| < 25°C | 🧊 Terlalu Dingin | `"Too cold!"` | Suhu terlalu rendah untuk berjemur |
| 25-30°C | 🌟 Sempurna | `"Perfect spot!"` | Suhu ideal untuk berjemur |

---

## 💻 Kode Fungsi

```javascript
function sunbathingSpot(temperature, spiderCount) {
    // Jumlah laba-laba memiliki prioritas lebih tinggi daripada suhu
    if (spiderCount >= 3) {
        return "Find another spot!";
    }
    
    if (spiderCount >= 1) {
        return "Be cautious!";
    }
    
    // Periksa kondisi suhu ketika tidak ada laba-laba (spiderCount = 0)
    if (temperature > 30) {
        return "Too hot!";
    }
    
    if (temperature < 25) {
        return "Too cold!";
    }
    
    // Suhu antara 25-30°C (inklusif) dan tidak ada laba-laba
    return "Perfect spot!";
}
```

---

## 🎯 Contoh Penggunaan dan Output

### Contoh 1: Lokasi dengan Banyak Laba-laba
```javascript
console.log(sunbathingSpot(28, 5)); 
// Output: "Find another spot!"
// Alasan: Terdapat 5 laba-laba (≥3), suhu diabaikan
```

### Contoh 2: Lokasi dengan Sedikit Laba-laba
```javascript
console.log(sunbathingSpot(27, 2)); 
// Output: "Be cautious!"
// Alasan: Terdapat 2 laba-laba (1-2), suhu diabaikan
```

### Contoh 3: Lokasi Tanpa Laba-laba - Suhu Ideal
```javascript
console.log(sunbathingSpot(27, 0)); 
// Output: "Perfect spot!"
// Alasan: Tidak ada laba-laba, suhu 27°C (dalam rentang 25-30°C)
```

### Contoh 4: Lokasi Tanpa Laba-laba - Terlalu Panas
```javascript
console.log(sunbathingSpot(35, 0)); 
// Output: "Too hot!"
// Alasan: Tidak ada laba-laba, tetapi suhu 35°C (>30°C)
```

### Contoh 5: Lokasi Tanpa Laba-laba - Terlalu Dingin
```javascript
console.log(sunbathingSpot(20, 0)); 
// Output: "Too cold!"
// Alasan: Tidak ada laba-laba, tetapi suhu 20°C (<25°C)
```

---

## 🔍 Catatan Penting

- **Prioritas Evaluasi**: Fungsi ini selalu memeriksa jumlah laba-laba terlebih dahulu sebelum mempertimbangkan suhu
- **Rentang Suhu Ideal**: 25°C hingga 30°C (inklusif)
- **Toleransi Laba-laba**: Maksimal 0 laba-laba untuk mendapatkan hasil "Perfect spot!"
- **Return Type**: Fungsi ini selalu mengembalikan string

---

## 🚀 Cara Implementasi

1. **Impor atau salin fungsi** ke dalam project JavaScript Anda
2. **Panggil fungsi** dengan parameter suhu dan jumlah laba-laba
3. **Gunakan output** untuk membuat keputusan tentang lokasi berjemur

```javascript
// Contoh implementasi dalam aplikasi
const currentTemp = 28;
const spidersFound = 0;

const recommendation = sunbathingSpot(currentTemp, spidersFound);
console.log(`Rekomendasi: ${recommendation}`);
```

---

*Dokumentasi ini dibuat untuk membantu developer memahami dan menggunakan fungsi `sunbathingSpot` dengan mudah dan efektif.*
