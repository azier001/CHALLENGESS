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
  if (hasNausea && hasStomachPain && hasHeartburn) {
    return "Possible gastritis";
  }
  
  // Cek apakah ada refluks asam (sakit perut dan heartburn tanpa mual)
  if (hasStomachPain && hasHeartburn && !hasNausea) {
    return "Likely acid reflux";
  }
  
  // Cek gejala individual - hanya mual
  if (hasNausea && !hasStomachPain && !hasHeartburn) {
    return "Possible stomach bug";
  }
  
  // Cek gejala individual - hanya sakit perut
  if (!hasNausea && hasStomachPain && !hasHeartburn) {
    return "Possible stomach ulcer";
  }
  
  // Cek gejala individual - hanya heartburn
  if (!hasNausea && !hasStomachPain && hasHeartburn) {
    return "Mild indigestion";
  }
  
  // Cek apakah tidak ada gejala sama sekali
  if (!hasNausea && !hasStomachPain && !hasHeartburn) {
    return "No issues detected";
  }
  
  // Untuk kombinasi gejala lainnya yang tidak terdefinisi
  return "Inconclusive, please consult with the doctor";
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

### Contoh 6: Hanya Sakit Perut
```javascript
const result6 = diagnoseStomachIssue(false, true, false);
console.log(result6);
// Output: "Possible stomach ulcer"
```

**Penjelasan**: Pasien hanya mengalami sakit perut → kemungkinan tukak lambung.

---

### Contoh 7: Hanya Heartburn
```javascript
const result7 = diagnoseStomachIssue(false, false, true);
console.log(result7);
// Output: "Mild indigestion"
```

**Penjelasan**: Pasien hanya mengalami heartburn → gangguan pencernaan ringan.

---

## 🔄 Alur Kerja Fungsi

```
┌─────────────────────────────────────────────────┐
│ Input: hasNausea, hasStomachPain, hasHeartburn  │
└───────────────────┬─────────────────────────────┘
                    │
                    ▼
            ┌───────────────────────────┐
            │ Semua gejala ada?         │
            │ (mual + perut + heartburn)│
            └───────────┬───────────────┘
                        │
            ┌───────────┴───────────┐
            │ Ya                    │ Tidak
            ▼                       ▼
    ┌──────────────────┐    ┌──────────────────────────┐
    │ Possible         │    │ Perut + heartburn tanpa  │
    │ gastritis        │    │ mual?                    │
    └──────────────────┘    └──────────┬───────────────┘
                                       │
                            ┌──────────┴──────────┐
                            │ Ya                  │ Tidak
                            ▼                     ▼
                    ┌──────────────┐      ┌─────────────────┐
                    │ Likely acid  │      │ Hanya mual?     │
                    │ reflux       │      │ (tanpa lainnya) │
                    └──────────────┘      └──────┬──────────┘
                                                 │
                                      ┌──────────┴──────────┐
                                      │ Ya                  │ Tidak
                                      ▼                     ▼
                              ┌──────────────┐      ┌──────────────────┐
                              │ Possible     │      │ Hanya sakit      │
                              │ stomach bug  │      │ perut?           │
                              └──────────────┘      └──────┬───────────┘
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

Fungsi ini menggunakan struktur **if-statement** yang mengecek kondisi secara berurutan dari atas ke bawah:

1. **Pertama**, cek apakah semua gejala ada → jika ya, kembalikan "Possible gastritis"
2. **Kedua**, cek apakah hanya sakit perut dan heartburn → jika ya, kembalikan "Likely acid reflux"
3. **Ketiga sampai kelima**, cek gejala individual (mual saja, sakit perut saja, atau heartburn saja)
4. **Keenam**, cek apakah tidak ada gejala sama sekali
5. **Terakhir**, jika tidak ada kondisi yang cocok, kembalikan pesan untuk konsultasi dokter

### Operator Logika yang Digunakan:
- `&&` (AND) = "dan" → semua kondisi harus benar
- `!` (NOT) = "tidak" → membalik nilai boolean
- Contoh: `hasNausea && !hasStomachPain` artinya "ada mual DAN tidak ada sakit perut"

---

## ⚡ Return Value

**Tipe Data**: `string`

Fungsi ini mengembalikan salah satu dari 7 kemungkinan hasil diagnosis dalam bentuk teks:

| No | Hasil Diagnosis | Kondisi |
|:--:|-----------------|---------|
| 1 | `"Possible gastritis"` | Semua gejala ada |
| 2 | `"Likely acid reflux"` | Sakit perut + heartburn (tanpa mual) |
| 3 | `"Possible stomach bug"` | Hanya mual |
| 4 | `"Possible stomach ulcer"` | Hanya sakit perut |
| 5 | `"Mild indigestion"` | Hanya heartburn |
| 6 | `"No issues detected"` | Tidak ada gejala |
| 7 | `"Inconclusive, please consult with the doctor"` | Kombinasi lainnya |

---

## 📌 Tips Penggunaan

✅ **Do (Lakukan)**:
- Gunakan fungsi ini sebagai *screening* awal untuk memahami gejala
- Selalu konsultasikan dengan dokter untuk diagnosis yang akurat
- Gunakan nilai boolean yang benar (`true`/`false`) sebagai input
- Test fungsi dengan berbagai kombinasi input untuk memahami cara kerjanya

❌ **Don't (Jangan)**:
- Jangan menganggap hasil diagnosis ini sebagai pengganti konsultasi medis profesional
- Jangan menggunakan tipe data selain boolean untuk parameter
- Jangan memodifikasi urutan if-statement tanpa memahami logikanya

---

## 🧪 Test Cases

Berikut adalah semua kemungkinan kombinasi input (2³ = 8 kombinasi):

```javascript
// Test 1: Semua false
diagnoseStomachIssue(false, false, false); 
// ✅ "No issues detected"

