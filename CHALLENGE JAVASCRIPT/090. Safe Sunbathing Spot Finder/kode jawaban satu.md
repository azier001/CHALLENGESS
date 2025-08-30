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
| > 0 (1-2) | ⚠️ Hati-hati | `"Be cautious!"` | Ada laba-laba, tetap waspada |
| = 0 | ✅ Aman | *Cek suhu* | Tidak ada laba-laba, evaluasi berdasarkan suhu |

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
  // Periksa apakah jumlah laba-laba terlalu banyak (≥3)
  if (spiderCount >= 3) {
    return "Find another spot!";
  } 
  // Periksa apakah ada laba-laba (>0)
  else if (spiderCount > 0) {
    return "Be cautious!";
  } 
  // Periksa apakah suhu terlalu panas (>30°C)
  else if (temperature > 30) {
    return "Too hot!";
  } 
  // Periksa apakah suhu terlalu dingin (<25°C)
  else if (temperature < 25) {
    return "Too cold!";
  } 
  // Kondisi ideal: tidak ada laba-laba dan suhu 25-30°C
  else {
    return "Perfect spot!";
  }
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
console.log(sunbathingSpot(27, 1)); 
// Output: "Be cautious!"
// Alasan: Terdapat 1 laba-laba (>0), suhu diabaikan
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

### Contoh 6: Batas Suhu Maksimal
```javascript
console.log(sunbathingSpot(30, 0)); 
// Output: "Perfect spot!"
// Alasan: Tidak ada laba-laba, suhu tepat 30°C (masih dalam rentang ideal)
```

### Contoh 7: Batas Suhu Minimal
```javascript
console.log(sunbathingSpot(25, 0)); 
// Output: "Perfect spot!"
// Alasan: Tidak ada laba-laba, suhu tepat 25°C (masih dalam rentang ideal)
```

---

## ⚡ Alur Logika Fungsi

1. **Cek Laba-laba Berbahaya**: Jika `spiderCount ≥ 3` → `"Find another spot!"`
2. **Cek Ada Laba-laba**: Jika `spiderCount > 0` → `"Be cautious!"`
3. **Cek Suhu Panas**: Jika `temperature > 30` → `"Too hot!"`
4. **Cek Suhu Dingin**: Jika `temperature < 25` → `"Too cold!"`
5. **Kondisi Ideal**: Semua kondisi lain → `"Perfect spot!"`

---

## 📝 Catatan Penting

- **Prioritas Evaluasi**: Fungsi ini menggunakan struktur `if-else if-else` yang memeriksa kondisi secara berurutan
- **Rentang Suhu Ideal**: 25°C hingga 30°C (inklusif kedua batas)
- **Toleransi Laba-laba**: Hanya 0 laba-laba yang memberikan kemungkinan hasil "Perfect spot!"
- **Return Type**: Fungsi ini selalu mengembalikan string
- **Edge Cases**: Nilai suhu tepat 25°C dan 30°C masih dianggap ideal

---

## 🚀 Cara Implementasi

1. **Impor atau salin fungsi** ke dalam project JavaScript Anda
2. **Panggil fungsi** dengan parameter suhu dan jumlah laba-laba
3. **Gunakan output** untuk membuat keputusan tentang lokasi berjemur

```javascript
// Contoh implementasi dalam aplikasi sederhana
function checkLocation() {
  const currentTemp = 28;
  const spidersFound = 0;
  
  const recommendation = sunbathingSpot(currentTemp, spidersFound);
  console.log(`🌞 Rekomendasi: ${recommendation}`);
  
  // Tambahkan logika aplikasi berdasarkan rekomendasi
  if (recommendation === "Perfect spot!") {
    console.log("✅ Ayo mulai berjemur!");
  }
}

checkLocation();
```

---

## 🧪 Testing

Untuk memastikan fungsi bekerja dengan benar, Anda dapat menjalankan test cases berikut:

```javascript
// Test case untuk semua skenario
const testCases = [
  { temp: 28, spiders: 5, expected: "Find another spot!" },
  { temp: 27, spiders: 1, expected: "Be cautious!" },
  { temp: 27, spiders: 0, expected: "Perfect spot!" },
  { temp: 35, spiders: 0, expected: "Too hot!" },
  { temp: 20, spiders: 0, expected: "Too cold!" },
  { temp: 25, spiders: 0, expected: "Perfect spot!" },
  { temp: 30, spiders: 0, expected: "Perfect spot!" }
];

// Jalankan semua test cases
testCases.forEach((test, index) => {
  const result = sunbathingSpot(test.temp, test.spiders);
  const status = result === test.expected ? "✅ PASS" : "❌ FAIL";
  console.log(`Test ${index + 1}: ${status} - ${result}`);
});
```

---

*Dokumentasi ini dibuat untuk membantu developer memahami dan menggunakan fungsi `sunbathingSpot` dengan mudah dan efektif.*
