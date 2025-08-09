# 🐚 Shell Collector Simulator

## 📝 Gambaran Challenge

**Tingkat Kesulitan:** `Easy`

Buat sebuah function yang mensimulasikan pengumpulan kerang di pantai berdasarkan command yang diberikan. Challenge ini berfokus pada manipulasi array dan logika kondisional.

---

## 🎯 Tujuan

Implementasikan sebuah function bernama `collectShells` yang memproses serangkaian command untuk memodifikasi koleksi kerang.

---

## 🔧 Spesifikasi Function

### Function Signature
```javascript
function collectShells(shells, commands)
```

### Parameter

| Parameter | Type | Deskripsi |
|-----------|------|-----------|
| `shells` | `Array<number>` | Array integer positif yang merepresentasikan jenis kerang yang telah dikumpulkan |
| `commands` | `Array<number>` | Array integer yang merepresentasikan command yang akan dijalankan |

### Return Value
- **Type:** `Array<number>`
- **Deskripsi:** Array shells yang telah dimodifikasi setelah memproses semua command

---

## ⚡ Logika Command

Function memproses command berdasarkan tanda bilangan:

### ✅ Bilangan Positif
- **Aksi:** Mengumpulkan kerang baru
- **Perilaku:** Menambahkan angka ke akhir array `shells`

### ❌ Bilangan Negatif  
- **Aksi:** Membuang kerang
- **Perilaku:** Menghapus kerang **terakhir yang dikumpulkan** dari jenis yang sesuai (jika ada)
- **Syarat Khusus:** Gunakan statement `continue` saat menghapus kerang

---

## 📋 Aturan Processing

1. **Processing Berurutan:** Proses setiap command sesuai urutan kemunculannya
2. **Pencocokan Type:** Untuk command negatif, cocokkan nilai absolut dengan jenis kerang
3. **Occurrence Terakhir:** Selalu hapus occurrence terakhir (paling kanan) dari jenis kerang
4. **Penghapusan Kondisional:** Hanya hapus jika jenis kerang ada dalam koleksi
5. **Modifikasi Array:** Modifikasi array `shells` secara langsung berdasarkan command

---

## 💡 Panduan Implementasi

### Requirement Utama
- ✅ Handle command positif dengan menambahkan ke array
- ✅ Handle command negatif dengan menghapus occurrence terakhir
- ✅ Gunakan statement `continue` untuk operasi penghapusan
- ✅ Pertahankan urutan asli untuk kerang yang tersisa
- ✅ Return array yang telah dimodifikasi

### Edge Case yang Perlu Dipertimbangkan
- Array shells awal yang kosong
- Command yang mereferensikan jenis kerang yang tidak ada
- Multiple kerang dengan jenis yang sama
- Command kosong
- Command dengan nilai 0

---

## 📊 Contoh Skenario

### Skenario 1: Operasi Dasar
```
Initial: [1, 2, 3]
Commands: [4, -2, 5]
Result: [1, 3, 4, 5]
```
*Penjelasan: Tambah 4, hapus 2, tambah 5*

### Skenario 2: Multiple Type yang Sama
```
Initial: [1, 2, 1, 3]
Commands: [-1]
Result: [1, 2, 3]
```
*Penjelasan: Hapus occurrence terakhir dari kerang type 1*

### Skenario 3: Kerang Tidak Ada
```
Initial: [1, 2, 3]
Commands: [-4, 5]
Result: [1, 2, 3, 5]
```
*Penjelasan: Kerang type 4 tidak ada, jadi tambah 5*

---

## 🏆 Kriteria Keberhasilan

Solusi Anda harus:
- ✅ Menangani command positif dan negatif dengan benar
- ✅ Mempertahankan urutan array yang tepat setelah modifikasi
- ✅ Menggunakan statement `continue` sesuai spesifikasi
- ✅ Menangani edge case dengan baik
- ✅ Return state akhir array shells yang benar

---

## 🚀 Memulai

1. Buat function `collectShells` dengan parameter yang tepat
2. Implementasikan loop untuk memproses command secara berurutan  
3. Tambahkan logika kondisional untuk command positif/negatif
4. Implementasikan logika penghapusan kerang untuk command negatif
5. Test dengan berbagai skenario untuk memastikan kebenaran

Selamat bersenang-senang dengan petualangan mengumpulkan kerang! 🏖️
