# 📚 Dokumentasi Fungsi `sortCrops`

## 📋 Deskripsi Fungsi

Fungsi `sortCrops` adalah fungsi JavaScript yang melakukan pengurutan (sorting) pada array angka dengan aturan khusus. Fungsi ini akan mengurutkan elemen-elemen dalam array dari yang terkecil ke terbesar, **tetapi hanya sampai sebelum angka 13 ditemukan**. Jika angka 13 ditemukan, maka elemen dari angka 13 ke belakang akan tetap pada posisi aslinya tanpa diurutkan.

## ⚙️ Parameter

| Parameter | Tipe | Deskripsi | Contoh |
|-----------|------|-----------|---------|
| `cropsArray` | Array | Array berisi angka-angka yang akan diurutkan | `[5, 2, 13, 8, 1]` |

## 🔧 Kode Fungsi

```javascript
function sortCrops(cropsArray) {
  // Mencari indeks angka 13 dalam array
  const index = cropsArray.indexOf(13);
  
  // Jika angka 13 ditemukan
  if (index !== -1) {
    // Membagi array menjadi bagian kiri (sebelum 13) dan kanan (dari 13 ke belakang)
    const left = cropsArray.slice(0, index);
    const right = cropsArray.slice(index);
    
    // Mengurutkan bagian kiri dan menggabungkan dengan bagian kanan menggunakan spread operator
    return [...left.sort((a, b) => a - b), ...right];
  }
  
  // Jika angka 13 tidak ditemukan, urutkan seluruh array
  return cropsArray.sort((a, b) => a - b);
}
```

## 🎯 Cara Kerja Fungsi

1. **Pencarian Angka 13**: Fungsi mencari posisi (indeks) angka 13 dalam array menggunakan method `indexOf()`
2. **Kondisi 1 - Angka 13 Ditemukan**: 
   - Array dibagi menjadi 2 bagian: `left` (sebelum angka 13) dan `right` (dari angka 13 ke belakang)
   - Bagian `left` diurutkan dari terkecil ke terbesar
   - Bagian `right` tetap pada urutan aslinya
   - Kedua bagian digabungkan menggunakan spread operator (`...`)
3. **Kondisi 2 - Angka 13 Tidak Ada**: Jika angka 13 tidak ditemukan, maka seluruh array akan diurutkan dari terkecil ke terbesar

## 📊 Contoh Penggunaan dan Output

### Contoh 1: Array Tanpa Angka 13
```javascript
const crops1 = [8, 3, 1, 9, 5];
const result1 = sortCrops(crops1);
console.log(result1);
// Output: [1, 3, 5, 8, 9]
```

### Contoh 2: Array Dengan Angka 13 di Tengah
```javascript
const crops2 = [7, 2, 9, 13, 4, 1, 8];
const result2 = sortCrops(crops2);
console.log(result2);
// Output: [2, 7, 9, 13, 4, 1, 8]
```

### Contoh 3: Array Dengan Angka 13 di Awal
```javascript
const crops3 = [13, 6, 2, 8];
const result3 = sortCrops(crops3);
console.log(result3);
// Output: [13, 6, 2, 8]
```

### Contoh 4: Array Dengan Angka 13 di Akhir
```javascript
const crops4 = [5, 9, 1, 3, 13];
const result4 = sortCrops(crops4);
console.log(result4);
// Output: [1, 3, 5, 9, 13]
```

### Contoh 5: Array Dengan Beberapa Angka 13
```javascript
const crops5 = [6, 3, 13, 7, 13, 2];
const result5 = sortCrops(crops5);
console.log(result5);
// Output: [3, 6, 13, 7, 13, 2]
// Catatan: Hanya 13 pertama yang menjadi pembatas
```

## 🎭 Tabel Karakter Khusus

| Karakter/Angka | Fungsi | Perilaku |
|----------------|--------|----------|
| `13` | Pembatas | Menghentikan proses pengurutan. Elemen dari posisi ini ke belakang tetap pada urutan asli |
| Angka lainnya | Data normal | Akan diurutkan jika berada sebelum angka 13 |

## 💡 Tips untuk Pemula

- **Method `indexOf()`**: Mengembalikan indeks pertama elemen yang dicari, atau -1 jika tidak ditemukan
- **Method `slice()`**: Membuat salinan sebagian array tanpa mengubah array asli
- **Method `sort()`**: Mengurutkan array. `(a, b) => a - b` berarti urutan naik (ascending)
- **Spread Operator (`...`)**: Menyebarkan elemen array untuk menggabungkan array dengan cara yang lebih modern
- **Operator `!==`**: Membandingkan nilai dan tipe data, kebalikan dari `===`

## ⚠️ Hal yang Perlu Diperhatikan

- Fungsi ini hanya akan mengenali angka 13 **yang pertama** ditemukan dalam array
- Array asli tidak akan berubah karena menggunakan method yang tidak mengubah array original
- Fungsi ini dirancang khusus untuk array yang berisi angka
- Menggunakan spread operator (`...`) yang merupakan sintaks ES6, pastikan environment mendukung fitur ini

## 🆚 Perbedaan dengan Versi Sebelumnya

| Aspek | Versi Lama | Versi Baru |
|-------|------------|------------|
| **Penggabungan Array** | `concat()` | Spread operator (`...`) |
| **Struktur Kondisi** | `if-else` terpisah | Kondisi terbalik dengan early return |
| **Keterbacaan Kode** | Lebih verbose | Lebih ringkas dan modern |
| **Performance** | Sedikit lebih lambat | Sedikit lebih cepat dengan spread operator |
