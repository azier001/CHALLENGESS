# 🎭 Dokumentasi Fungsi sortBroadwayShows

## 📝 Deskripsi

Fungsi `sortBroadwayShows` adalah sebuah fungsi JavaScript yang digunakan untuk mengurutkan daftar judul pertunjukan Broadway berdasarkan rating-nya secara menurun (dari rating tertinggi ke terendah). Fungsi ini sangat berguna ketika Anda ingin menampilkan pertunjukan Broadway yang paling populer atau berkualitas tinggi di urutan teratas.

## 🔧 Sintaks

```javascript
sortBroadwayShows(showTitles, ratings)
```

## 📋 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `showTitles` | Array<string> | Array berisi daftar judul pertunjukan Broadway |
| `ratings` | Array<number> | Array berisi rating untuk setiap pertunjukan (harus sesuai urutan dengan showTitles) |

### ⚠️ Catatan Penting
- Kedua array harus memiliki panjang yang sama
- Indeks array `ratings` harus sesuai dengan indeks array `showTitles`
- Rating berupa angka (number) untuk proses pengurutan yang benar

## 🔄 Return Value

**Tipe**: `Array<string>`

**Deskripsi**: Array berisi judul pertunjukan yang sudah diurutkan berdasarkan rating dari tertinggi ke terendah.

## 💻 Kode Sumber

```javascript
function sortBroadwayShows(showTitles, ratings) {
    // Langkah 1: Membuat array objek yang berisi judul pertunjukan dan rating
    const showsWithRatings = showTitles.map((title, index) => ({
        title: title,
        rating: ratings[index]
    }));
    
    // Langkah 2: Mengurutkan array berdasarkan rating secara menurun (descending)
    showsWithRatings.sort((a, b) => b.rating - a.rating);
    
    // Langkah 3: Mengambil judul pertunjukan yang sudah diurutkan
    const sortedTitles = showsWithRatings.map(show => show.title);
    
    // Langkah 4: Mengembalikan array judul pertunjukan yang sudah diurutkan
    return sortedTitles;
}
```

## 🎯 Cara Kerja Fungsi

1. **Penggabungan Data**: Fungsi menggabungkan array `showTitles` dan `ratings` menjadi array objek yang berisi pasangan judul dan rating
2. **Pengurutan**: Array objek diurutkan berdasarkan rating secara menurun menggunakan method `sort()`
3. **Ekstraksi**: Judul pertunjukan yang sudah diurutkan diekstrak dari array objek
4. **Return**: Mengembalikan array judul yang sudah diurutkan

## 📊 Contoh Penggunaan

### Input
```javascript
const judul = ["Hamilton", "The Lion King", "Wicked", "Phantom of the Opera"];
const rating = [9.2, 8.5, 8.9, 8.7];

const hasilUrutan = sortBroadwayShows(judul, rating);
console.log(hasilUrutan);
```

### Output
```javascript
["Hamilton", "Wicked", "Phantom of the Opera", "The Lion King"]
```

### 📈 Tabel Hasil Pengurutan

| Urutan | Judul Pertunjukan | Rating | Keterangan |
|--------|------------------|--------|------------|
| 1 | Hamilton | 9.2 | Rating tertinggi |
| 2 | Wicked | 8.9 | Rating kedua tertinggi |
| 3 | Phantom of the Opera | 8.7 | Rating ketiga tertinggi |
| 4 | The Lion King | 8.5 | Rating terendah |

## 🧪 Contoh Penggunaan Lainnya

### Contoh 1: Pertunjukan dengan Rating Sama
```javascript
const shows = ["Show A", "Show B", "Show C"];
const ratings = [8.0, 8.0, 7.5];

console.log(sortBroadwayShows(shows, ratings));
// Output: ["Show A", "Show B", "Show C"]
// Catatan: Urutan pertunjukan dengan rating sama tetap sesuai urutan asli
```

### Contoh 2: Banyak Pertunjukan
```javascript
const broadwayShows = [
    "Chicago", 
    "The Book of Mormon", 
    "Dear Evan Hansen", 
    "Come From Away", 
    "Aladdin"
];

const showRatings = [8.1, 9.0, 8.8, 8.6, 7.9];

console.log(sortBroadwayShows(broadwayShows, showRatings));
// Output: ["The Book of Mormon", "Dear Evan Hansen", "Come From Away", "Chicago", "Aladdin"]
```

## ⚡ Tips dan Best Practices

- **Validasi Input**: Pastikan kedua array memiliki panjang yang sama sebelum memanggil fungsi
- **Tipe Data**: Pastikan rating berupa angka (number) agar pengurutan berjalan dengan benar
- **Performance**: Fungsi ini memiliki kompleksitas waktu O(n log n) karena menggunakan algoritma sorting

## 🐛 Potensi Error

- Jika panjang array tidak sama, beberapa pertunjukan mungkin tidak memiliki rating (undefined)
- Jika rating bukan angka, hasil pengurutan mungkin tidak sesuai ekspektasi

---
*Dokumentasi ini dibuat untuk membantu pemula memahami cara kerja fungsi sortBroadwayShows* 🎪
