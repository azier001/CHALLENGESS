# 🖨️ Printing Press Plate Adjuster

## 📋 Gambaran Challenge
**Level Kesulitan:** `Easy`

Sebagai operator mesin cetak, Anda bertugas untuk menyesuaikan plate untuk publikasi majalah yang beragam. Setiap plate mewakili halaman majalah, dan Anda perlu melakukan penyesuaian khusus berdasarkan konten setiap halaman.

---

## 🎯 Tujuan

Buat function bernama `adjustPrintingPlates` yang memproses section majalah dan menerapkan penyesuaian khusus berdasarkan kondisi yang telah ditentukan.

### Function Signature
```javascript
function adjustPrintingPlates(magazineSections)
```

---

## 📝 Parameter

| Parameter | Type | Deskripsi |
|-----------|------|-----------|
| `magazineSections` | `Array<Array<string>>` | Array 2D dari string dimana setiap inner array mewakili halaman majalah |

---

## 🔧 Aturan Pemrosesan

Function harus memproses setiap halaman sesuai dengan kondisi berikut **berdasarkan urutan prioritas**:

### 1. 🚫 **Filter Advertisement**
- **Kondisi:** Jika halaman mengandung kata `"advertisement"`
- **Aksi:** Skip halaman sepenuhnya (jangan sertakan dalam output)
- **Implementasi:** Gunakan statement `continue`

### 2. 🔄 **Pembalikan Kata Panjang**
- **Kondisi:** Jika halaman mengandung kata yang lebih panjang dari 10 karakter
- **Aksi:** Reverse seluruh halaman
- **Implementasi:** Gunakan method array `reverse()`

### 3. ⚖️ **Pembalikan Element Tengah**
- **Kondisi:** Jika halaman mengandung tepat 5 element
- **Aksi:** Reverse hanya 3 element tengah (indeks 1, 2, 3)
- **Implementasi:** Extract element tengah, reverse mereka, lalu rekonstruksi

### 4. ✅ **Tanpa Perubahan**
- **Kondisi:** Tidak ada kondisi di atas yang terpenuhi
- **Aksi:** Biarkan halaman apa adanya

---

## 📤 Return Value

**Type:** `Array<Array<string>>`  
**Deskripsi:** Array 2D dari string yang mewakili section majalah yang telah disesuaikan

---

## 💡 Template Implementasi

```javascript
function adjustPrintingPlates(magazineSections) {
  let adjustedSections = [];
  
  for (let page of magazineSections) {
    // Kode Anda di sini
    // Ingat untuk menggunakan continue untuk skip advertisement
    // Gunakan method reverse() array untuk melakukan reverse jika diperlukan
    // Jangan lupa untuk push halaman yang sudah disesuaikan ke adjustedSections
  }
  
  return adjustedSections;
}
```

---

## 🛠️ Persyaratan Teknis

### Konsep Kunci yang Harus Diimplementasikan:
- ✅ **Control Flow:** Penggunaan efektif statement `break` dan `continue`
- ✅ **Manipulasi Array:** Bekerja dengan array 2D
- ✅ **Pemrosesan String:** Validasi panjang kata dan pengecekan konten
- ✅ **Algoritma Reversing:** Teknik pembalikan array
- ✅ **Logika Matematis:** Indexing array dan kalkulasi panjang

### Best Practice:
- Handle edge case dengan tepat
- Pertahankan struktur array asli
- Gunakan nama variable yang deskriptif
- Implementasikan kode yang bersih dan mudah dibaca

---

## 🧪 Contoh Workflow

```
Input Page: ["word1", "word2", "advertisement", "word4"]
↓
Check: Mengandung "advertisement"? ✅ YA
↓
Aksi: Skip page (lanjut ke page berikutnya)
↓
Result: Page tidak disertakan dalam output
```

```
Input Page: ["short", "word", "supercalifragilisticexpialidocious"]
↓
Check: Mengandung kata > 10 karakter? ✅ YA
↓
Aksi: Reverse seluruh page
↓
Result: ["supercalifragilisticexpialidocious", "word", "short"]
```

---

## 📚 Tujuan Pembelajaran

Dengan menyelesaikan challenge ini, Anda akan berlatih:

- 🎯 **Conditional Logic:** Mengimplementasikan decision tree yang kompleks
- 🔄 **Method Array:** Menggunakan function manipulasi array built-in
- 📊 **Data Structure:** Bekerja dengan array multi-dimensi
- 🧮 **Desain Algorithm:** Membuat workflow pemrosesan yang efisien
- 🐛 **Problem Solving:** Memecah requirement kompleks menjadi langkah-langkah yang dapat dikelola

---

*Semoga berhasil dengan implementasi Anda! Ingat untuk test function Anda dengan berbagai skenario input untuk memastikan semua kondisi ditangani dengan benar.* 🚀
