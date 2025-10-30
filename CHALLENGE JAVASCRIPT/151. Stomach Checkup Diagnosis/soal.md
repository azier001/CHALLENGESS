# 🏥 Stomach Checkup Diagnosis

## 📋 Gambaran Challenge

**Tingkat Kesulitan:** `Easy`

Buat sebuah function yang mensimulasikan proses diagnosis dasar di kantor dokter untuk pemeriksaan lambung. Function ini menganalisis kombinasi gejala dan mengembalikan diagnosis yang sesuai.

---

## 🎯 Tujuan

Implementasikan function bernama `diagnoseStomachIssue` yang menerima tiga parameter boolean yang merepresentasikan gejala yang berbeda dan mengembalikan diagnosis berdasarkan kombinasinya.

---

## 📥 Function Signature

```javascript
function diagnoseStomachIssue(hasNausea, hasStomachPain, hasHeartburn)
```

### Parameter

| Parameter | Type | Deskripsi |
|-----------|------|-------------|
| `hasNausea` | `boolean` | Apakah pasien mengalami mual |
| `hasStomachPain` | `boolean` | Apakah pasien mengalami sakit perut |
| `hasHeartburn` | `boolean` | Apakah pasien mengalami heartburn |

### Return Value

- **Type:** `string`
- **Deskripsi:** Pesan diagnosis berdasarkan kombinasi gejala

---

## 🔍 Kriteria Diagnosis

Function harus mengevaluasi gejala dan mengembalikan diagnosis sesuai dengan logika berikut:

| Gejala | Diagnosis |
|----------|-----------|
| ✅ Ketiga gejala ada | `"Possible gastritis"` |
| ✅ Sakit perut + Heartburn (tanpa mual) | `"Likely acid reflux"` |
| ✅ Hanya mual | `"Possible stomach bug"` |
| ✅ Hanya sakit perut | `"Possible stomach ulcer"` |
| ✅ Hanya heartburn | `"Mild indigestion"` |
| ❌ Tidak ada gejala | `"No issues detected"` |
| ❓ Kombinasi lainnya | `"Inconclusive, please consult with the doctor"` |

---

## 💡 Persyaratan

- ✔️ Gunakan **logical operators dasar** (AND, OR, NOT) untuk menentukan diagnosis
- ✔️ Manfaatkan **variables** untuk menyimpan hasil intermediate
- ✔️ Ikuti kriteria diagnosis yang tercantum di atas dengan tepat
- ✔️ Return strings yang sesuai persis seperti yang ditentukan

---

## 📝 Contoh Penggunaan

```javascript
// Contoh 1: Semua gejala ada
diagnoseStomachIssue(true, true, true);
// Returns: "Possible gastritis"

// Contoh 2: Hanya sakit perut dan heartburn
diagnoseStomachIssue(false, true, true);
// Returns: "Likely acid reflux"

// Contoh 3: Hanya mual
diagnoseStomachIssue(true, false, false);
// Returns: "Possible stomach bug"

// Contoh 4: Tidak ada gejala
diagnoseStomachIssue(false, false, false);
// Returns: "No issues detected"
```

---

## 🧠 Petunjuk

1. Mulai dengan memeriksa kondisi yang paling spesifik terlebih dahulu (semua gejala, kombinasi tertentu)
2. Gunakan logical operators seperti `&&` (AND), `||` (OR), dan `!` (NOT)
3. Pertimbangkan untuk menyimpan boolean expressions dalam variables untuk kode yang lebih bersih
4. Urutan conditional statements kamu sangat penting!

---

## ⚠️ Catatan Penting

> **Disclaimer:** Ini adalah latihan edukasi yang disederhanakan. Diagnosis medis yang sebenarnya memerlukan evaluasi medis profesional dan tidak boleh digantikan oleh sistem otomatis.

---

**Semangat! 🚀**
