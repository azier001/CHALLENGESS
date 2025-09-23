# 🛒 Dokumentasi Fungsi `groceryBasket`

## 📋 Deskripsi

Fungsi `groceryBasket` adalah sebuah fungsi JavaScript yang membantu Anda menemukan barang-barang yang tersedia di toko dari daftar barang yang Anda inginkan. Fungsi ini akan mengembalikan array yang berisi hanya barang-barang yang ada di toko dan juga ada dalam daftar keinginan Anda.

Fungsi ini sangat berguna untuk:
- ✅ Memeriksa ketersediaan barang di toko
- 🛍️ Membuat daftar belanja yang realistis
- 📊 Filtering data berdasarkan kriteria tertentu

## 🔧 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `storeItems` | Array | Array yang berisi daftar barang-barang yang tersedia di toko |
| `wantedItems` | Array | Array yang berisi daftar barang-barang yang Anda inginkan |

## 💻 Kode Fungsi

```javascript
function groceryBasket(storeItems, wantedItems) {
  // Memfilter barang yang diinginkan berdasarkan ketersediaan di toko
  // Mengembalikan array berisi barang yang tersedia di toko dan juga diinginkan
  return wantedItems.filter(item => storeItems.includes(item));
}
```

## 📖 Cara Kerja

1. **Input**: Fungsi menerima dua parameter array - `storeItems` dan `wantedItems`
2. **Proses**: Menggunakan method `filter()` untuk memeriksa setiap item dalam `wantedItems`
3. **Validasi**: Untuk setiap item, menggunakan `includes()` untuk mengecek apakah item tersebut ada di `storeItems`
4. **Output**: Mengembalikan array baru yang hanya berisi item yang ada di kedua array

## 🎯 Contoh Penggunaan

### Contoh 1: Belanja Buah-buahan
```javascript
const itemsInStore = ['apel', 'pisang', 'jeruk', 'mangga'];
const myWishlist = ['apel', 'anggur', 'pisang', 'strawberry'];

const availableItems = groceryBasket(itemsInStore, myWishlist);
console.log(availableItems);
```

**Output:**
```javascript
['apel', 'pisang']
```

### Contoh 2: Belanja Alat Tulis
```javascript
const stationeryStore = ['pensil', 'penghapus', 'penggaris', 'buku'];
const neededItems = ['pensil', 'spidol', 'penghapus', 'krayon'];

const canBuy = groceryBasket(stationeryStore, neededItems);
console.log(canBuy);
```

**Output:**
```javascript
['pensil', 'penghapus']
```

### Contoh 3: Tidak Ada Item yang Cocok
```javascript
const availableBooks = ['Harry Potter', 'Lord of the Rings', 'Sherlock Holmes'];
const wantedBooks = ['Twilight', 'Hunger Games', 'Divergent'];

const matchingBooks = groceryBasket(availableBooks, wantedBooks);
console.log(matchingBooks);
```

**Output:**
```javascript
[]
```

## 📊 Tabel Karakter Contoh

| Input `storeItems` | Input `wantedItems` | Output | Penjelasan |
|-------------------|--------------------| -------|------------|
| `['a', 'b', 'c']` | `['a', 'd', 'b']` | `['a', 'b']` | Item 'a' dan 'b' tersedia di toko |
| `['x', 'y', 'z']` | `['m', 'n', 'o']` | `[]` | Tidak ada item yang cocok |
| `['1', '2', '3']` | `['2', '3', '4']` | `['2', '3']` | Item '2' dan '3' tersedia |

## ⚠️ Hal yang Perlu Diperhatikan

- Fungsi ini **case-sensitive**, artinya 'Apel' dan 'apel' dianggap berbeda
- Urutan item dalam output akan mengikuti urutan dalam `wantedItems`
- Jika tidak ada item yang cocok, fungsi akan mengembalikan array kosong `[]`
- Kedua parameter harus berupa array untuk fungsi bekerja dengan benar

## 🔍 Kompleksitas

- **Time Complexity**: O(n × m) dimana n adalah jumlah item dalam `wantedItems` dan m adalah jumlah item dalam `storeItems`
- **Space Complexity**: O(k) dimana k adalah jumlah item yang cocok

## 🚀 Tips Penggunaan

1. **Validasi Input**: Pastikan kedua parameter adalah array
2. **Konsistensi Data**: Gunakan format yang sama untuk semua item (misalnya semua lowercase)
3. **Performance**: Jika `storeItems` sangat besar, pertimbangkan menggunakan Set untuk pencarian yang lebih cepat

---

**📝 Catatan**: Dokumentasi ini dibuat untuk membantu pemula memahami cara kerja fungsi `groceryBasket` dengan mudah.
