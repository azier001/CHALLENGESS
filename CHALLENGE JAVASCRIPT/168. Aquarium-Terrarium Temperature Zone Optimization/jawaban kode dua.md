# 📊 Dokumentasi Fungsi `calculateOptimalZones`

## 🎯 Deskripsi

Fungsi `calculateOptimalZones` digunakan untuk menghitung nilai rata-rata (mean) dari setiap array pembacaan suhu. Fungsi ini akan membalik urutan pembacaan suhu terlebih dahulu, kemudian menghitung rata-ratanya, dan membulatkan hasilnya hingga 2 angka desimal.

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
  // Iterasi setiap array pembacaan suhu
  return temperatureReadings.map(readings => {
    
    // Balik urutan array pembacaan suhu
    const reversed = readings.reverse();
    
    // Hitung total semua nilai suhu dan bagi dengan jumlah data untuk mendapat rata-rata
    const mean = reversed.reduce((sum, temp) => sum + temp, 0) / reversed.length;
    
    // Bulatkan hasil rata-rata ke 2 angka desimal
    return Math.round(mean * 100) / 100;
  });
}
```

---

## 🔍 Cara Kerja

1. **Iterasi Data**: Fungsi menggunakan `map()` untuk memproses setiap array pembacaan suhu
2. **Pembalikan Urutan**: Setiap array pembacaan dibalik urutannya menggunakan `reverse()`
3. **Perhitungan Rata-rata**: Menggunakan `reduce()` untuk menjumlahkan semua nilai, lalu dibagi dengan jumlah data
4. **Pembulatan**: Hasil rata-rata dibulatkan ke 2 angka desimal menggunakan `Math.round(mean * 100) / 100`

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
| 0 | `[20, 22, 24, 23, 21]` | `[21, 23, 24, 22, 20]` | (21+23+24+22+20) / 5 | 22 |
| 1 | `[18, 19, 20, 21]` | `[21, 20, 19, 18]` | (21+20+19+18) / 4 | 19.5 |
| 2 | `[25, 26, 27, 28, 29, 30]` | `[30, 29, 28, 27, 26, 25]` | (30+29+28+27+26+25) / 6 | 27.5 |

---

## ⚠️ Catatan Penting

- **Perubahan Data Asli**: Metode `reverse()` akan **mengubah array asli**. Jika Anda ingin mempertahankan data asli, sebaiknya buat salinan array terlebih dahulu.
- **Array Kosong**: Jika ada array kosong dalam input, fungsi akan menghasilkan `NaN` karena pembagian dengan 0.
- **Validasi Data**: Pastikan semua elemen dalam array adalah angka yang valid.

---

## 🛠️ Saran Perbaikan

Untuk menghindari perubahan pada data asli, Anda bisa menggunakan spread operator:

```javascript
function calculateOptimalZones(temperatureReadings) {
  return temperatureReadings.map(readings => {
    // Buat salinan array sebelum membalik urutan
    const reversed = [...readings].reverse();
    
    const mean = reversed.reduce((sum, temp) => sum + temp, 0) / reversed.length;
    
    return Math.round(mean * 100) / 100;
  });
}
```

---

## 📌 Use Case

Fungsi ini cocok digunakan untuk:
- 📈 Analisis data sensor suhu
- 🌡️ Monitoring zona suhu optimal
- 📊 Pengolahan data historis suhu
- 🔬 Penelitian yang memerlukan rata-rata pembacaan suhu
