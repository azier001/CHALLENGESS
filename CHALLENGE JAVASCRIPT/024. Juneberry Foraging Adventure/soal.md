# 🫐 Juneberry Foraging Adventure
## 📋 Dokumentasi Masalah Programming

---

## 🌟 Gambaran Umum

Bayangkan Anda adalah **Charlie**, seorang katekis yang penuh rasa ingin tahu, sedang mencari buah Juneberry di hari musim panas yang indah. Charlie menemukan sebaris semak dan ingin menghitung buah Juneberry yang dapat dipetik, namun dia memiliki keterbatasan dalam kapasitas membawa buah.

### 🎯 **Misi Utama**
Membuat fungsi `countJuneberries` yang dapat menghitung buah Juneberry dalam sebaris semak hingga mencapai akhir baris atau batas kapasitas maksimum.

---

## 📝 Spesifikasi Fungsi

### **Nama Fungsi:** `countJuneberries`

### **Parameter Input:**
| Parameter | Tipe Data | Deskripsi |
|-----------|-----------|-----------|
| `bushRow` | `string` | String yang merepresentasikan sebaris semak. Setiap karakter mewakili bagian semak: `'J'` = Juneberry, karakter lain = daun/ranting |
| `maxBerries` | `number` | Bilangan bulat yang menunjukkan batas maksimum Juneberry yang ingin dikumpulkan |

### **Return Value:**
- **Tipe:** `string`
- **Format:** Pesan yang menyatakan jumlah Juneberry yang ditemukan dan status pencarian

---

## 🔍 Aturan Pencarian

### ✅ **Yang Dihitung:**
- Hanya karakter `'J'` (huruf besar) yang dianggap sebagai Juneberry
- Case-sensitive: `'j'` (huruf kecil) TIDAK dihitung

### 🛑 **Kondisi Berhenti:**
1. Mencapai batas `maxBerries`
2. Mencapai akhir string `bushRow`

### 📤 **Format Output:**
- **Jika mencapai batas maksimum:** `"Found X Juneberries. Basket full!"`
- **Jika belum mencapai batas:** `"Found X Juneberries. Keep foraging!"`

---

## 🔄 Alur Algoritma

```
1. 🏁 Inisialisasi counter Juneberry = 0
2. 🔄 Loop melalui setiap karakter dalam bushRow
3. 🔍 Jika karakter adalah 'J':
   - Tambahkan counter
4. ⚡ Jika counter = maxBerries ATAU mencapai akhir string:
   - Keluar dari loop
5. 📋 Return string hasil sesuai kondisi
```

---

## 🧪 Contoh Skenario Testing

### **Skenario 1: Basket Penuh**
- **Input:** `bushRow = "JLJJBLJ"`, `maxBerries = 3`
- **Proses:** Menemukan 3 'J' sebelum selesai
- **Expected Output:** `"Found 3 Juneberries. Basket full!"`

### **Skenario 2: Perlu Lanjut Mencari**
- **Input:** `bushRow = "LBLJBL"`, `maxBerries = 5`
- **Proses:** Hanya menemukan 1 'J' dari seluruh string
- **Expected Output:** `"Found 1 Juneberries. Keep foraging!"`

### **Skenario 3: Tidak Ada Juneberry**
- **Input:** `bushRow = "LBLBL"`, `maxBerries = 3`
- **Proses:** Tidak menemukan 'J' sama sekali
- **Expected Output:** `"Found 0 Juneberries. Keep foraging!"`

---

## ⚠️ Catatan Penting

- **Case Sensitivity:** Hanya `'J'` (huruf besar) yang dihitung
- **Efisiensi:** Loop berhenti segera setelah mencapai `maxBerries`
- **Edge Cases:** Pertimbangkan string kosong, maxBerries = 0, dll.

---

## 🎨 Tips Implementasi

💡 **Gunakan loop dengan kondisi break**  
💡 **Perhatikan indeks array untuk menghindari out of bounds**  
💡 **Test dengan berbagai kombinasi input**  
💡 **Pastikan format output string sesuai spesifikasi**

---

> **🌟 Selamat Coding! Semoga Charlie berhasil mengumpulkan Juneberry-nya! 🫐**
