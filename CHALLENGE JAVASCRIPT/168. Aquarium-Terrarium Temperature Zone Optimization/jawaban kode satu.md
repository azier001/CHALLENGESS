# 📊 Dokumentasi Fungsi `calculateOptimalZones`

## 🎯 Deskripsi

Fungsi `calculateOptimalZones` digunakan untuk menghitung nilai rata-rata (mean) dari setiap array pembacaan suhu. Fungsi ini akan membalik urutan pembacaan suhu terlebih dahulu menggunakan metode yang aman (tanpa mengubah data asli), kemudian menghitung rata-ratanya, dan membulatkan hasilnya hingga 2 angka desimal.

---

## 📝 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `temperatureReadings` | `Array<Array<Number>>` | Array dua dimensi yang berisi kumpulan pembacaan suhu. Setiap elemen adalah array yang berisi angka-angka suhu. |

---

## 🔄 Nilai Kembalian (Return Value)

**Tipe:** `Array<Number>`

Mengembalikan array yang berisi nilai rata-rata dari setiap set pembacaan suhu, dibulatkan hingga 2 angka desimal.

---

## 💻 Kode Fungsi

```javascript
function calculateOptimalZones(temperatureReadings) {
    // Iterasi setiap bagian (section) dari array pembacaan suhu
    return temperatureReadings.map(section => {
        
        // Balik urutan array suhu tanpa mengubah array asli
        // menggunakan slice() untuk membuat salinan terlebih dahulu
        const reversed = section.slice().reverse();
        
        // Hitung total dari semua nilai suhu
        const sum = reversed.reduce((acc, temp) => acc + temp, 0);
        
        // Hitung rata-rata dengan membagi total dengan jumlah data
        const mean = sum / reversed.length;
        
        // Bulatkan hasil rata-rata ke 2 angka desimal
        return Math.round(mean * 100) / 100;
    });
}
```

---

## 🔍 Cara Kerja

1. **Iterasi Data**: Fungsi menggunakan `map()` untuk memproses setiap array pembacaan suhu (section)
2. **Salinan Array**: Menggunakan `slice()` untuk membuat salinan array sebelum dibalik, sehingga data asli tetap aman
3. **Pembalikan Urutan**: Array salinan dibalik urutannya menggunakan `reverse()`
4. **Perhitungan Total**: Menggunakan `reduce()` untuk menjumlahkan semua nilai suhu
5. **Perhitungan Rata-rata**: Total dibagi dengan jumlah data untuk mendapatkan nilai mean
6. **Pembulatan**: Hasil rata-rata dibulatkan ke 2 angka desimal menggunakan `Math.round(mean * 100) / 100`

---

## 📊 Contoh Penggunaan

### Input

```javascript
const temperatureData = [
  [20, 22, 24, 23, 21],
  [18, 19, 20, 21],
  [25, 26, 27, 28, 29, 30]
];

const result = calculateOptimalZones(temperatureData);
console.log(result);
```

### Output

```javascript
[22, 19.5, 27.5]
```

### Penjelasan Output

| Index | Data Asli | Data Setelah Reverse | Perhitungan | Hasil |
|-------|-----------|---------------------|-------------|-------|
| 0 | `[20, 22, 24, 23, 21]` | `[21, 23, 24, 22, 20]` | (21+23+24+22+20) / 5 = 110 / 5 | 22 |
| 1 | `[18, 19, 20, 21]` | `[21, 20, 19, 18]` | (21+20+19+18) / 4 = 78 / 4 | 19.5 |
| 2 | `[25, 26, 27, 28, 29, 30]` | `[30, 29, 28, 27, 26, 25]` | (30+29+28+27+26+25) / 6 = 165 / 6 | 27.5 |

---

## 📋 Contoh Penggunaan Lainnya

### Contoh 1: Data Suhu Harian

