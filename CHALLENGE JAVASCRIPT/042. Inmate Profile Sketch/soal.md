# 🎯 Inmate Profile Sketch Challenge

## 📋 Ringkasan Challenge

| **Tingkat Kesulitan** | **Easy** |
|----------------|----------|
| **Nama Function** | `sketchInmateProfile` |
| **Return Type** | String |

---

## 📝 Deskripsi Masalah

Buat sebuah function untuk membantu seorang penjaga penjara membuat sketsa ASCII sederhana dari profil samping seorang narapidana. Penjaga perlu mengatur fitur wajah dengan benar berdasarkan arah menghadap narapidana.

---

## 🔧 Function Signature

```javascript
function sketchInmateProfile(features, facingLeft) {
    // Implementasi Anda di sini
}
```

---

## 📥 Parameter

### `features` (Array)
- **Type**: Array of strings
- **Deskripsi**: Setiap string adalah karakter tunggal yang mewakili fitur wajah
- **Contoh**: `['|', 'O', ')', '-', '>']`

### `facingLeft` (Boolean)
- **Type**: Boolean
- **Deskripsi**: Menunjukkan arah menghadap narapidana
- **Nilai**: 
  - `true` = menghadap ke kiri
  - `false` = menghadap ke kanan

---

## 🎯 Persyaratan

Function harus mengembalikan **single string** yang mewakili sketsa profil narapidana.

---

## 📐 Langkah-langkah Algoritma

Ikuti langkah-langkah berikut untuk membuat sketsa:

### Langkah 1: Periksa Arah
```
JIKA facingLeft adalah true:
    Balik urutan array features
```

### Langkah 2: Gabungkan Karakter
```
Gabungkan semua karakter dalam array features menjadi single string
```

### Langkah 3: Tukar Karakter Arah
```
JIKA facingLeft adalah true:
    Ganti '<' dengan '>' dan '>' dengan '<' dalam string yang dihasilkan
```

---

## ⚠️ Catatan Penting

> **Catatan**: Sketsa harus selalu dalam **single line**, dengan **tanpa spasi** di antara karakter.

---

## 💡 Contoh Penggunaan

```javascript
// Contoh 1: Menghadap Kanan
const features1 = ['|', 'O', ')', '-', '>'];
const result1 = sketchInmateProfile(features1, false);
// Output yang diharapkan: "|O)->"

// Contoh 2: Menghadap Kiri
const features2 = ['|', 'O', ')', '-', '>'];
const result2 = sketchInmateProfile(features2, true);
// Output yang diharapkan: "<-)|O"
```

---

## 🔍 Poin Penting yang Perlu Diingat

- ✅ Selalu return single string
- ✅ Tidak ada spasi di antara karakter
- ✅ Balik urutan array ketika menghadap kiri
- ✅ Tukar karakter '<' dan '>' ketika menghadap kiri
- ✅ Proses langkah-langkah dalam urutan yang benar

---

## 🚀 Memulai

1. Buat function dengan nama dan parameter yang telah ditentukan
2. Implementasikan logika mengikuti tiga langkah yang telah dijelaskan
3. Test dengan berbagai array features dan arah yang berbeda
4. Pastikan output sesuai dengan format yang diharapkan

---

*Selamat mengerjakan implementasinya! 🎉*
