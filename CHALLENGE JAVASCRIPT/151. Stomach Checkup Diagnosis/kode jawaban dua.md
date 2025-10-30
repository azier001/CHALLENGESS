# 📋 Dokumentasi Fungsi `diagnoseStomachIssue`

## 🎯 Deskripsi

Fungsi `diagnoseStomachIssue` adalah fungsi diagnostik sederhana yang membantu mengidentifikasi kemungkinan masalah perut berdasarkan kombinasi gejala yang dialami. Fungsi ini menganalisis tiga gejala utama (mual, sakit perut, dan heartburn) untuk memberikan diagnosis awal.

> ⚠️ **Catatan Penting**: Ini hanya diagnosis awal berdasarkan gejala. Untuk diagnosis yang akurat, selalu konsultasikan dengan dokter profesional.

---

## 📝 Parameter

Fungsi ini menerima **3 parameter boolean** yang merepresentasikan gejala-gejala yang dialami:

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `hasNausea` | `boolean` | Apakah pasien mengalami mual? (`true` = ya, `false` = tidak) |
| `hasStomachPain` | `boolean` | Apakah pasien mengalami sakit perut? (`true` = ya, `false` = tidak) |
| `hasHeartburn` | `boolean` | Apakah pasien mengalami heartburn/sensasi panas di dada? (`true` = ya, `false` = tidak) |

---

## 🔍 Tabel Kombinasi Gejala & Diagnosis

| Mual | Sakit Perut | Heartburn | Diagnosis |
|:----:|:-----------:|:---------:|-----------|
| ✅ | ✅ | ✅ | Possible gastritis (Kemungkinan gastritis) |
| ❌ | ✅ | ✅ | Likely acid reflux (Kemungkinan besar refluks asam) |
| ✅ | ❌ | ❌ | Possible stomach bug (Kemungkinan infeksi perut) |
| ❌ | ✅ | ❌ | Possible stomach ulcer (Kemungkinan tukak lambung) |
| ❌ | ❌ | ✅ | Mild indigestion (Gangguan pencernaan ringan) |
| ❌ | ❌ | ❌ | No issues detected (Tidak ada masalah terdeteksi) |
| *Lainnya* | *Lainnya* | *Lainnya* | Inconclusive, please consult with the doctor (Tidak dapat disimpulkan, silakan konsultasi dengan dokter) |

---

## 💻 Kode Fungsi

```javascript
function diagnoseStomachIssue(hasNausea, hasStomachPain, hasHeartburn) {
  
  // Cek apakah semua gejala ada
  const allSymptoms = hasNausea && hasStomachPain && hasHeartburn;
  
  // Cek apakah tidak ada gejala sama sekali
  const noSymptoms = !hasNausea && !hasStomachPain && !hasHeartburn;
  
  // Cek apakah hanya sakit perut dan heartburn tanpa mual
  const painAndHeartburnOnly = !hasNausea && hasStomachPain && hasHeartburn;
  
  // Cek apakah hanya mengalami mual
  const nauseaOnly = hasNausea && !hasStomachPain && !hasHeartburn;
  
  // Cek apakah hanya mengalami sakit perut
  const painOnly = !hasNausea && hasStomachPain && !hasHeartburn;
  
  // Cek apakah hanya mengalami heartburn
  const heartburnOnly = !hasNausea && !hasStomachPain && hasHeartburn;
  
  // Tentukan diagnosis berdasarkan kombinasi gejala
  if (allSymptoms) {
    return "Possible gastritis";
    
  } else if (painAndHeartburnOnly) {
    return "Likely acid reflux";
    
  } else if (nauseaOnly) {
    return "Possible stomach bug";
    
  } else if (painOnly) {
    return "Possible stomach ulcer";
    
  } else if (heartburnOnly) {
    return "Mild indigestion";
    
  } else if (noSymptoms) {
    return "No issues detected";
    
  } else {
    return "Inconclusive, please consult with the doctor";
  }
}
```

---

## 📊 Contoh Penggunaan

### Contoh 1: Semua Gejala Ada
```javascript
const result1 = diagnoseStomachIssue(true, true, true);
console.log(result1);
// Output: "Possible gastritis"
```

**Penjelasan**: Pasien mengalami mual, sakit perut, dan heartburn → kemungkinan gastritis.

---

### Contoh 2: Hanya Sakit Perut dan Heartburn
```javascript
const result2 = diagnoseStomachIssue(false, true, true);
console.log(result2);
// Output: "Likely acid reflux"
```

**Penjelasan**: Pasien mengalami sakit perut dan heartburn tanpa mual → kemungkinan besar refluks asam.

---

### Contoh 3: Hanya Mual
```javascript
const result3 = diagnoseStomachIssue(true, false, false);
console.log(result3);
// Output: "Possible stomach bug"
```

**Penjelasan**: Pasien hanya mengalami mual → kemungkinan infeksi perut atau stomach bug.

---

### Contoh 4: Tidak Ada Gejala
```javascript
const result4 = diagnoseStomachIssue(false, false, false);
console.log(result4);
// Output: "No issues detected"
```

**Penjelasan**: Pasien tidak mengalami gejala apapun → tidak ada masalah terdeteksi.

---

