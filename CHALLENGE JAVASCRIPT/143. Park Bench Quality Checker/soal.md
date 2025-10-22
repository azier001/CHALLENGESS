# 🪑 Park Bench Quality Checker

> **Tingkat Kesulitan:** `Easy` 🟢

---

## 📋 Gambaran Challenge

Departemen taman lokal menghadapi kritik karena bangku yang kurang terawat. Tugas Anda adalah membuat function yang mengevaluasi kualitas bangku taman berdasarkan ketebalan coating dan lokasi penempatannya.

---

## 🎯 Tujuan

Buat sebuah function bernama **`benchQualityChecker`** yang menilai kualitas bangku taman dan memberikan rekomendasi pemeliharaan.

---

## 📥 Parameter Function

Function harus menerima **dua parameter**:

| Parameter | Tipe | Deskripsi |
|-----------|------|-------------|
| `coatingThickness` | `number` | Integer yang merepresentasikan ketebalan coating dalam **mikrometer (μm)** |
| `isHighTraffic` | `boolean` | Menunjukkan apakah bangku berada di area lalu lintas tinggi (`true`) atau area lalu lintas rendah (`false`) |

---

## 🔍 Kriteria Penilaian Kualitas

Function harus mengembalikan string berdasarkan aturan evaluasi berikut:

### 🔴 Kondisi Kritis
- **Coating < 50 μm**
  - Return: `"Terrible - Replace immediately!"`

### 🟡 Kondisi Peringatan
- **Coating: 50-100 μm (inklusif)**
  - **Area high-traffic:** Return `"Poor - Needs recoating soon"`
  - **Area low-traffic:** Return `"Acceptable - Monitor closely"`

### 🟢 Kondisi Baik
- **Coating: 101-150 μm (inklusif)**
  - Return: `"Good - No action needed"`

### 🔵 Coating Berlebihan
- **Coating > 150 μm**
  - Return: `"Excellent - Overcoated!"`

---

## 💡 Persyaratan Implementasi

- Gunakan **conditional statements** (`if-else`) untuk mengimplementasikan logika
- Pastikan penanganan yang tepat untuk **nilai batas** (50, 100, 101, 150)
- Pertimbangkan **kedua parameter** saat mengevaluasi bangku dalam rentang 50-100 μm

---

## 📝 Function Signature

```javascript
function benchQualityChecker(coatingThickness, isHighTraffic) {
  // Implementasi Anda di sini
}
```

---

## ✅ Contoh Perilaku yang Diharapkan

```javascript
// Kasus kritis
benchQualityChecker(45, false)
// → "Terrible - Replace immediately!"

// Kasus peringatan
benchQualityChecker(75, true)
// → "Poor - Needs recoating soon"

benchQualityChecker(75, false)
// → "Acceptable - Monitor closely"

// Kasus baik
benchQualityChecker(125, true)
// → "Good - No action needed"

// Coating berlebihan
benchQualityChecker(200, false)
// → "Excellent - Overcoated!"
```

---

## 🚀 Memulai

1. Definisikan function dengan parameter yang diperlukan
2. Implementasikan logika conditional mengikuti kriteria di atas
3. Test dengan berbagai kombinasi input
4. Pastikan semua edge case tercakup

---

**Selamat mengerjakan! 🎉**
