# 📊 Dokumentasi Fungsi `calculateTripStats`

## 📝 Deskripsi

Fungsi `calculateTripStats` digunakan untuk menghitung statistik perjalanan berdasarkan data jarak tempuh harian (dalam mil). Fungsi ini akan menganalisis data dan memberikan informasi lengkap seperti total jarak, rata-rata jarak per hari, hari dengan jarak terbanyak, dan hari dengan jarak paling sedikit.

## 🎯 Kegunaan

Fungsi ini sangat berguna untuk:
- Menganalisis performa perjalanan harian
- Mengetahui hari dengan aktivitas tertinggi dan terendah
- Menghitung statistik perjalanan secara otomatis
- Membuat laporan perjalanan yang lebih informatif

---

## 📥 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `dailyMiles` | Array of Numbers | Array yang berisi data jarak tempuh harian dalam mil. Setiap elemen array merepresentasikan jarak yang ditempuh pada hari tertentu. |

### Contoh Parameter:
```javascript
[45, 60, 32, 78, 55] // Jarak tempuh 5 hari berturut-turut
```

---

## 📤 Output / Nilai Kembalian

Fungsi ini mengembalikan sebuah **objek** dengan properti berikut:

| Properti | Tipe | Deskripsi |
|----------|------|-----------|
| `totalMiles` | Number | Total keseluruhan jarak yang ditempuh selama perjalanan |
| `averageMiles` | Number | Rata-rata jarak tempuh per hari |
| `maxMilesDay` | Number | Index hari dengan jarak tempuh terbanyak (dimulai dari 0) |
| `minMilesDay` | Number | Index hari dengan jarak tempuh paling sedikit (dimulai dari 0) |
| `totalDays` | Number | Total jumlah hari dalam perjalanan |

---

## 💻 Code Fungsi

```javascript
function calculateTripStats(dailyMiles) {
  // Inisialisasi variabel untuk menyimpan total jarak
  let total = 0;
  
  // Menggunakan elemen pertama sebagai nilai awal untuk max dan min
  let maxMiles = dailyMiles[0];
  let minMiles = dailyMiles[0];
  let maxDay = 0;
  let minDay = 0;
  
  // Looping melalui setiap hari untuk menghitung statistik
  for (let i = 0; i < dailyMiles.length; i++) {
    // Menambahkan jarak hari ini ke total
    total += dailyMiles[i];
    
    // Mengecek apakah jarak hari ini lebih besar dari maksimal sebelumnya
    if (dailyMiles[i] > maxMiles) {
      maxMiles = dailyMiles[i];
      maxDay = i;
    }
    
    // Mengecek apakah jarak hari ini lebih kecil dari minimal sebelumnya
    if (dailyMiles[i] < minMiles) {
      minMiles = dailyMiles[i];
      minDay = i;
    }
  }
  
  // Menghitung rata-rata jarak per hari
  let average = total / dailyMiles.length;
  
  // Mengembalikan objek dengan semua statistik
  return {
    totalMiles: total,
    averageMiles: average,
    maxMilesDay: maxDay,
    minMilesDay: minDay,
    totalDays: dailyMiles.length
  };
}
```

---

## 🔍 Contoh Penggunaan

### Contoh 1: Perjalanan 5 Hari

```javascript
const perjalananMingguIni = [45, 60, 32, 78, 55];
const hasil = calculateTripStats(perjalananMingguIni);

console.log(hasil);
```

**Output:**
```javascript
{
  totalMiles: 270,
  averageMiles: 54,
  maxMilesDay: 3,
  minMilesDay: 2,
  totalDays: 5
}
```

**Penjelasan:**
- Total jarak: 270 mil (45 + 60 + 32 + 78 + 55)
- Rata-rata: 54 mil per hari (270 ÷ 5)
- Hari dengan jarak terbanyak: Hari ke-4 (index 3) dengan 78 mil
- Hari dengan jarak paling sedikit: Hari ke-3 (index 2) dengan 32 mil
- Total hari: 5 hari

---

### Contoh 2: Perjalanan 3 Hari

```javascript
const perjalananAkhirPekan = [120, 95, 110];
const statistik = calculateTripStats(perjalananAkhirPekan);

console.log(statistik);
```

**Output:**
```javascript
{
  totalMiles: 325,
  averageMiles: 108.33333333333333,
  maxMilesDay: 0,
  minMilesDay: 1,
  totalDays: 3
}
```

**Penjelasan:**
- Total jarak: 325 mil
- Rata-rata: ~108.33 mil per hari
- Hari dengan jarak terbanyak: Hari ke-1 (index 0) dengan 120 mil
- Hari dengan jarak paling sedikit: Hari ke-2 (index 1) dengan 95 mil
- Total hari: 3 hari

---

## ⚠️ Catatan Penting

1. **Index Array Dimulai dari 0**: Perhatikan bahwa `maxMilesDay` dan `minMilesDay` mengembalikan index array yang dimulai dari 0. Jadi hari pertama adalah index 0, hari kedua adalah index 1, dan seterusnya.

2. **Array Tidak Boleh Kosong**: Pastikan array `dailyMiles` minimal memiliki 1 elemen, karena fungsi ini menggunakan elemen pertama sebagai nilai awal.

3. **Tipe Data**: Pastikan semua elemen dalam array adalah angka (number) untuk menghindari hasil yang tidak diharapkan.

---

## 🎓 Tips untuk Pemula

- **Apa itu Array?** Array adalah kumpulan data yang disimpan dalam satu variabel. Dalam contoh ini, `[45, 60, 32]` adalah array dengan 3 angka.

- **Apa itu Index?** Index adalah posisi elemen dalam array. Posisi pertama memiliki index 0, bukan 1.

- **Cara Membaca Output**: Jika `maxMilesDay: 3`, artinya hari ke-4 (karena dimulai dari 0) memiliki jarak terbanyak.

---

## 📚 Referensi

- [MDN Web Docs - Arrays](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array)
- [MDN Web Docs - For Loop](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for)
- [MDN Web Docs - Objects](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)

---

**Dibuat dengan ❤️ untuk memudahkan analisis perjalanan Anda**
