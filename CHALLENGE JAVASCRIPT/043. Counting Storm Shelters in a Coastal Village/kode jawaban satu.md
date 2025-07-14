# 🏠 Dokumentasi Fungsi findStormShelters

## 📝 Deskripsi Fungsi

Fungsi `findStormShelters` adalah sebuah algoritma yang menghitung jumlah tempat perlindungan badai (storm shelter) berdasarkan ketinggian dinding. Fungsi ini menggunakan pendekatan **greedy algorithm** dengan iterasi dari kanan ke kiri untuk menemukan dinding-dinding yang dapat berfungsi sebagai tempat berlindung.

Sebuah dinding dianggap sebagai tempat perlindungan badai jika ketinggiannya **lebih tinggi** dari semua dinding yang berada di sebelah kanannya.

## 🔧 Parameter

| Parameter | Tipe | Wajib | Deskripsi |
|-----------|------|-------|-----------|
| `wallHeights` | Array of Numbers | ✅ | Array yang berisi ketinggian dinding-dinding yang akan diperiksa |

## 📊 Return Value

| Tipe | Deskripsi |
|------|-----------|
| `Number` | Jumlah total dinding yang dapat berfungsi sebagai tempat perlindungan badai |

## 💻 Kode Fungsi

```javascript
function findStormShelters(wallHeights) {
  let maxHeight = 0;        // Ketinggian maksimum yang ditemukan sejauh ini
  let shelterCount = 0;     // Penghitung jumlah tempat perlindungan
  
  // Iterasi dari kanan ke kiri untuk memeriksa setiap dinding
  for (let i = wallHeights.length - 1; i >= 0; i--) {
    // Jika dinding saat ini lebih tinggi dari maksimum yang pernah ditemukan,
    // maka dinding ini adalah tempat perlindungan badai
    if (wallHeights[i] > maxHeight) {
      shelterCount++;                   // Tambah penghitung tempat perlindungan
      maxHeight = wallHeights[i];       // Update ketinggian maksimum
    }
  }
  
  return shelterCount;      // Kembalikan jumlah total tempat perlindungan
}
```

## 🎯 Cara Kerja Algoritma

1. **Inisialisasi**: Mulai dengan `maxHeight = 0` dan `shelterCount = 0`
2. **Iterasi Mundur**: Periksa setiap dinding dari kanan ke kiri
3. **Pemeriksaan Ketinggian**: Jika dinding saat ini lebih tinggi dari `maxHeight`
4. **Update**: Tambahkan ke `shelterCount` dan perbarui `maxHeight`
5. **Return**: Kembalikan total jumlah tempat perlindungan

## 📋 Contoh Penggunaan dan Output

### Contoh 1: Kasus Sederhana
```javascript
const heights1 = [3, 5, 2, 7, 1];
console.log(findStormShelters(heights1));
// Output: 2
```

**Penjelasan**: 
- Dinding dengan ketinggian 7 (indeks 3) → tempat perlindungan ✅
- Dinding dengan ketinggian 5 (indeks 1) → tempat perlindungan ✅
- Total: 2 tempat perlindungan

### Contoh 2: Dinding Menurun
```javascript
const heights2 = [6, 4, 3, 2, 1];
console.log(findStormShelters(heights2));
// Output: 5
```

**Penjelasan**: 
Semua dinding adalah tempat perlindungan karena setiap dinding lebih tinggi dari semua dinding di sebelah kanannya.

### Contoh 3: Dinding Menaik
```javascript
const heights3 = [1, 2, 3, 4, 5];
console.log(findStormShelters(heights3));
// Output: 1
```

**Penjelasan**: 
Hanya dinding tertinggi (ketinggian 5) yang menjadi tempat perlindungan.

### Contoh 4: Dinding Sama Tinggi
```javascript
const heights4 = [4, 4, 4, 4];
console.log(findStormShelters(heights4));
// Output: 1
```

**Penjelasan**: 
Hanya dinding paling kanan yang menjadi tempat perlindungan (karena tidak ada dinding yang lebih tinggi di sebelah kanannya).

### Contoh 5: Array Kosong
```javascript
const heights5 = [];
console.log(findStormShelters(heights5));
// Output: 0
```

**Penjelasan**: 
Tidak ada dinding untuk diperiksa, sehingga tidak ada tempat perlindungan.

## 🔍 Visualisasi Proses

Untuk array `[3, 5, 2, 7, 1]`:

```
Indeks:  0  1  2  3  4
Tinggi: [3, 5, 2, 7, 1]
         ↑     ↑
      Shelter Shelter

Proses dari kanan ke kiri:
1. i=4: height=1, maxHeight=0 → 1 > 0 ✅ → shelterCount=1, maxHeight=1
2. i=3: height=7, maxHeight=1 → 7 > 1 ✅ → shelterCount=2, maxHeight=7
3. i=2: height=2, maxHeight=7 → 2 < 7 ❌
4. i=1: height=5, maxHeight=7 → 5 < 7 ❌
5. i=0: height=3, maxHeight=7 → 3 < 7 ❌

Hasil: 2 tempat perlindungan
```

## ⚡ Kompleksitas

- **Time Complexity**: O(n) - di mana n adalah jumlah elemen dalam array
- **Space Complexity**: O(1) - hanya menggunakan variabel tambahan yang konstan

## 🚀 Keunggulan

- ✅ Efisien dengan kompleksitas waktu linear
- ✅ Menggunakan memori yang minimal
- ✅ Algoritma yang mudah dipahami
- ✅ Dapat menangani berbagai kasus edge case
- ✅ Kode yang bersih dan readable

## 📚 Aplikasi Praktis

Fungsi ini dapat digunakan dalam berbagai skenario:
- Menentukan lokasi optimal untuk menara telekomunikasi
- Analisis ketinggian gedung untuk perencanaan kota
- Simulasi perlindungan dalam game strategy
- Optimasi penempatan infrastruktur berdasarkan elevasi terrain
- Menghitung jumlah building yang dapat melihat sunset/sunrise

## 🔧 Tips Penggunaan

1. **Input Validation**: Pastikan input adalah array yang valid
2. **Edge Cases**: Fungsi menangani array kosong dengan baik
3. **Performance**: Cocok untuk array berukuran besar karena O(n)
4. **Readability**: Nama variabel yang jelas memudahkan maintenance

## 🧪 Test Cases

```javascript
// Test berbagai skenario
console.log(findStormShelters([1, 2, 3, 4, 5]));     // 1
console.log(findStormShelters([5, 4, 3, 2, 1]));     // 5
console.log(findStormShelters([3, 3, 3, 3]));        // 1
console.log(findStormShelters([10]));                 // 1
console.log(findStormShelters([]));                   // 0
console.log(findStormShelters([1, 5, 3, 6, 4]));     // 2
```
