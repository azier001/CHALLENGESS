# 🏠 Tantangan House Number Converter

## 📋 Gambaran Challenge

**Tingkat Kesulitan:** `Easy`

Anda adalah seorang turis yang mengunjungi sebuah desa tropis yang indah dengan gubuk-gubuk beratap jerami. Penduduk desa menggunakan sistem penomoran unik untuk rumah mereka, dan mereka membutuhkan bantuan Anda untuk mengonversi nomor rumah biasa mereka ke dalam kode binary khusus dan mengurutkannya dalam urutan terbalik.

---

## 🎯 Deskripsi Tugas

Buat sebuah function bernama `houseNumberConverter` yang menerima `decimalNumbers` sebagai parameter.

### Persyaratan Function

Function Anda harus melakukan tugas-tugas berikut:

1. **Convert** setiap nomor rumah decimal ke representasi binary (sebagai string)
2. **Reverse** urutan dari angka-angka binary yang dihasilkan

---

## 📝 Parameter

| Parameter | Type | Deskripsi |
|-----------|------|-----------|
| `decimalNumbers` | `array` | Sebuah array berisi integer yang merepresentasikan nomor rumah dalam format decimal. Setiap angka akan berupa integer positif. |

---

## 📤 Return Value

Function harus mengembalikan **array of strings**, dimana:
- Setiap string adalah representasi binary dari nomor rumah
- Urutan dari angka-angka binary ini dibalik dari urutan input

---

## 💡 Contoh

### Input
```javascript
[5, 12, 3, 7]
```

### Output
```javascript
["111", "11", "1100", "101"]
```

### Breakdown Step-by-Step

| Step | Decimal | Binary | Posisi |
|------|---------|--------|--------|
| 1 | 5 | "101" | Asli: ke-1 → Final: ke-4 |
| 2 | 12 | "1100" | Asli: ke-2 → Final: ke-3 |
| 3 | 3 | "11" | Asli: ke-3 → Final: ke-2 |
| 4 | 7 | "111" | Asli: ke-4 → Final: ke-1 |

**Hasil Akhir:** `["111", "11", "1100", "101"]`

---

## 🔧 Tips Implementasi

> **Ingat:** Tangani operasi conversion dan reversal secara terpisah untuk kejelasan.

### Built-in Methods yang Berguna
- **Binary conversion:** Gunakan built-in methods JavaScript untuk mengonversi angka ke binary strings
- **Array manipulation:** Manfaatkan array methods untuk membalik urutan

### Alur Proses
```
Input Array → Convert ke Binary → Reverse Order → Output Array
```

---

## 🌟 Kriteria Sukses

- ✅ Function dengan benar mengonversi decimal numbers ke binary strings
- ✅ Function membalik urutan dari resulting array
- ✅ Function menangani positive integers sesuai spesifikasi
- ✅ Code bersih dan mudah dibaca dengan operasi terpisah untuk conversion dan reversal
