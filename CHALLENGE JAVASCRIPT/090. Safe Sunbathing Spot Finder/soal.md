# 🏖️ Safe Sunbathing Spot Finder

## 📋 Ringkasan Challenge

**Level Kesulitan:** `Easy` 🟢

Buat sebuah function yang membantu pengunjung pantai menentukan apakah suatu tempat aman untuk berjemur berdasarkan kondisi lingkungan.

---

## 🎯 Tujuan

Implementasikan sebuah function bernama `sunbathingSpot` yang mengevaluasi kondisi keamanan pantai menggunakan pembacaan suhu dan observasi jumlah laba-laba.

### Function Signature
```javascript
function sunbathingSpot(temperature, spiderCount)
```

---

## 📝 Parameter

| Parameter | Type | Deskripsi |
|-----------|------|-----------|
| `temperature` | `number` | Suhu dalam derajat Celsius (selalu berupa integer) |
| `spiderCount` | `number` | Jumlah laba-laba yang terlihat di sekitar (integer non-negatif) |

---

## 🔍 Kriteria Evaluasi Keamanan

Function harus mengevaluasi kondisi menggunakan sistem prioritas berikut:

### 🕷️ **Spider Count (Prioritas Tinggi)**
- **0 laba-laba** → Lanjut ke pengecekan suhu
- **1-2 laba-laba** → Return `"Be cautious!"`
- **3+ laba-laba** → Return `"Find another spot!"`

### 🌡️ **Rentang Temperature (Prioritas Rendah)**
- **25-30°C (inclusive)** → Return `"Perfect spot!"` *(hanya jika 0 laba-laba)*
- **Di atas 30°C** → Return `"Too hot!"`
- **Di bawah 25°C** → Return `"Too cold!"`

---

## ⚠️ Catatan Penting

> **Spider count mengambil prioritas atas temperature!**
> 
> Meskipun suhu berada dalam rentang yang sempurna, kehadiran laba-laba akan menggantikan keputusan berdasarkan suhu.

---

## 📤 Expected Return Values

Function mengembalikan salah satu string berikut:

- `"Perfect spot!"` - Kondisi ideal (25-30°C, tidak ada laba-laba)
- `"Too hot!"` - Suhu di atas 30°C
- `"Too cold!"` - Suhu di bawah 25°C
- `"Be cautious!"` - 1-2 laba-laba hadir
- `"Find another spot!"` - 3 atau lebih laba-laba hadir

---

## 💡 Contoh Test Cases

```javascript
// Kondisi sempurna
sunbathingSpot(27, 0) // → "Perfect spot!"

// Masalah temperature
sunbathingSpot(35, 0) // → "Too hot!"
sunbathingSpot(20, 0) // → "Too cold!"

// Peringatan laba-laba (override temperature)
sunbathingSpot(28, 2) // → "Be cautious!"
sunbathingSpot(27, 5) // → "Find another spot!"
```

---

## 🚀 Langkah Memulai

1. Buat function dengan nama dan parameter yang telah ditentukan
2. Implementasikan pengecekan spider count terlebih dahulu (prioritas tinggi)
3. Tambahkan validasi rentang temperature sebagai fallback
4. Test dengan berbagai kombinasi input
5. Pastikan semua return values sesuai dengan yang telah dispesifikasikan

**Selamat coding! 🌞**
