# 🔬 Menganalisis Spesimen Tumbuhan di Laboratorium

<div align="center">

![Tingkat Kesulitan](https://img.shields.io/badge/Tingkat%20Kesulitan-Mudah-brightgreen)
![Topik](https://img.shields.io/badge/Topik-Lab%20Biologi-blue)
![Bahasa](https://img.shields.io/badge/Bahasa-JavaScript-yellow)

</div>

---

## 🎯 Gambaran Tantangan

> **Skenario:** Kamu adalah mahasiswa biologi yang bekerja di laboratorium kampus, memeriksa spesimen tumbuhan di bawah mikroskop. Misi kamu adalah menghitung spesimen yang menunjukkan karakteristik tertentu secara sistematis.

**Tugas:** Buat fungsi bernama `analyzePlantSpecimens` yang memproses data spesimen dan menghitung kecocokan berdasarkan karakteristik target.

---

## 📋 Spesifikasi Fungsi

### **Nama Fungsi**
```javascript
analyzePlantSpecimens(specimens, targetCharacteristic)
```

### **Parameter**

| Parameter | Tipe | Deskripsi | Contoh |
|-----------|------|-----------|---------|
| `specimens` | `Array<string>` | Kumpulan spesimen tumbuhan beserta karakteristiknya | `["daun hijau, batang tipis", "bunga kuning"]` |
| `targetCharacteristic` | `string` | Ciri khusus yang sedang dicari | `"daun hijau"` |

---

## ⚙️ Persyaratan Pemrosesan

### **Logika Inti**
1. **🔍 Iterasi** melalui setiap spesimen dalam array
2. **✅ Hitung** spesimen yang mengandung karakteristik target
3. **⏭️ Lewati** spesimen yang tidak cocok menggunakan pernyataan `continue`
4. **🛑 Henti Darurat** ketika menemui `"microscope malfunction"`
5. **📊 Kembalikan** jumlah akhir spesimen yang cocok

### **Aturan Alur Kontrol**

| Kondisi | Aksi | Pernyataan |
|---------|------|------------|
| Spesimen cocok dengan target | Tambah penghitung, lanjutkan | Lanjutkan loop |
| Spesimen tidak cocok | Lewati ke spesimen berikutnya | `continue` |
| Ditemukan "microscope malfunction" | Henti segera, kembalikan jumlah saat ini | `break` |

---

## 🚨 Kondisi Khusus

> **⚠️ Penting:** Jika pemeriksaan menemukan spesimen berlabel **"microscope malfunction"**, analisis harus dihentikan segera. Ini mensimulasikan kondisi laboratorium nyata di mana kerusakan peralatan mengharuskan penghentian prosedur.

---

## 📤 Nilai Kembalian

- **Tipe:** `number`
- **Deskripsi:** Total jumlah spesimen yang cocok dengan karakteristik target
- **Catatan:** Jumlah mewakili spesimen yang dianalisis sebelum terjadi kerusakan

---

## 🔬 Konteks Laboratorium

Tantangan ini mensimulasikan metodologi ilmiah nyata di mana:
- **Observasi sistematis** sangat penting untuk pengumpulan data yang akurat
- **Keandalan peralatan** mempengaruhi hasil penelitian  
- **Penanganan error yang tepat** mencegah hasil yang tidak valid
- **Standar dokumentasi** memastikan eksperimen dapat direproduksi

---

## 💡 Contoh Skenario

```javascript
// Contoh data spesimen
const specimens = [
    "daun hijau, batang tipis",
    "bunga kuning, batang tebal", 
    "daun hijau, batang tebal",
    "microscope malfunction",
    "daun hijau, daun lebar"  // Tidak akan dihitung
];

// Karakteristik yang dicari
const targetCharacteristic = "daun hijau";

// Hasil yang diharapkan: 2 (berhenti saat malfunction)
```
