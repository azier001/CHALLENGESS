# 🥭 Challenge Persiapan Tropical Fruit Salad

## 🏷️ Overview Challenge
**Difficulty Level:** `Easy`  
**Function Name:** `tropicalFruitSalad`

---

## 📖 Latar Belakang Cerita
Kamu adalah seorang **chef di pulau tropis** yang terkenal dengan kemampuan menciptakan kembali masakan tradisional. Misi kamu adalah menyiapkan tropical fruit salad yang unik menggunakan array buah-buahan segar. Challenge ini mensimulasikan proses persiapan menggunakan teknik manipulasi array dasar termasuk slicing, operasi string, dan array methods.

---

## 🎯 Requirements Challenge

### Function Signature
```javascript
function tropicalFruitSalad(fruits) {
    // Implementasi kamu di sini
}
```

### Parameters
| Parameter | Type | Deskripsi |
|-----------|------|-----------|
| `fruits` | `Array<string>` | Array berisi nama-nama buah (strings) |

### Return Value
- **Type:** `Array<string>`
- **Deskripsi:** Array yang merepresentasikan tropical fruit salad yang sudah disiapkan

---

## ⚙️ Langkah-Langkah Processing

Function harus melakukan operasi berikut **secara berurutan**:

### 1. 🍊 Penghilangan Lapisan Luar
- Hapus buah **pertama** dan **terakhir** dari array
- Ini merepresentasikan proses mengupas lapisan luar dari seleksi buah

### 2. 🍯 Proses Pemanis (Even Indices)
- Untuk setiap buah pada posisi **even-indexed** `(0, 2, 4, ...)`
- Tambahkan `'y'` di akhir nama buah
- Ini mensimulasikan proses pemberian pemanis

### 3. 🔪 Proses Pemotongan (Odd Indices)
- Untuk setiap buah pada posisi **odd-indexed** `(1, 3, 5, ...)`
- Hapus **karakter terakhir** dari nama buah
- Ini merepresentasikan proses pemotongan

### 4. 🔄 Pencampuran Salad
- **Reverse** urutan semua buah yang tersisa
- Langkah terakhir ini mencampur salad yang sudah disiapkan

---

## ⚠️ Special Cases

> **Catatan Penting:** Jika setelah menghapus buah pertama dan terakhir, array menjadi kosong, return **empty array** `[]`.

---

## 💡 Contoh Walkthrough

```javascript
// Input
const fruits = ["mango", "pineapple", "papaya", "coconut", "banana"];

// Step 1: Hapus yang pertama dan terakhir
// ["pineapple", "papaya", "coconut"]

// Step 2 & 3: Process berdasarkan index
// Index 0 (even): "pineapple" → "pineappley"
// Index 1 (odd): "papaya" → "papay" 
// Index 2 (even): "coconut" → "coconuty"
// Hasil: ["pineappley", "papay", "coconuty"]

// Step 4: Reverse array
// Hasil akhir: ["coconuty", "papay", "pineappley"]
```

---

## 🎨 Tips Implementasi

- Gunakan array slicing methods untuk step 1
- Pertimbangkan menggunakan loop dengan pengecekan index untuk steps 2 & 3
- Ingat untuk handle edge case empty array
- String concatenation dan substring methods akan berguna
- Jangan lupa untuk reverse hasil akhir

---

## 🏁 Kriteria Sukses

Solusi kamu harus:
- ✅ Handle semua ukuran array dengan benar
- ✅ Menerapkan transformasi dalam urutan yang benar
- ✅ Return empty array ketika diperlukan
- ✅ Membedakan dengan benar antara even dan odd indices
- ✅ Melakukan reverse hasil akhir dengan benar

Selamat coding! 🌴👨‍🍳
