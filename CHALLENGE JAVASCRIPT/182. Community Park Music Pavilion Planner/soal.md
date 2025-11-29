# 🎵 Community Park Music Pavilion Planner

> **Tingkat Kesulitan:** Medium

---

## 📋 Ringkasan Challenge

Buat sebuah function `planParkDay` yang mengelola operasional pavilion musik di taman komunitas. Function ini memproses jadwal pertunjukan, menghitung kebutuhan ruang berdasarkan ukuran audiens, dan mengidentifikasi tugas maintenance berikutnya yang masih pending.

---

## 🎯 Function Signature

```javascript
function planParkDay(schedules, inventory, audienceCounts, tasks)
```

---

## 📥 Parameters

| Parameter | Type | Deskripsi |
|-----------|------|-----------|
| `schedules` | `array` | Entry pertunjukan dengan format `"BandName@Time"` |
| `inventory` | `object` | Nama instrumen yang dipetakan ke jumlah yang tersedia |
| `audienceCounts` | `array` | Perkiraan jumlah audiens untuk setiap pertunjukan yang dijadwalkan |
| `tasks` | `array` | Tugas maintenance dengan format `"task-name:status"` |

---

## 🔧 Persyaratan Logic

### 1. **Schedule Summary Generation**
Gabungkan semua entry jadwal dengan jumlah audiens yang sesuai untuk membuat string ringkasan yang komprehensif.

**Format:** `"BandName@Time(audienceCount)"`

### 2. **Space Calculation**
Hitung total ruang yang dibutuhkan dengan:
- Menerapkan formula: `Math.floor(count * 1.5)` ke setiap jumlah audiens
- Menjumlahkan semua hasil perhitungan

### 3. **Maintenance Task Identification**
Loop melalui tasks maintenance untuk menemukan yang pertama dengan status `"pending"`:
- Gunakan statement **break/continue** untuk pencarian yang efisien
- Return hanya nama task (tanpa status)

---

## 📤 Return Value

Function mengembalikan sebuah **object** dengan struktur berikut:

```javascript
{
  "summary": "BandA@10:00(50)BandB@14:00(75)",
  "spaceNeeded": 187,
  "nextMaintenance": "mow-grass"
}
```

### Properties Return Object

- **`summary`** _(string)_: Jadwal pertunjukan yang digabungkan dengan jumlah audiens
- **`spaceNeeded`** _(number)_: Total ruang yang dihitung untuk semua pertunjukan
- **`nextMaintenance`** _(string)_: Nama task maintenance pertama yang pending

---

## 💡 Contoh

### Input:
```javascript
const schedules = ["RockBand@10:00", "JazzTrio@14:00"];
const inventory = { guitar: 5, drums: 2, keyboard: 3 };
const audienceCounts = [50, 75];
const tasks = ["clean-stage:completed", "mow-grass:pending", "repair-lights:pending"];
```

### Output:
```javascript
{
  "summary": "RockBand@10:00(50)JazzTrio@14:00(75)",
  "spaceNeeded": 187,
  "nextMaintenance": "mow-grass"
}
```

### Breakdown Perhitungan:
- **Ruang untuk 50 audiens:** `Math.floor(50 * 1.5) = 75`
- **Ruang untuk 75 audiens:** `Math.floor(75 * 1.5) = 112`
- **Total ruang yang dibutuhkan:** `75 + 112 = 187`

---

## ✅ Poin Penting yang Perlu Diingat

- Pastikan string summary **tidak memiliki spasi atau pemisah** antara entry jadwal
- Perhitungan ruang menggunakan `Math.floor()` untuk membulatkan ke bawah ke integer terdekat
- Hanya return **task pending pertama** yang ditemukan dalam array tasks
- Parameter `inventory` disediakan tetapi mungkin tidak digunakan dalam logic inti

---

## 🚀 Tips Implementasi

1. Gunakan method array seperti `map()` dan `reduce()` untuk pemrosesan data yang efisien
2. Implementasikan kontrol loop yang tepat dengan `break` saat menemukan task pending pertama
3. Tangani edge cases (array kosong, tidak ada task pending, dll.)
4. Pastikan konsistensi tipe data dalam return object

---

**Semangat untuk implementasinya! 🎪**
