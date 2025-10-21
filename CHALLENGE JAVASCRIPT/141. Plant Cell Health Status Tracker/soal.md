# 🌱 Plant Cell Health Status Tracker

## Level Challenge
**Easy** 🟢

---

## 📋 Gambaran Umum

Buat sebuah fungsi bernama `checkPlantCellHealth` yang memantau status kesehatan sel tanaman berdasarkan pengukuran integritas seluler dan indikator perilaku hama.

---

## 🎯 Tujuan

Fungsi ini menerima dua parameter: `cellIntegrity` dan `pestPresence`. Fungsi akan melakukan iterasi melalui array `cellIntegrity` dan memeriksa nilai yang sesuai dalam array `pestPresence` pada setiap index untuk menentukan status kesehatan setiap sel.

---

## 📊 Kriteria Status Kesehatan

Status kesehatan setiap sel ditentukan menggunakan aturan berikut:

### ✅ **Healthy**
- Integritas sel > **75%** DAN
- Tidak ada kehadiran hama (`false`)

### ⚠️ **At Risk**
- Integritas sel antara **50% - 75%** (inklusif) ATAU
- Kehadiran hama terdeteksi (`true`)

### ❌ **Unhealthy**
- Integritas sel < **50%**
- *Terlepas dari kehadiran hama*

---

## 🔧 Spesifikasi Fungsi

### Nama Fungsi
```javascript
checkPlantCellHealth(cellIntegrity, pestPresence)
```

### Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-------------|
| `cellIntegrity` | `integer-array` | Array di mana setiap integer merepresentasikan persentase integritas dari sel tanaman |
| `pestPresence` | `boolean-array` | Array dengan panjang yang sama dengan `cellIntegrity`, di mana setiap nilai boolean menunjukkan kehadiran (`true`) atau ketiadaan (`false`) hama |

### Return Value

| Tipe | Deskripsi |
|------|-------------|
| `string-array` | Array dari string yang mendeskripsikan status kesehatan setiap sel ("Healthy", "At Risk", atau "Unhealthy") |

---

## 💡 Contoh

```javascript
// Sample Input
const cellIntegrity = [80, 65, 45, 90, 55];
const pestPresence = [false, false, true, true, false];

// Expected Output
// ["Healthy", "At Risk", "Unhealthy", "At Risk", "At Risk"]
```

### Penjelasan:
- **Index 0**: 80% integritas, tidak ada hama → **Healthy**
- **Index 1**: 65% integritas, tidak ada hama → **At Risk** (rentang 50-75%)
- **Index 2**: 45% integritas, ada hama → **Unhealthy** (< 50%)
- **Index 3**: 90% integritas, ada hama → **At Risk** (kehadiran hama)
- **Index 4**: 55% integritas, tidak ada hama → **At Risk** (rentang 50-75%)

---

## 📝 Catatan Implementasi

- Kedua array akan selalu memiliki **panjang yang sama**
- Nilai integritas adalah persentase (0-100)
- Fungsi harus mengembalikan array dengan panjang yang sama dengan array input
- Setiap elemen dalam output berkorespondensi dengan status kesehatan pada index yang sama dalam array input

---

## 🚀 Mulai Coding

Implementasikan fungsi `checkPlantCellHealth` mengikuti kriteria di atas. Pastikan untuk menangani semua edge case dan uji solusi Anda dengan berbagai kombinasi input!

**Happy Coding!** 💻🌿
