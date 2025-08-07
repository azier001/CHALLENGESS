# 🚕 Dokumentasi Fungsi `calculateCabFare`

## 📋 Deskripsi

Fungsi `calculateCabFare` adalah sebuah kalkulator tarif taksi yang menghitung total biaya perjalanan berdasarkan jarak tempuh dan tarif dasar. Fungsi ini menggunakan sistem tarif berbasis jarak dengan biaya tetap Rp 10.000 per kilometer, ditambah dengan tarif dasar yang dapat disesuaikan.

## 🔧 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `distances` | `Array<number>` | Array berisi jarak-jarak perjalanan dalam kilometer |
| `baseFare` | `number` | Tarif dasar taksi (dalam rupiah atau mata uang lainnya) |

## 💰 Sistem Tarif

- **Tarif per kilometer**: Rp 10.000
- **Tarif dasar**: Sesuai parameter yang diberikan
- **Total tarif**: (Total jarak × Rp 10.000) + Tarif dasar

## 📝 Kode Fungsi

```javascript
function calculateCabFare(distances, baseFare) {
  // Membalik urutan array jarak
  const reversedDistances = distances.reverse();
  
  // Menjumlahkan semua jarak untuk mendapatkan total jarak yang ditempuh
  const totalDistance = reversedDistances.reduce((sum, distance) => sum + distance, 0);
  
  // Menghitung tarif berdasarkan jarak (Rp 10.000 per kilometer)
  const distanceBasedFare = totalDistance * 10;
  
  // Menghitung total tarif dengan menambahkan tarif jarak dan tarif dasar
  const totalFare = distanceBasedFare + baseFare;
  
  return totalFare;
}
```

## 🎯 Cara Penggunaan

### Contoh 1: Perjalanan Sederhana
```javascript
const jarak = [5, 3, 2]; // 5km, 3km, 2km
const tarifDasar = 15000; // Rp 15.000

const totalBiaya = calculateCabFare(jarak, tarifDasar);
console.log(`Total biaya: Rp ${totalBiaya.toLocaleString()}`);
```

**Output:**
```
Total biaya: Rp 115.000
```

**Penjelasan Perhitungan:**
- Total jarak: 5 + 3 + 2 = 10 km
- Tarif jarak: 10 × 10.000 = Rp 100.000
- Total tarif: Rp 100.000 + Rp 15.000 = Rp 115.000

### Contoh 2: Perjalanan Panjang
```javascript
const jarak = [12, 8, 5, 3]; // Multiple stops
const tarifDasar = 20000; // Rp 20.000

const totalBiaya = calculateCabFare(jarak, tarifDasar);
console.log(`Total biaya: Rp ${totalBiaya.toLocaleString()}`);
```

**Output:**
```
Total biaya: Rp 300.000
```

**Penjelasan Perhitungan:**
- Total jarak: 12 + 8 + 5 + 3 = 28 km
- Tarif jarak: 28 × 10.000 = Rp 280.000
- Total tarif: Rp 280.000 + Rp 20.000 = Rp 300.000

### Contoh 3: Perjalanan Singkat
```javascript
const jarak = [2.5, 1.5]; // Jarak pendek
const tarifDasar = 10000; // Rp 10.000

const totalBiaya = calculateCabFare(jarak, tarifDasar);
console.log(`Total biaya: Rp ${totalBiaya.toLocaleString()}`);
```

**Output:**
```
Total biaya: Rp 50.000
```

**Penjelasan Perhitungan:**
- Total jarak: 2.5 + 1.5 = 4 km
- Tarif jarak: 4 × 10.000 = Rp 40.000
- Total tarif: Rp 40.000 + Rp 10.000 = Rp 50.000

## ⚠️ Catatan Penting

1. **Modifikasi Array**: Fungsi ini menggunakan `reverse()` yang akan mengubah array asli. Jika Anda ingin mempertahankan urutan array asli, salin array terlebih dahulu:
   ```javascript
   const reversedDistances = [...distances].reverse();
   ```

2. **Validasi Input**: Pastikan:
   - Array `distances` berisi angka positif
   - Parameter `baseFare` adalah angka positif
   - Array tidak kosong

3. **Desimal**: Fungsi mendukung jarak dalam bentuk desimal (contoh: 2.5 km)

## 🔍 Contoh Penggunaan dengan Validasi

```javascript
function calculateCabFareWithValidation(distances, baseFare) {
    // Validasi input
    if (!Array.isArray(distances) || distances.length === 0) {
        throw new Error("Distances harus berupa array yang tidak kosong");
    }
    
    if (baseFare < 0) {
        throw new Error("Tarif dasar tidak boleh negatif");
    }
    
    if (distances.some(distance => distance < 0)) {
        throw new Error("Jarak tidak boleh negatif");
    }
    
    // Salin array untuk menghindari modifikasi array asli
    const distancesCopy = [...distances];
    
    return calculateCabFare(distancesCopy, baseFare);
}

// Contoh penggunaan
try {
    const hasil = calculateCabFareWithValidation([10, 5], 25000);
    console.log(`Tarif total: Rp ${hasil.toLocaleString()}`);
} catch (error) {
    console.error(error.message);
}
```

## 📊 Tabel Contoh Tarif

| Total Jarak (km) | Tarif Dasar (Rp) | Tarif Jarak (Rp) | Total (Rp) |
|------------------|-------------------|-------------------|------------|
| 3 | 10.000 | 30.000 | 40.000 |
| 5 | 15.000 | 50.000 | 65.000 |
| 10 | 20.000 | 100.000 | 120.000 |
| 15 | 25.000 | 150.000 | 175.000 |
| 20 | 30.000 | 200.000 | 230.000 |
| 25 | 35.000 | 250.000 | 285.000 |

## 🧮 Formula Perhitungan

```
Total Tarif = (Σ Jarak × 10.000) + Tarif Dasar

Dimana:
- Σ Jarak = Jumlah total semua jarak dalam array
- 10.000 = Tarif per kilometer (dalam rupiah)
- Tarif Dasar = Parameter baseFare yang diberikan
```

## 💡 Tips Penggunaan

1. **Untuk Jarak Desimal**: Gunakan angka desimal untuk jarak yang lebih presisi
   ```javascript
   const jarakPresisi = [2.3, 4.7, 1.2];
   ```

2. **Multiple Stops**: Array distances cocok untuk perjalanan dengan beberapa pemberhentian
   ```javascript
   const perjalananMultiStop = [5, 2, 3, 1, 4]; // 5 segmen perjalanan
   ```

3. **Monitoring Biaya**: Gunakan untuk estimasi biaya sebelum perjalanan
   ```javascript
   const estimasiBiaya = calculateCabFare([8, 3], 15000);
   ```

---

*Dokumentasi ini dibuat untuk membantu pemula memahami cara kerja fungsi `calculateCabFare` dalam menghitung tarif taksi berdasarkan jarak tempuh.*
