# 🌊 Menghitung Storm Shelters di Desa Pesisir

## 🎯 Gambaran Challenge
**Difficulty:** `Easy`

Di sebuah desa pesisir, dinding-dinding batu kuno berdiri melawan badai yang ganas. Tugas Anda adalah mengidentifikasi jumlah **storm shelters** di antara dinding-dinding ini. Storm shelter adalah dinding yang lebih tinggi dari semua dinding di sebelah kanannya, memberikan perlindungan penting bagi penduduk desa selama cuaca buruk.

## 📋 Deskripsi Problem

Buat function bernama `findStormShelters` yang mengidentifikasi dinding-dinding yang berfungsi sebagai storm shelters dengan cara:
- Melakukan iterasi melalui array dari **kanan ke kiri**
- Melacak tinggi maksimum yang ditemukan sejauh ini
- Menghitung dinding yang melebihi maksimum ini

## 🔧 Spesifikasi Function

### Function Signature
```javascript
function findStormShelters(wallHeights)
```

### Parameters
- **`wallHeights`** *(array)*: Array berisi angka-angka yang merepresentasikan tinggi dinding batu
  - Setiap angka adalah integer positif
  - Merepresentasikan tinggi dinding dari kiri ke kanan

### Return Value
- **Number**: Jumlah storm shelters (dinding yang lebih tinggi dari semua dinding di sebelah kanannya)

## 📊 Contoh-contoh

### Contoh 1
```javascript
findStormShelters([3, 7, 8, 3, 6, 1])
// Returns: 3
```
**Penjelasan:** Storm shelters berada di index 2, 1, dan 0 (tinggi 8, 7, dan 3)

### Contoh 2
```javascript
findStormShelters([5, 4, 3, 2, 1])
// Returns: 5
```
**Penjelasan:** Semua dinding adalah storm shelters karena masing-masing lebih tinggi dari semua dinding di sebelah kanannya

### Contoh 3
```javascript
findStormShelters([1, 2, 3, 4, 5])
// Returns: 1
```
**Penjelasan:** Hanya dinding paling kanan (tinggi 5) yang merupakan storm shelter

## 🧠 Pendekatan Algorithm

1. **Mulai dari dinding paling kanan** dan bergerak ke kiri
2. **Lacak tinggi maksimum** yang ditemukan sejauh ini
3. **Hitung dinding** yang lebih tinggi dari maksimum saat ini
4. **Update maksimum** ketika dinding yang lebih tinggi ditemukan

## 💡 Key Insights

- Dinding paling kanan selalu merupakan storm shelter
- Dinding memenuhi syarat sebagai storm shelter jika lebih tinggi dari semua dinding di sebelah kanannya
- Memproses dari kanan ke kiri memungkinkan pelacakan efisien terhadap tinggi maksimum
- Time complexity: O(n) - single pass melalui array
- Space complexity: O(1) - hanya perlu melacak tinggi maksimum dan count

## 🎨 Representasi Visual

Untuk array `[3, 7, 8, 3, 6, 1]`:

```
Height
  8 |   █
  7 | █ █
  6 | █ █   █
  5 | █ █   █
  4 | █ █   █
  3 | █ █ █ █
  2 | █ █ █ █
  1 | █ █ █ █ █ █
    +-------------
      3 7 8 3 6 1
      ↑ ↑ ↑     
    Storm Shelters
```

Dinding-dinding di posisi 0, 1, dan 2 (tinggi 3, 7, dan 8) adalah storm shelters karena masing-masing lebih tinggi dari semua dinding di sebelah kanannya.
