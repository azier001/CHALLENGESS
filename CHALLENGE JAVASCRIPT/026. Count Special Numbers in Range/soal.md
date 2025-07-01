# 🔢 Count Special Numbers in Range

## 📋 Ringkasan Tantangan

| **Kesulitan** | **Jenis** | **Area Fokus** |
|---------------|-----------|----------------|
| 🟢 **Mudah** | Algoritma | Kontrol Loop & Kondisi |

---

## 🎯 Tujuan

Buat sebuah function bernama `countSpecialNumbers` yang menghitung dan mengembalikan jumlah **angka spesial** dalam rentang yang diberikan (termasuk batas awal dan akhir).

---

## 🔍 Definisi Angka Spesial

Sebuah angka dianggap **spesial** jika memenuhi **KEDUA** kriteria berikut:

### ✅ Kriteria 1: Habis Dibagi
- Angka tersebut harus habis dibagi **3** ATAU **5**

### ✅ Kriteria 2: Tidak Mengandung Angka 7
- Angka tersebut **TIDAK BOLEH** mengandung digit **7**

---

## 📝 Spesifikasi Function

### Bentuk Function
```javascript
function countSpecialNumbers(start, end)
```

### Parameter
| Parameter | Tipe | Keterangan |
|-----------|------|------------|
| `start` | `number` | Awal rentang *(termasuk)* |
| `end` | `number` | Akhir rentang *(termasuk)* |

### Nilai yang Dikembalikan
- **Tipe**: `number` (bilangan bulat)
- **Keterangan**: Jumlah angka spesial dalam rentang yang ditentukan

---

## 🛠️ Persyaratan Implementasi

### Elemen Wajib
- ✅ Gunakan statement `break` dan `continue` untuk kontrol loop
- ✅ Function harus terdiri dari **10-19 baris kode**
- ✅ Implementasikan kontrol alur yang efisien untuk meningkatkan performa

### Pendekatan yang Disarankan
1. **Inisialisasi** counter untuk menghitung angka spesial
2. **Loop** melalui angka dari `start` sampai `end` (termasuk keduanya)
3. **Cek pembagian** dengan 3 atau 5 → gunakan `continue` jika tidak habis dibagi
4. **Cek digit 7** → gunakan `continue` jika mengandung digit 7
5. **Tambahkan counter** jika angka lolos kedua pengecekan
6. **Kembalikan** nilai counter akhir

---

## 💡 Konsep Penting

### Statement Kontrol Loop
- **`continue`**: Lewati iterasi saat ini dan lanjut ke iterasi berikutnya
- **`break`**: Keluar dari loop sepenuhnya (jika diperlukan)

### Tips Efisiensi
- Gunakan `continue` untuk melewati pengecekan yang tidak perlu
- Urutkan kondisi dari yang paling mungkin gagal ke yang paling tidak mungkin

---

## 📊 Contoh Analisis Rentang

### Rentang Contoh: 10-20
Mari kita analisis angka mana yang akan menjadi spesial:

| Angka | Habis dibagi 3 atau 5? | Mengandung 7? | Spesial? |
|-------|------------------------|---------------|----------|
| 10 | ✅ (÷5) | ❌ | ✅ **YA** |
| 11 | ❌ | ❌ | ❌ Tidak |
| 12 | ✅ (÷3) | ❌ | ✅ **YA** |
| 13 | ❌ | ❌ | ❌ Tidak |
| 14 | ❌ | ❌ | ❌ Tidak |
| 15 | ✅ (÷3,÷5) | ❌ | ✅ **YA** |
| 16 | ❌ | ❌ | ❌ Tidak |
| 17 | ❌ | ✅ | ❌ Tidak |
| 18 | ✅ (÷3) | ❌ | ✅ **YA** |
| 19 | ❌ | ❌ | ❌ Tidak |
| 20 | ✅ (÷5) | ❌ | ✅ **YA** |

**Hasil**: 5 angka spesial dalam rentang 10-20

---

## 🎲 Test Case yang Perlu Dipertimbangkan

### Kasus Ekstrem
- Rentang dengan hanya satu angka
- Rentang di mana start sama dengan end
- Rentang tanpa angka spesial
- Rentang dengan angka yang mengandung 7
- Angka negatif dalam rentang

### Kasus Performa
- Rentang besar (1-1000)
- Rentang dengan banyak kelipatan 3 dan 5

---

## 🏆 Kriteria Keberhasilan

- ✅ Function dengan benar mengidentifikasi angka spesial
- ✅ Penggunaan statement `continue` dan `break` yang tepat
- ✅ Kode antara 10-19 baris
- ✅ Implementasi kontrol loop yang efisien
- ✅ Menangani kasus ekstrem dengan baik

---

## 📚 Hasil Pembelajaran

Setelah menyelesaikan tantangan ini, kamu akan berlatih:
- **Kontrol loop** dengan `break` dan `continue`
- **Logika kondisional** dengan beberapa kriteria
- **Manipulasi string** untuk pengecekan digit
- **Optimisasi efisiensi** algoritma
- **Penanganan kasus ekstrem**

---

## 🤔 Penjelasan untuk Pemula

### Apa itu "Habis Dibagi"?
Angka A habis dibagi angka B jika sisa pembagian A ÷ B adalah 0.
- Contoh: 15 habis dibagi 3 karena 15 ÷ 3 = 5 sisa 0
- Contoh: 15 habis dibagi 5 karena 15 ÷ 5 = 3 sisa 0

### Bagaimana Cek Digit 7?
Kita perlu mengecek apakah angka 7 ada dalam suatu bilangan:
- Contoh: 17 mengandung digit 7 ❌
- Contoh: 25 tidak mengandung digit 7 ✅

### Kapan Gunakan `continue`?
Gunakan `continue` ketika kita ingin melewati angka yang tidak memenuhi syarat dan langsung lanjut ke angka berikutnya, tanpa perlu mengecek kondisi lainnya.

---

*Semangat dalam implementasinya! 🚀*