### Contoh 5: Kombinasi Gejala Lainnya
```javascript
const result5 = diagnoseStomachIssue(true, true, false);
console.log(result5);
// Output: "Inconclusive, please consult with the doctor"
```

**Penjelasan**: Kombinasi gejala tidak termasuk dalam kategori diagnosis yang sudah ditentukan → perlu konsultasi dokter.

---

## 🔄 Alur Kerja Fungsi

```
┌─────────────────────────────────────────────────┐
│ Input: hasNausea, hasStomachPain, hasHeartburn  │
└───────────────────┬─────────────────────────────┘
                    │
                    ▼
            ┌───────────────┐
            │ Semua gejala? │
            └───────┬───────┘
                    │
        ┌───────────┴───────────┐
        │ Ya                    │ Tidak
        ▼                       ▼
┌──────────────────┐    ┌─────────────────────┐
│ Possible         │    │ Sakit perut &       │
│ gastritis        │    │ heartburn saja?     │
└──────────────────┘    └──────────┬──────────┘
                                   │
                        ┌──────────┴──────────┐
                        │ Ya                  │ Tidak
                        ▼                     ▼
                ┌──────────────┐      ┌─────────────┐
                │ Likely acid  │      │ Hanya mual? │
                │ reflux       │      └──────┬──────┘
                └──────────────┘             │
                                    ┌────────┴────────┐
                                    │ Ya              │ Tidak
                                    ▼                 ▼
                            ┌──────────────┐   ┌───────────────┐
                            │ Possible     │   │ Hanya sakit   │
                            │ stomach bug  │   │ perut?        │
                            └──────────────┘   └───────┬───────┘
                                                       │
                                            ┌──────────┴──────────┐
                                            │ Ya                  │ Tidak
                                            ▼                     ▼
                                    ┌──────────────┐      ┌──────────────┐
                                    │ Possible     │      │ Hanya        │
                                    │ stomach      │      │ heartburn?   │
                                    │ ulcer        │      └──────┬───────┘
                                    └──────────────┘             │
                                                        ┌────────┴────────┐
                                                        │ Ya              │ Tidak
                                                        ▼                 ▼
                                                ┌──────────────┐  ┌────────────┐
                                                │ Mild         │  │ Tidak ada  │
                                                │ indigestion  │  │ gejala?    │
                                                └──────────────┘  └─────┬──────┘
                                                                        │
                                                                ┌───────┴───────┐
                                                                │ Ya            │ Tidak
                                                                ▼               ▼
                                                        ┌──────────────┐ ┌──────────────┐
                                                        │ No issues    │ │ Inconclusive │
                                                        │ detected     │ │ consult      │
                                                        └──────────────┘ │ doctor       │
                                                                         └──────────────┘
```

---

## 🎓 Penjelasan untuk Pemula

Fungsi ini bekerja seperti dokter yang menanyakan 3 pertanyaan:
1. Apakah kamu merasa mual?
2. Apakah perutmu sakit?
3. Apakah kamu merasakan sensasi panas/terbakar di dada (heartburn)?

Berdasarkan jawaban **Ya** (`true`) atau **Tidak** (`false`) dari ketiga pertanyaan ini, fungsi akan memberikan diagnosis awal tentang apa yang mungkin terjadi dengan perutmu.

### Cara Kerja:
- Fungsi mengecek berbagai **kombinasi gejala** menggunakan operator logika (`&&` untuk "dan", `!` untuk "tidak")
- Setiap kombinasi gejala menghasilkan diagnosis yang berbeda
- Jika kombinasi gejala tidak sesuai dengan pola yang sudah ditentukan, fungsi akan menyarankan untuk konsultasi dengan dokter

---

## ⚡ Return Value

**Tipe Data**: `string`

Fungsi ini mengembalikan salah satu dari 7 kemungkinan hasil diagnosis dalam bentuk teks:
- `"Possible gastritis"`
- `"Likely acid reflux"`
- `"Possible stomach bug"`
- `"Possible stomach ulcer"`
- `"Mild indigestion"`
- `"No issues detected"`
- `"Inconclusive, please consult with the doctor"`

---

## 📌 Tips Penggunaan

✅ **Do (Lakukan)**:
- Gunakan fungsi ini sebagai *screening* awal untuk memahami gejala
- Selalu konsultasikan dengan dokter untuk diagnosis yang akurat
- Gunakan nilai boolean yang benar (`true`/`false`) sebagai input

❌ **Don't (Jangan)**:
- Jangan menganggap hasil diagnosis ini sebagai pengganti konsultasi medis profesional
- Jangan menggunakan tipe data selain boolean untuk parameter

---

## 📚 Referensi

Fungsi ini menggunakan konsep:
- **Boolean Logic**: Operator `&&` (AND), `!` (NOT)
- **Conditional Statements**: `if-else` untuk menentukan alur diagnosis
- **Const Variables**: Untuk menyimpan hasil pengecekan kombinasi gejala

---

## 📄 Lisensi

Dokumentasi ini dibuat untuk tujuan edukasi dan pembelajaran programming. Selalu konsultasikan dengan profesional kesehatan untuk masalah medis yang sebenarnya.

---

**Dibuat dengan ❤️ untuk pembelajaran JavaScript**
