# 🥾 Kalkulator Skor Performa Pendaki (Hiker's Performance Score Calculator)

> **Level Tantangan:** `Easy` 🟢

## 📋 Overview

Buat sebuah function bernama `calculateHikeScore` yang mensimulasikan pendakian melalui bukit-bukit bergelombang dan menghitung skor performa pendaki berdasarkan berbagai kriteria termasuk jumlah bukit yang didaki, jarak yang ditempuh, dan respons terhadap protokol keamanan.

## 🎯 Persyaratan Function

### Function Signature
```javascript
function calculateHikeScore(hills, distance, whistleResponse)
```

### Parameter

| Parameter | Type | Deskripsi |
|-----------|------|-----------|
| `hills` | `number` | Jumlah bukit yang didaki selama pendakian (non-negative integer) |
| `distance` | `number` | Total jarak pendakian dalam kilometer (non-negative number) |
| `whistleResponse` | `boolean` | Apakah pendaki merespons dengan benar peluit forest ranger |

### Return Value
- **Type:** `integer`
- **Deskripsi:** Skor performa akhir yang dihitung

## 🏆 Sistem Penilaian (Scoring System)

Performa pendaki dievaluasi menggunakan sistem penilaian komprehensif berikut:

### ✅ Reward Poin

- **🏔️ Base Score**
  - **+10 poin** untuk setiap bukit yang didaki
  
- **🚶 Distance Bonus**
  - **+5 poin** untuk setiap kilometer penuh yang didaki
  
- **📯 Ranger's Whistle Bonus**
  - **+50 poin** jika pendaki merespons dengan benar peluit (`true`)
  
- **💪 Endurance Bonus**
  - **+100 poin** jika lebih dari 10 bukit berhasil didaki

### ⚠️ Penalti

- **🚩 Short Hike Penalty**
  - **-20 poin** jika total jarak kurang dari 5 km

## 📝 Contoh Skenario

### Skenario 1: Performa Sangat Baik
- Hills: `15`
- Distance: `12.5 km`
- Whistle Response: `true`
- **Kalkulasi yang diharapkan:** Base (150) + Distance (60) + Whistle (50) + Endurance (100) = **360 poin**

### Skenario 2: Performa Rata-rata
- Hills: `8`
- Distance: `6.2 km`
- Whistle Response: `false`
- **Kalkulasi yang diharapkan:** Base (80) + Distance (30) = **110 poin**

### Skenario 3: Pendakian Pendek dengan Penalti
- Hills: `3`
- Distance: `3.8 km`
- Whistle Response: `true`
- **Kalkulasi yang diharapkan:** Base (30) + Distance (15) + Whistle (50) - Short Hike Penalty (20) = **75 poin**

## 🎨 Catatan Implementasi

- Gunakan `Math.floor()` untuk kalkulasi distance agar hanya menghitung kilometer penuh
- Pastikan penanganan yang tepat untuk nilai boolean pada whistle response
- Return skor akhir sebagai integer
- Pertimbangkan edge case dengan nilai nol

## 🚀 Getting Started

1. Define function dengan parameter yang diperlukan
2. Hitung base score dari jumlah bukit yang didaki
3. Tambahkan distance bonus untuk kilometer penuh
4. Periksa dan terapkan whistle response bonus
5. Terapkan endurance bonus jika berlaku
6. Terapkan short hike penalty jika berlaku
7. Return skor akhir yang telah dikalkulasi

---

**Happy coding!** 🎉
