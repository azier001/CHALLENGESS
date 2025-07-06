# 🥒 Dokumentasi Fungsi `organizePickleStall`

## 📋 Deskripsi Fungsi

Fungsi `organizePickleStall` adalah sebuah fungsi JavaScript yang digunakan untuk mengorganisir dan menampilkan daftar menu acar (pickle) dalam format yang rapi dan terurut berdasarkan harga. Fungsi ini akan menggabungkan nama-nama acar dengan harga-harganya, mengurutkannya dari harga termurah ke termahal, dan menampilkannya dalam format menu yang menarik.

## 🎯 Kegunaan

- Mengorganisir daftar produk acar dengan harga
- Mengurutkan menu berdasarkan harga (murah ke mahal)
- Membuat tampilan menu yang profesional dan mudah dibaca
- Memformat harga dengan 2 desimal untuk konsistensi

## 📝 Parameter

| Parameter | Tipe | Deskripsi | Contoh |
|-----------|------|-----------|---------|
| `pickleNames` | Array of String | Daftar nama-nama acar yang akan ditampilkan | `["Acar Timun", "Acar Wortel", "Acar Kubis"]` |
| `prices` | Array of Number | Daftar harga yang sesuai dengan urutan nama acar | `[2.50, 1.75, 3.00]` |

## 🔄 Return Value

**Tipe:** `String`

**Deskripsi:** Mengembalikan string yang berisi menu acar yang sudah diformat dan diurutkan berdasarkan harga.

## 🚀 Contoh Penggunaan

```javascript
// Contoh 1: Menu acar sederhana
const namaAcar = ["Acar Timun", "Acar Wortel", "Acar Kubis"];
const hargaAcar = [2.50, 1.75, 3.00];

const menu = organizePickleStall(namaAcar, hargaAcar);
console.log(menu);
```

## 📊 Contoh Output

```
=== Bashkir Pickle Menu ===
Acar Wortel: $1.75
Acar Timun: $2.50
Acar Kubis: $3.00
===========================
```

## 🔧 Kode Fungsi Lengkap

```javascript
function organizePickleStall(pickleNames, prices) {
    // Membuat array objek untuk menggabungkan nama dengan harga
    const pickleItems = pickleNames.map((name, index) => ({
        name: name,
        price: prices[index]
    }));
    
    // Mengurutkan berdasarkan harga secara ascending (murah ke mahal)
    pickleItems.sort((a, b) => a.price - b.price);
    
    // Membuat string menu yang terformat
    let menu = "=== Bashkir Pickle Menu ===\n";
    
    // Menambahkan setiap item acar ke dalam menu
    pickleItems.forEach(item => {
        menu += `${item.name}: $${item.price.toFixed(2)}\n`;
    });
    
    // Menambahkan footer
    menu += "===========================";
    
    return menu;
}
```

## 🔍 Penjelasan Kode Step by Step

### 1. **Menggabungkan Data**
```javascript
const pickleItems = pickleNames.map((name, index) => ({
    name: name,
    price: prices[index]
}));
```
- Menggunakan `map()` untuk membuat array objek baru
- Setiap objek berisi `name` dan `price` yang sesuai berdasarkan index

### 2. **Mengurutkan Berdasarkan Harga**
```javascript
pickleItems.sort((a, b) => a.price - b.price);
```
- Menggunakan `sort()` dengan callback function
- Mengurutkan dari harga terendah ke tertinggi (ascending)

### 3. **Membuat Header Menu**
```javascript
let menu = "=== Bashkir Pickle Menu ===\n";
```
- Membuat string menu dengan header yang menarik

### 4. **Menambahkan Item ke Menu**
```javascript
pickleItems.forEach(item => {
    menu += `${item.name}: $${item.price.toFixed(2)}\n`;
});
```
- Menggunakan `forEach()` untuk iterasi setiap item
- `toFixed(2)` untuk memformat harga dengan 2 desimal

### 5. **Menambahkan Footer**
```javascript
menu += "===========================";
```
- Menambahkan garis penutup untuk tampilan yang rapi

## 💡 Tips Penggunaan

- Pastikan panjang array `pickleNames` dan `prices` sama
- Harga sebaiknya dalam format number untuk pengurutan yang benar
- Fungsi ini tidak mengubah array asli, hanya mengurutkan copy-nya

## ⚠️ Catatan Penting

- Jika jumlah nama dan harga tidak sama, akan terjadi error
- Pastikan semua harga berupa number, bukan string
- Fungsi akan mengurutkan dari harga termurah ke termahal secara otomatis

## 🎨 Variasi Penggunaan

```javascript
// Contoh dengan lebih banyak item
const pickles = ["Kimchi", "Sauerkraut", "Pickled Cucumber", "Pickled Onion"];
const priceList = [4.50, 3.25, 2.00, 2.75];

const result = organizePickleStall(pickles, priceList);
console.log(result);
```

**Output:**
```
=== Bashkir Pickle Menu ===
Pickled Cucumber: $2.00
Pickled Onion: $2.75
Sauerkraut: $3.25
Kimchi: $4.50
===========================
```
