# 🔧 Perbaiki Ironman Suit yang Berkarat

## 📊 Informasi Challenge
- **Level Kesulitan**: `Easy`
- **Nama Function**: `repairIronmanSuit`
- **Konsep Programming**: String manipulation dan simulasi

---

## 🎯 Deskripsi Masalah

Tony Stark telah menemukan Ironman suit-nya yang berkarat di sebuah gudang tua dan membutuhkan bantuan Anda untuk memperbaikinya! Kondisi suit sangat kritis, dan waktu semakin menipis sebelum misi berikutnya.

### 🦾 Kondisi Suit
Status suit direpresentasikan oleh string yang berisi:
- **`R`** - Bagian berkarat (rusty parts, perlu dibersihkan)
- **`C`** - Bagian bersih (clean parts, dalam kondisi baik)

### ⚡ Tantangan
Tony memiliki energi terbatas dan hanya bisa membersihkan sejumlah tertentu bagian sekaligus. Namun, ada masalah - **karat menyebar**! Setelah pembersihan, bagian berkarat yang tersisa akan mengontaminasi bagian bersih yang berdekatan.

---

## 🔧 Spesifikasi Function

### Function Signature
```javascript
function repairIronmanSuit(suitStatus, cleanParts)
```

### Parameter
| Parameter | Type | Deskripsi |
|-----------|------|-----------|
| `suitStatus` | `string` | Status suit saat ini (hanya berisi 'R' dan 'C') |
| `cleanParts` | `number` | Jumlah maksimum bagian yang bisa dibersihkan Tony dalam satu putaran |

### Return Value
- **Type**: `string`
- **Deskripsi**: Status akhir suit setelah satu putaran pembersihan dan penyebaran karat

---

## ⚙️ Proses Perbaikan

Simulasi perbaikan mengikuti langkah-langkah berikut:

### Step 1: 🧹 Fase Pembersihan
- Scan suit **dari kiri ke kanan**
- Ganti `R` dengan `C` untuk maksimal `cleanParts` bagian berkarat
- Berhenti ketika batas pembersihan tercapai

### Step 2: 🦠 Fase Penyebaran Karat
- Setiap bagian berkarat yang tersisa (`R`) menyebarkan karat ke **satu bagian bersih yang berdekatan**
- Karat bisa menyebar ke sisi **kiri** atau **kanan** (jika ada bagian bersih)
- Ini terjadi secara bersamaan untuk semua bagian berkarat

---

## 💡 Contoh Walkthrough

### Input
```
suitStatus = "RRRCCCRRR"
cleanParts = 3
```

### Proses
1. **Status Awal**: `"RRRCCCRRR"`
2. **Setelah Pembersihan** (3 bagian): `"CCCCCCRRR"`
   - 3 'R' pertama dari kiri dibersihkan
3. **Setelah Penyebaran Karat**: `"RCCCCCRR"`
   - 'R' di posisi ke-7 menyebar ke kiri (posisi 6)
   - 'R' di posisi ke-8 dan ke-9 menyebar ke kiri (posisi 7)

### Output
```
"RCCCCCRR"
```

---

## 🎯 Poin Penting yang Harus Diingat

> ⚠️ **Penting**: Penyebaran karat terjadi **setelah** semua pembersihan selesai

> 💡 **Tips**: Pertimbangkan edge case dimana karat mungkin tidak memiliki bagian bersih yang berdekatan untuk disebarkan

> 🔄 **Urutan Proses**: Selalu bersihkan dulu, kemudian simulasikan penyebaran karat

---

## 🧪 Test Solution Anda

Coba test case tambahan ini untuk memverifikasi implementasi Anda:

```javascript
// Test Case 1: Tidak ada karat untuk disebarkan
repairIronmanSuit("RRR", 3) // Expected: "CCC"

// Test Case 2: Kapasitas pembersihan terbatas
repairIronmanSuit("RRRRR", 2) // Expected: "CCRR" (setelah penyebaran)

// Test Case 3: Pattern campuran
repairIronmanSuit("RCRCRC", 1) // Expected: bervariasi berdasarkan implementasi
```

---

## 🏆 Kriteria Keberhasilan

Function Anda harus:
- ✅ Membersihkan jumlah bagian berkarat yang tepat dari kiri ke kanan
- ✅ Mensimulasikan penyebaran karat dengan akurat
- ✅ Menangani edge case (tidak ada karat, tidak ada bagian bersih, dll.)
- ✅ Mengembalikan status akhir yang benar sebagai string

---

*Semoga berhasil, dan semoga arc reactor menyertai Anda! ⚡*
