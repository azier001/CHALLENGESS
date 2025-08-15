# 📋 Dokumentasi Fungsi `updateLeatherRegulations`

## 📝 Deskripsi Fungsi

Fungsi `updateLeatherRegulations` digunakan untuk memperbarui regulasi industri kulit berdasarkan indeks suasana hati dewan dan tekanan dari industri kulit. Fungsi ini menerapkan berbagai aturan untuk menambah, menghapus, atau mengubah regulasi yang ada.

## 🔧 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `currentRegulations` | Array | Array yang berisi daftar regulasi saat ini |
| `councilMoodIndex` | Number | Indeks suasana hati dewan (1-10) |
| `leatherIndustryPressure` | Boolean | Status tekanan dari industri kulit (true/false) |

## 📊 Tabel Referensi Karakter councilMoodIndex

| Nilai | Kondisi Dewan | Dampak pada Regulasi |
|-------|---------------|---------------------|
| 1-3 | Mood Buruk/Ketat | Menambah kontrol kualitas yang ketat |
| 4-7 | Mood Netral | Mengubah inspeksi bulanan menjadi triwulan |
| 8-10 | Mood Baik/Longgar | Berpotensi menghapus penilaian dampak lingkungan |

## 🔄 Return Value

**Tipe:** Array  
**Deskripsi:** Array baru yang berisi regulasi yang sudah diperbarui

## 💻 Kode Fungsi

```javascript
function updateLeatherRegulations(currentRegulations, councilMoodIndex, leatherIndustryPressure) {
  // Membuat salinan array regulasi untuk menghindari modifikasi array asli
  let updatedRegulations = [...currentRegulations];
  
  // Aturan 1: Jika councilMoodIndex <= 3 dan "Strict quality control" belum ada, tambahkan regulasi tersebut
  if (councilMoodIndex <= 3 && !updatedRegulations.includes("Strict quality control")) {
    updatedRegulations.push("Strict quality control");
  }
  
  // Aturan 2: Jika councilMoodIndex >= 8 dan ada tekanan industri, hapus "Environmental impact assessment"
  if (councilMoodIndex >= 8 && leatherIndustryPressure) {
    updatedRegulations = updatedRegulations.filter(reg => 
      reg !== "Environmental impact assessment"
    );
  }
  
  // Aturan 3: Jika councilMoodIndex antara 4-7, ubah "Monthly inspections" menjadi "Quarterly inspections"
  if (councilMoodIndex >= 4 && councilMoodIndex <= 7) {
    updatedRegulations = updatedRegulations.map(reg =>
      reg === "Monthly inspections" ? "Quarterly inspections" : reg
    );
  }
  
  // Aturan 4: Jika jumlah regulasi kurang dari 5 dan tidak ada tekanan industri, tambahkan perlindungan konsumen
  if (updatedRegulations.length < 5 && !leatherIndustryPressure) {
    updatedRegulations.push("Consumer protection guidelines");
  }
  
  return updatedRegulations;
}
```

## 🎯 Contoh Penggunaan dan Output

### Contoh 1: Dewan dalam mood buruk
```javascript
const regulations = ["Basic safety standards", "Monthly inspections"];
const result = updateLeatherRegulations(regulations, 2, false);

console.log(result);
// Output: ["Basic safety standards", "Monthly inspections", "Strict quality control", "Consumer protection guidelines"]
```

### Contoh 2: Dewan dalam mood baik dengan tekanan industri
```javascript
const regulations = ["Environmental impact assessment", "Monthly inspections", "Safety protocols"];
const result = updateLeatherRegulations(regulations, 9, true);

console.log(result);
// Output: ["Monthly inspections", "Safety protocols"]
```

### Contoh 3: Dewan dalam mood netral
```javascript
const regulations = ["Monthly inspections", "Safety standards", "Quality checks"];
const result = updateLeatherRegulations(regulations, 5, false);

console.log(result);
// Output: ["Quarterly inspections", "Safety standards", "Quality checks", "Consumer protection guidelines"]
```

### Contoh 4: Regulasi sudah lengkap dengan tekanan industri
```javascript
const regulations = ["Safety standards", "Quality control", "Monthly inspections", "Worker protection", "Export guidelines"];
const result = updateLeatherRegulations(regulations, 6, true);

console.log(result);
// Output: ["Safety standards", "Quality control", "Quarterly inspections", "Worker protection", "Export guidelines"]
```

## 📚 Penjelasan Aturan

### 🔴 Aturan 1: Kontrol Kualitas Ketat
- **Kondisi:** `councilMoodIndex <= 3` DAN "Strict quality control" belum ada
- **Aksi:** Menambahkan "Strict quality control"
- **Tujuan:** Ketika dewan sedang ketat, mereka menambah kontrol kualitas yang lebih ketat
- **Optimasi:** Menggunakan kondisi gabungan untuk efisiensi

### 🟡 Aturan 2: Relaksasi Lingkungan
- **Kondisi:** `councilMoodIndex >= 8` DAN `leatherIndustryPressure = true`
- **Aksi:** Menghapus "Environmental impact assessment"
- **Tujuan:** Dewan yang mood bagus + tekanan industri = regulasi lingkungan dihapus
- **Catatan:** Menggunakan `filter()` untuk menghapus item tertentu

### 🔵 Aturan 3: Perubahan Frekuensi Inspeksi
- **Kondisi:** `councilMoodIndex` antara 4-7 (inklusif)
- **Aksi:** Mengubah "Monthly inspections" menjadi "Quarterly inspections"
- **Tujuan:** Mood netral menghasilkan inspeksi yang lebih jarang
- **Metode:** Menggunakan `map()` untuk transformasi array

### 🟢 Aturan 4: Perlindungan Konsumen
- **Kondisi:** Jumlah regulasi < 5 DAN `leatherIndustryPressure = false`
- **Aksi:** Menambahkan "Consumer protection guidelines"
- **Tujuan:** Ketika regulasi sedikit dan tidak ada tekanan industri, tambah perlindungan konsumen
- **Logika:** Memastikan regulasi minimal untuk perlindungan konsumen

## ⚠️ Catatan Penting

- Fungsi ini **tidak mengubah** array `currentRegulations` yang asli
- Menggunakan spread operator (`...`) untuk membuat salinan array
- Urutan penerapan aturan penting karena setiap aturan mengubah hasil aturan sebelumnya
- Nilai `councilMoodIndex` yang valid adalah 1-10
- Kode telah dioptimasi dengan menggabungkan kondisi di Aturan 1 untuk efisiensi
- Fungsi menggunakan metode array modern seperti `filter()`, `map()`, dan `includes()`

## 🚀 Perbaikan dari Versi Sebelumnya

- **Aturan 1:** Kondisi digabungkan dalam satu `if` statement untuk efisiensi
- **Struktur kode:** Lebih ringkas dan mudah dibaca
- **Komentar:** Lebih spesifik dan informatif dalam bahasa Indonesia
