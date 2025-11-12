# 📋 Dokumentasi Fungsi `processTestResults`

## 🎯 Deskripsi

Fungsi `processTestResults` adalah fungsi JavaScript yang digunakan untuk memproses dan menggabungkan dua array hasil testing (hasil awal dan hasil akhir). Fungsi ini akan menambahkan prefix/awalan pada setiap elemen array dan menggabungkannya dengan pemisah untuk menghasilkan laporan yang terstruktur.

## 📝 Sintaks

```javascript
processTestResults(preliminaryResults, finalResults)
```

## 🔧 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `preliminaryResults` | Array | Array yang berisi hasil-hasil testing awal/pendahuluan |
| `finalResults` | Array | Array yang berisi hasil-hasil testing akhir/kesimpulan |

### Penjelasan Parameter:

- **preliminaryResults**: Berisi daftar hasil testing tahap awal. Setiap elemen akan diberi prefix "Status: "
- **finalResults**: Berisi daftar hasil testing tahap akhir. Setiap elemen akan diberi prefix "Conclusion: "

## 📤 Return Value

Fungsi ini mengembalikan sebuah **Array** yang berisi:
1. Semua hasil preliminary dengan prefix "Status: "
2. String pemisah "---"
3. Semua hasil final dengan prefix "Conclusion: "

## 💻 Code Lengkap

```javascript
function processTestResults(preliminaryResults, finalResults) {
  // Menambahkan prefix "Status: " pada setiap hasil preliminary
  const prefixedPreliminary = preliminaryResults.map(result => "Status: " + result);
  
  // Menambahkan prefix "Conclusion: " pada setiap hasil final
  const prefixedFinal = finalResults.map(result => "Conclusion: " + result);
  
  // Menggabungkan array preliminary, pemisah, dan array final
  return [...prefixedPreliminary, "---", ...prefixedFinal];
}
```

## 🎨 Cara Kerja

1. **Map Preliminary Results**: Fungsi menggunakan `map()` untuk iterasi setiap elemen di `preliminaryResults` dan menambahkan string "Status: " di depannya
2. **Map Final Results**: Fungsi menggunakan `map()` untuk iterasi setiap elemen di `finalResults` dan menambahkan string "Conclusion: " di depannya
3. **Spread & Combine**: Menggunakan spread operator (`...`) untuk menggabungkan ketiga array dengan pemisah "---" di tengahnya

## 📊 Contoh Penggunaan

### Contoh 1: Testing Sederhana

```javascript
const preliminary = ["Test dimulai", "Memuat data"];
const final = ["Berhasil", "Semua test lulus"];

const result = processTestResults(preliminary, final);
console.log(result);
```

**Output:**
```javascript
[
  "Status: Test dimulai",
  "Status: Memuat data",
  "---",
  "Conclusion: Berhasil",
  "Conclusion: Semua test lulus"
]
```

### Contoh 2: Testing dengan Banyak Tahapan

```javascript
const preliminary = [
  "Koneksi database OK",
  "API endpoint tersedia",
  "Autentikasi berhasil"
];

const final = [
  "Tidak ada error",
  "Performance baik",
  "Test selesai"
];

const result = processTestResults(preliminary, final);
console.log(result);
```

**Output:**
```javascript
[
  "Status: Koneksi database OK",
  "Status: API endpoint tersedia",
  "Status: Autentikasi berhasil",
  "---",
  "Conclusion: Tidak ada error",
  "Conclusion: Performance baik",
  "Conclusion: Test selesai"
]
```

## 🔍 Penjelasan untuk Pemula

### Apa itu `map()`?
`map()` adalah method array yang digunakan untuk membuat array baru dengan mengubah setiap elemen dari array lama. Seperti memberikan stempel pada setiap kertas.

### Apa itu Spread Operator (`...`)?
Spread operator (`...`) digunakan untuk "membuka" atau "menyebarkan" isi array. Bayangkan seperti membuka kotak dan mengeluarkan semua isinya.

### Mengapa Pakai Array di Return?
Array bracket `[...]` digunakan untuk membuat array baru yang berisi gabungan dari semua elemen.

## ✨ Kelebihan Fungsi Ini

- ✅ **Mudah dibaca**: Struktur code yang jelas dan terorganisir
- ✅ **Fleksibel**: Bisa menerima array dengan jumlah elemen berapapun
- ✅ **Reusable**: Bisa digunakan di berbagai bagian aplikasi
- ✅ **Terstruktur**: Hasil output yang rapi dengan pemisah yang jelas

## 🎓 Catatan Penting

- Kedua parameter harus berupa **Array**
- Jika salah satu array kosong, hasilnya tetap valid dengan array kosong di bagian tersebut
- Pemisah "---" selalu muncul di tengah, bahkan jika salah satu array kosong
- Fungsi ini tidak mengubah array original (immutable)

---

💡 **Tips**: Fungsi ini sangat berguna untuk membuat laporan testing yang terstruktur dan mudah dibaca!