// Test 2: Hanya nausea
diagnoseStomachIssue(true, false, false);  
// ✅ "Possible stomach bug"

// Test 3: Hanya stomach pain
diagnoseStomachIssue(false, true, false);  
// ✅ "Possible stomach ulcer"

// Test 4: Hanya heartburn
diagnoseStomachIssue(false, false, true);  
// ✅ "Mild indigestion"

// Test 5: Nausea + stomach pain
diagnoseStomachIssue(true, true, false);   
// ✅ "Inconclusive, please consult with the doctor"

// Test 6: Nausea + heartburn
diagnoseStomachIssue(true, false, true);   
// ✅ "Inconclusive, please consult with the doctor"

// Test 7: Stomach pain + heartburn
diagnoseStomachIssue(false, true, true);   
// ✅ "Likely acid reflux"

// Test 8: Semua true
diagnoseStomachIssue(true, true, true);    
// ✅ "Possible gastritis"
```

---

## 📚 Konsep Programming yang Digunakan

### 1. **Conditional Statements (If-Else)**
Fungsi ini menggunakan struktur `if-else` untuk membuat keputusan berdasarkan kondisi:
```javascript
if (kondisi) {
  // jalankan kode ini jika kondisi benar
}
```

### 2. **Boolean Logic**
- **AND (`&&`)**: Semua kondisi harus `true`
- **NOT (`!`)**: Membalik nilai (`true` menjadi `false` dan sebaliknya)

### 3. **Early Return**
Fungsi langsung mengembalikan nilai ketika kondisi terpenuhi, tanpa melanjutkan pengecekan berikutnya.

### 4. **Default Case**
Baris terakhir (`return "Inconclusive..."`) berfungsi sebagai *default* untuk menangani kasus yang tidak terdefinisi.

---

## 🔍 Perbedaan Versi Fungsi

Ada dua cara menulis fungsi ini:

### Versi 1: Dengan Variabel Konstanta (Versi Sebelumnya)
```javascript
const allSymptoms = hasNausea && hasStomachPain && hasHeartburn;
if (allSymptoms) { ... }
```
**Kelebihan**: Lebih mudah dibaca, kondisi diberi nama yang deskriptif

### Versi 2: Direct Condition Check (Versi Ini)
```javascript
if (hasNausea && hasStomachPain && hasHeartburn) { ... }
```
**Kelebihan**: Lebih ringkas, lebih sedikit variabel

Kedua versi menghasilkan output yang sama! 🎯

---

## 📄 Lisensi

Dokumentasi ini dibuat untuk tujuan edukasi dan pembelajaran programming. Selalu konsultasikan dengan profesional kesehatan untuk masalah medis yang sebenarnya.

---

**Dibuat dengan ❤️ untuk pembelajaran JavaScript**
