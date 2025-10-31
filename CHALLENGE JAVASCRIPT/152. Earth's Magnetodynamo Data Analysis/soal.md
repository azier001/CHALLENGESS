# 🌍 Analisis Data Magnetodynamo Bumi

## Tingkat Kesulitan
**Easy** ⭐

---

## 📋 Deskripsi Challenge

Bantu seorang ilmuwan yang sangat berprestasi dalam menganalisis data magnetodynamo Bumi yang dikumpulkan di laboratorium mereka. Tugas Anda adalah memproses array data input untuk mengungkap pola geologis tersembunyi melalui manipulasi data sistematis dan analisis statistik.

---

## 🎯 Tujuan

Buat sebuah function bernama **`analyzeMagnetodynamo`** yang memproses pengukuran medan magnet dan menghitung nilai rata-ratanya setelah menerapkan transformasi data tertentu.

---

## 📊 Spesifikasi Function

### Function Signature
```javascript
analyzeMagnetodynamo(primaryData, secondaryData)
```

### Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `primaryData` | Array of Numbers | Pengukuran medan magnet primer |
| `secondaryData` | Array of Numbers | Pengukuran medan magnet sekunder |

### Return Value

- **Tipe:** Number
- **Deskripsi:** Nilai rata-rata (mean) dari data yang telah diproses

---

## ⚙️ Langkah-langkah Pemrosesan

Function harus melakukan operasi berikut secara berurutan:

### 1. **Slice Primary Data**
   - Ekstrak hanya **setengah pertama** elemen dari array `primaryData`
   - Gunakan teknik array slicing untuk menjaga integritas data

### 2. **Slice Secondary Data**
   - Ekstrak hanya **setengah terakhir** elemen dari array `secondaryData`
   - Pastikan indexing yang tepat untuk hasil yang akurat

### 3. **Concatenate Array**
   - Gabungkan `primaryData` yang telah di-slice dengan `secondaryData` yang telah di-slice
   - Pertahankan urutan: primary terlebih dahulu, secondary terakhir

### 4. **Hitung Average**
   - Hitung mean (rata-rata) dari array gabungan yang dihasilkan
   - Return nilai yang telah dihitung

---

## 💡 Contoh Penggunaan

```javascript
const primary = [10, 20, 30, 40, 50, 60];
const secondary = [5, 15, 25, 35, 45, 55];

const result = analyzeMagnetodynamo(primary, secondary);
// Proses yang diharapkan:
// - Setengah pertama primary: [10, 20, 30]
// - Setengah terakhir secondary: [35, 45, 55]
// - Gabungan: [10, 20, 30, 35, 45, 55]
// - Average: (10+20+30+35+45+55)/6 = 32.5
```

---

## 🔬 Konteks Ilmiah

Magnetodynamo adalah mekanisme dimana Bumi menghasilkan medan magnetnya melalui gerakan besi cair di outer core. Challenge ini mensimulasikan proses:

- Memfilter pengukuran tahap awal (primary data)
- Memilih pengukuran tahap akhir (secondary data)
- Menggabungkan dataset untuk analisis komprehensif
- Menurunkan insights statistik yang bermakna

---

## ✅ Ringkasan Requirements

- [ ] Nama function: `analyzeMagnetodynamo`
- [ ] Menerima dua parameter array
- [ ] Slice setengah pertama dari primary data
- [ ] Slice setengah terakhir dari secondary data
- [ ] Concatenate kedua array yang telah di-slice
- [ ] Hitung dan return nilai average
- [ ] Handle array dengan panjang berapapun dengan tepat

---

**Semoga berhasil dengan analisis data geologis Anda! 🧲🔍**
