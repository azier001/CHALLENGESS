# 🔨 Tantangan Workshop Pandai Besi

## 📋 Gambaran Soal

**Nama Function:** `sortMetalPieces`  
**Level Kesulitan:** `Easy`  
**Kategori:** Array Sorting & String Manipulation

---

## 🎯 Deskripsi Tantangan

Buatlah sebuah function yang mengorganisir potongan-potongan logam di workshop pandai besi berdasarkan beratnya, mensimulasikan penggunaan sistem katrol untuk mengangkat. Function ini akan mengurutkan potongan logam berdasarkan berat dan mengembalikan string yang diformat untuk menggambarkan urutan pengangkatan yang optimal.

> **Skenario:** Seorang pandai besi perlu mengangkat berbagai potongan logam menggunakan sistem katrol. Untuk bekerja secara efisien dan aman, potongan yang lebih ringan harus diangkat terlebih dahulu, kemudian secara bertahap ke yang lebih berat.

---

## 🔧 Spesifikasi Function

### Function Signature
```javascript
function sortMetalPieces(pieces)
```

### Parameter
- **`pieces`** *(string array)*: Array dari string yang merepresentasikan potongan logam
  - Format: `"name-weight"`
  - Contoh: `["anvil-50", "hammer-5", "tongs-2"]`

### Return Value
- **Type:** `string`
- **Format:** `"Lift order: 1. [nama piece], 2. [nama piece], ..., N. [nama piece]"`

---

## ⚙️ Langkah-langkah Implementasi

Function harus melakukan operasi berikut:

1. **Parse Data Berat**
   - Ekstrak berat dari setiap string dalam input array
   - Handle format "name-weight" dengan benar

2. **Sort Berdasarkan Berat**
   - Susun potongan logam dalam urutan ascending berdasarkan berat
   - Potongan paling ringan harus muncul pertama

3. **Format Output**
   - Buat string deskriptif yang menunjukkan urutan pengangkatan
   - Tampilkan hanya nama potongan logam (tanpa berat)
   - Gunakan format numbered list untuk kejelasan

---

## 📐 Constraints & Aturan

| Constraint | Deskripsi |
|------------|-------------|
| **Minimum Input** | Array berisi minimal satu potongan logam |
| **Format String** | Setiap string mengikuti pattern "name-weight" dengan tepat |
| **Nilai Berat** | Selalu berupa integer positif |
| **Konvensi Penamaan** | Nama potongan logam tidak akan mengandung hyphens |
| **Integritas Data** | Semua input akan dalam format yang benar |

---

## 💡 Contoh Penggunaan

### Input
```javascript
["anvil-50", "hammer-5", "tongs-2", "horseshoe-3"]
```

### Expected Output
```
"Lift order: 1. tongs, 2. horseshoe, 3. hammer, 4. anvil"
```

### Proses Step-by-step
1. **Parse:** Ekstrak berat → `{tongs: 2, horseshoe: 3, hammer: 5, anvil: 50}`
2. **Sort:** Susun berdasarkan berat → `[tongs-2, horseshoe-3, hammer-5, anvil-50]`
3. **Format:** Buat numbered list yang menampilkan hanya nama potongan logam

---

## 🎨 Detail Format Output

String yang dikembalikan harus mengikuti pattern yang tepat ini:

```
Lift order: 1. [nama piece], 2. [nama piece], ..., N. [nama piece]
```

**Poin Penting:**
- Dimulai dengan "Lift order: "
- Setiap item diberi nomor secara berurutan
- Menampilkan hanya nama potongan logam (berat digunakan untuk sorting tapi tidak ditampilkan)
- List dipisahkan dengan comma
- Tanpa trailing comma

---

## 🔍 Edge Cases yang Perlu Dipertimbangkan

- **Single Item:** Handle array dengan hanya satu potongan logam
- **Berat yang Sama:** Pertahankan urutan yang konsisten untuk potongan dengan berat yang sama
- **Variasi Panjang Nama:** Support nama potongan logam pendek maupun panjang
- **Nilai Berat Besar:** Handle angka berat dengan benar untuk multi-digit

---

## 🏆 Kriteria Keberhasilan

✅ Berhasil parse berat dari setiap string  
✅ Mengurutkan potongan dalam ascending order berdasarkan berat  
✅ Mengembalikan string dengan format yang tepat dengan nama piece saja  
✅ Menangani semua constraints dan edge cases  
✅ Menggunakan berat untuk sorting tapi menampilkan hanya nama dalam output
