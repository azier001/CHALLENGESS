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
    const index13 = cropsArray.indexOf(13);
    
    // Jika angka 13 tidak ditemukan, urutkan seluruh array
    if (index13 === -1) {
        return cropsArray.sort((a, b) => a - b);
    }
    
    // Jika angka 13 ditemukan, urutkan hanya elemen sebelum angka 13
    const beforeThirteen = cropsArray.slice(0, index13);
    const fromThirteenOnwards = cropsArray.slice(index13);
    
    // Urutkan bagian sebelum angka 13 dan gabungkan dengan sisanya
    return beforeThirteen.sort((a, b) => a - b).concat(fromThirteenOnwards);
}
```

## 🎯 Cara Kerja Fungsi

1. **Pencarian Angka 13**: Fungsi mencari posisi (indeks) angka 13 dalam array menggunakan method `indexOf()`
2. **Kondisi 1 - Angka 13 Tidak Ada**: Jika angka 13 tidak ditemukan (indeks = -1), maka seluruh array akan diurutkan dari terkecil ke terbesar
3. **Kondisi 2 - Angka 13 Ditemukan**: 
   - Array dibagi menjadi 2 bagian: sebelum angka 13 dan dari angka 13 ke belakang
   - Bagian sebelum angka 13 diurutkan dari terkecil ke terbesar
   - Bagian dari angka 13 ke belakang tetap pada urutan aslinya
   - Kedua bagian digabungkan kembali

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

## 🎭 Tabel Karakter Khusus

| Karakter/Angka | Fungsi | Perilaku |
|----------------|--------|----------|
| `13` | Pembatas | Menghentikan proses pengurutan. Elemen dari posisi ini ke belakang tetap pada urutan asli |
| Angka lainnya | Data normal | Akan diurutkan jika berada sebelum angka 13 |

## 💡 Tips untuk Pemula

- **Method `indexOf()`**: Mengembalikan indeks pertama elemen yang dicari, atau -1 jika tidak ditemukan
- **Method `slice()`**: Membuat salinan sebagian array tanpa mengubah array asli
- **Method `sort()`**: Mengurutkan array. `(a, b) => a - b` berarti urutan naik (ascending)
- **Method `concat()`**: Menggabungkan dua array menjadi satu array baru

## ⚠️ Hal yang Perlu Diperhatikan

- Fungsi ini hanya akan mengenali angka 13 **yang pertama** ditemukan dalam array
- Array asli tidak akan berubah karena menggunakan method yang tidak mengubah array original
- Fungsi ini dirancang khusus untuk array yang berisi angka