```javascript
const suhuHarian = [
  [28, 30, 32, 31, 29],     // Senin
  [27, 29, 31, 30],         // Selasa
  [26, 28, 30, 29, 27, 26]  // Rabu
];

const rataRata = calculateOptimalZones(suhuHarian);
console.log(rataRata);
// Output: [30, 29.25, 27.67]
```

### Contoh 2: Data Suhu Ruangan

```javascript
const suhuRuangan = [
  [22.5, 23.1, 22.8],       // Ruang A
  [24.0, 24.5, 24.2, 24.1]  // Ruang B
];

const hasilRataRata = calculateOptimalZones(suhuRuangan);
console.log(hasilRataRata);
// Output: [22.8, 24.2]
```

---

## ✅ Keunggulan Implementasi

- **Aman untuk Data Asli**: Menggunakan `slice()` sebelum `reverse()` memastikan array asli tidak berubah
- **Kode Terstruktur**: Memisahkan perhitungan sum dan mean untuk meningkatkan keterbacaan
- **Mudah Dipahami**: Setiap langkah perhitungan ditulis dengan jelas dan terpisah
- **Presisi Tinggi**: Pembulatan 2 desimal memberikan hasil yang akurat dan konsisten

---

## ⚠️ Catatan Penting

- ✅ **Data Asli Aman**: Fungsi ini tidak mengubah array asli karena menggunakan `slice()` terlebih dahulu
- ⚠️ **Array Kosong**: Jika ada array kosong dalam input, fungsi akan menghasilkan `NaN` karena pembagian dengan 0
- ⚠️ **Validasi Data**: Pastikan semua elemen dalam array adalah angka yang valid
- ⚠️ **Array dengan 1 Elemen**: Fungsi tetap bisa bekerja dan akan mengembalikan nilai elemen tersebut

---

## 🧪 Testing

### Test Case 1: Array Normal

```javascript
const test1 = [[10, 20, 30]];
console.log(calculateOptimalZones(test1)); // [20]
```

### Test Case 2: Array dengan Desimal

```javascript
const test2 = [[10.5, 20.7, 30.3]];
console.log(calculateOptimalZones(test2)); // [20.5]
```

### Test Case 3: Multiple Sections

```javascript
const test3 = [
  [5, 10, 15],
  [100, 200, 300],
  [1, 2, 3, 4, 5]
];
console.log(calculateOptimalZones(test3)); // [10, 200, 3]
```

---

## 🔧 Perbandingan dengan Versi Sebelumnya

| Aspek | Versi Lama | Versi Baru |
|-------|-----------|-----------|
| Keamanan Data | ❌ Mengubah array asli | ✅ Tidak mengubah array asli |
| Keterbacaan | Baik | ✅ Lebih baik (terpisah sum & mean) |
| Performa | Cepat | Sedikit lebih lambat (karena slice) |
| Best Practice | Kurang | ✅ Mengikuti best practice |

---

## 📌 Use Case

Fungsi ini cocok digunakan untuk:
- 🌡️ **Monitoring Suhu**: Analisis data sensor suhu dari berbagai zona
- 📊 **Laporan Statistik**: Membuat ringkasan data suhu dalam bentuk rata-rata
- 🏠 **Smart Home**: Menghitung rata-rata suhu ruangan untuk sistem AC otomatis
- 🔬 **Penelitian**: Pengolahan data historis suhu untuk analisis tren
- 🏭 **Industri**: Monitoring suhu mesin atau proses produksi
- 🌾 **Pertanian**: Analisis suhu greenhouse atau area pertanian

---

## 💡 Tips Penggunaan

1. **Validasi Input**: Selalu cek apakah input adalah array yang valid sebelum memanggil fungsi
2. **Handle Edge Cases**: Tambahkan pengecekan untuk array kosong jika diperlukan
3. **Gunakan dengan Data Real-time**: Cocok untuk streaming data suhu dari sensor IoT
4. **Kombinasi dengan Visualisasi**: Hasil dapat langsung digunakan untuk membuat grafik atau chart
