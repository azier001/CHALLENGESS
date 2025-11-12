# 🏥 Medical Test Results Processor

## Ikhtisar Challenge

**Tingkat Kesulitan:** `Easy`

---

## 📋 Deskripsi Masalah

Di sebuah fasilitas produksi medis berteknologi tinggi, seorang pasien yang gugup sedang menunggu hasil tes mereka. Tugas Anda adalah memproses dan menggabungkan hasil tes pendahuluan dan hasil tes akhir menjadi satu laporan yang terformat.

Anda perlu membuat sebuah function bernama **`processTestResults`** yang mengubah dan menggabungkan data tes medis menjadi laporan yang komprehensif dan terstruktur dengan baik.

---

## 🎯 Spesifikasi Function

### Function Signature

```javascript
function processTestResults(preliminaryResults, finalResults)
```

### Parameters

| Parameter | Type | Deskripsi |
|-----------|------|-------------|
| `preliminaryResults` | `Array<string>` | Array string yang merepresentasikan hasil tes pendahuluan |
| `finalResults` | `Array<string>` | Array string yang merepresentasikan hasil tes akhir |

### Return Value

- **Type:** `Array<string>`
- **Deskripsi:** Array yang telah diproses berisi hasil tes yang terformat dengan prefix dan separator yang tepat

---

## ⚙️ Operasi yang Diperlukan

Function harus melakukan operasi berikut **secara berurutan**:

1. **Prefix Hasil Pendahuluan**  
   Tambahkan prefix `"Status: "` pada setiap hasil pendahuluan

2. **Prefix Hasil Akhir**  
   Tambahkan prefix `"Conclusion: "` pada setiap hasil akhir

3. **Sisipkan Separator**  
   Tambahkan separator `"---"` di antara hasil pendahuluan dan hasil akhir

4. **Gabungkan Hasil**  
   Gabungkan semua elemen yang telah diproses ke dalam satu array

5. **Return Array yang Diproses**  
   Kembalikan array hasil tes yang telah diformat

---

## 💡 Contoh

### Input

```javascript
const preliminary = ["Blood pressure normal", "Temperature 36.5°C"];
const final = ["All tests passed", "Patient healthy"];
```

### Expected Output

```javascript
[
  "Status: Blood pressure normal",
  "Status: Temperature 36.5°C",
  "---",
  "Conclusion: All tests passed",
  "Conclusion: Patient healthy"
]
```

---

## 📝 Catatan Implementasi

- Pertahankan urutan hasil seperti yang muncul di array input
- Separator `"---"` harus muncul tepat satu kali di antara kedua bagian
- Semua string harus diformat dengan benar dengan prefix masing-masing
- Tangani array kosong dengan baik (jika berlaku)

---

## ✅ Kriteria Sukses

Implementasi Anda harus:

- ✓ Dengan benar memberi prefix semua hasil pendahuluan dengan `"Status: "`
- ✓ Dengan benar memberi prefix semua hasil akhir dengan `"Conclusion: "`
- ✓ Menyertakan tepat satu separator `"---"` pada posisi yang benar
- ✓ Mengembalikan satu array gabungan dengan semua hasil yang terformat
- ✓ Mempertahankan urutan asli hasil dalam setiap kategori

---

**Semangat! 🚀**
