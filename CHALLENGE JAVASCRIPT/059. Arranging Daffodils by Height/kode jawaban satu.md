# 🌼 Fungsi arrangeDaffodils

## 📋 Deskripsi

Fungsi `arrangeDaffodils` adalah sebuah fungsi JavaScript yang digunakan untuk mengurutkan tinggi bunga daffodil dari yang terpendek hingga yang tertinggi. Fungsi ini sangat berguna ketika Anda ingin menyusun data tinggi bunga dalam urutan yang teratur.

## 🔧 Sintaks

```javascript
arrangeDaffodils(daffodilHeights)
```

## 📝 Parameter

| Parameter | Tipe | Deskripsi | Wajib |
|-----------|------|-----------|-------|
| `daffodilHeights` | Array | Array yang berisi angka-angka yang merepresentasikan tinggi bunga daffodil | ✅ Ya |

### Detail Parameter:
- **daffodilHeights**: Harus berupa array yang berisi nilai numerik (angka)
- Nilai dalam array dapat berupa bilangan bulat atau desimal
- Array tidak boleh kosong untuk hasil yang optimal

## 💻 Kode Fungsi

```javascript
function arrangeDaffodils(daffodilHeights) {
    // Mengurutkan array tinggi daffodil dari yang terkecil ke yang terbesar
    // menggunakan metode sort() dengan fungsi perbandingan (a, b) => a - b
    return daffodilHeights.sort((a, b) => a - b);
}
```

## 🔄 Nilai Kembalian

Fungsi ini mengembalikan array baru yang berisi tinggi-tinggi daffodil yang telah diurutkan dari yang terpendek ke yang tertinggi (ascending order).

## 📊 Contoh Penggunaan

### Contoh 1: Array dengan bilangan bulat
```javascript
const tinggiDaffodil = [15, 8, 23, 12, 19];
const hasilUrutan = arrangeDaffodils(tinggiDaffodil);

console.log("Tinggi asli:", tinggiDaffodil);
console.log("Setelah diurutkan:", hasilUrutan);
```

**Output:**
```
Tinggi asli: [15, 8, 23, 12, 19]
Setelah diurutkan: [8, 12, 15, 19, 23]
```

### Contoh 2: Array dengan bilangan desimal
```javascript
const tinggiDaffodiDesimal = [12.5, 8.2, 15.7, 10.1, 9.8];
const hasilUrutanDesimal = arrangeDaffodils(tinggiDaffodiDesimal);

console.log("Tinggi asli:", tinggiDaffodiDesimal);
console.log("Setelah diurutkan:", hasilUrutanDesimal);
```

**Output:**
```
Tinggi asli: [12.5, 8.2, 15.7, 10.1, 9.8]
Setelah diurutkan: [8.2, 9.8, 10.1, 12.5, 15.7]
```

### Contoh 3: Array dengan satu elemen
```javascript
const tinggiSatu = [25];
const hasilSatu = arrangeDaffodils(tinggiSatu);

console.log("Hasil:", hasilSatu); // [25]
```

### Contoh 4: Array kosong
```javascript
const tinggiKosong = [];
const hasilKosong = arrangeDaffodils(tinggiKosong);

console.log("Hasil:", hasilKosong); // []
```

## ⚠️ Catatan Penting

1. **Modifikasi Array**: Fungsi ini akan **mengubah array asli** karena menggunakan metode `sort()`. Jika Anda ingin mempertahankan array asli, buat salinan terlebih dahulu:
   ```javascript
   const arrayAsli = [15, 8, 23, 12, 19];
   const arraySalinan = [...arrayAsli]; // Membuat salinan
   const hasilUrutan = arrangeDaffodils(arraySalinan);
   ```

2. **Tipe Data**: Pastikan semua elemen dalam array adalah angka. Jika ada string atau tipe data lain, hasil pengurutan mungkin tidak sesuai harapan.

3. **Array Kosong**: Fungsi dapat menangani array kosong dan akan mengembalikan array kosong.

## 🎯 Kasus Penggunaan

- Mengurutkan data tinggi tanaman dalam penelitian botani
- Menyusun data pengukuran untuk visualisasi grafik
- Mempersiapkan data untuk analisis statistik
- Mengurutkan nilai-nilai numerik dalam aplikasi web

## 🔗 Metode Terkait

- `Array.prototype.sort()` - Metode JavaScript untuk mengurutkan array
- `Array.prototype.reverse()` - Untuk mengurutkan dari besar ke kecil setelah sort
- `Math.max()` dan `Math.min()` - Untuk mencari nilai maksimum dan minimum

---

*Dokumentasi ini dibuat untuk membantu pemula memahami cara kerja dan penggunaan fungsi `arrangeDaffodils`.*
