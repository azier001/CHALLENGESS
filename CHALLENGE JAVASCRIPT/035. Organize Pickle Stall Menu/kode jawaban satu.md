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
  // Menggabungkan nama acar dan harga menjadi array objek
  let pickles = pickleNames.map((name, index) => ({ name, price: prices[index] }));
  
  // Mengurutkan acar berdasarkan harga secara ascending (murah ke mahal)
  pickles.sort((a, b) => a.price - b.price);
  
  // Membuat string menu yang terformat
  let menu = "=== Bashkir Pickle Menu ===\n";
  
  // Menambahkan setiap acar ke dalam menu
  pickles.forEach(pickle => {
    menu += `${pickle.name}: $${pickle.price.toFixed(2)}\n`;
  });
  
  // Menambahkan footer
  menu += "===========================";
  
  return menu;
}
```

## 🔍 Penjelasan Kode Step by Step

### 1. **Menggabungkan Data**
```javascript
let pickles = pickleNames.map((name, index) => ({ name, price: prices[index] }));
```
- Menggunakan `map()` untuk membuat array objek baru dari dua array terpisah
- Setiap objek berisi `name` dan `price` yang sesuai berdasarkan index yang sama
- Menggunakan shorthand property untuk `name` (sama dengan `name: name`)

### 2. **Mengurutkan Berdasarkan Harga**
```javascript
pickles.sort((a, b) => a.price - b.price);
```
- Menggunakan `sort()` dengan callback function untuk membandingkan harga
- `a.price - b.price` menghasilkan pengurutan ascending (dari kecil ke besar)
- Jika hasil negatif, `a` akan ditempatkan sebelum `b`

### 3. **Membuat Header Menu**
```javascript
let menu = "=== Bashkir Pickle Menu ===\n";
```
- Membuat string menu dengan header yang menarik
- `\n` untuk membuat baris baru setelah header

### 4. **Menambahkan Item ke Menu**
```javascript
pickles.forEach(pickle => {
  menu += `${pickle.name}: $${pickle.price.toFixed(2)}\n`;
});
```
- Menggunakan `forEach()` untuk iterasi setiap objek pickle
- Template literal untuk memformat string dengan nama dan harga
- `toFixed(2)` memastikan harga ditampilkan dengan 2 digit desimal

### 5. **Menambahkan Footer**
```javascript
menu += "===========================";
```
- Menambahkan garis penutup untuk tampilan yang rapi
- Tidak ada `\n` di akhir agar tidak ada baris kosong

## 💡 Tips Penggunaan

- Pastikan panjang array `pickleNames` dan `prices` sama untuk menghindari `undefined`
- Harga sebaiknya dalam format number untuk pengurutan yang benar
- Fungsi menggunakan `let` untuk variabel yang akan dimodifikasi
- Gunakan shorthand property (`{ name, price }`) untuk kode yang lebih bersih

## ⚠️ Catatan Penting

- Jika jumlah nama dan harga tidak sama, beberapa item akan memiliki harga `undefined`
- Pastikan semua harga berupa number, bukan string
- Fungsi akan mengurutkan dari harga termurah ke termahal secara otomatis
- Array asli tidak akan berubah karena `map()` membuat copy baru

## 🎨 Variasi Penggunaan

```javascript
// Contoh dengan lebih banyak item
const pickles = ["Kimchi Korea", "Sauerkraut Jerman", "Acar Timun", "Acar Bawang"];
const priceList = [4.50, 3.25, 2.00, 2.75];

const result = organizePickleStall(pickles, priceList);
console.log(result);
```

**Output:**
```
=== Bashkir Pickle Menu ===
Acar Timun: $2.00
Acar Bawang: $2.75
Sauerkraut Jerman: $3.25
Kimchi Korea: $4.50
===========================
```

## 🧪 Contoh Penggunaan Lanjutan

```javascript
// Contoh dengan harga yang sama
const samePricePickles = ["Acar A", "Acar B", "Acar C"];
const samePrices = [2.50, 2.50, 1.00];

console.log(organizePickleStall(samePricePickles, samePrices));
```

**Output:**
```
=== Bashkir Pickle Menu ===
Acar C: $1.00
Acar A: $2.50
Acar B: $2.50
===========================
```

## 🔧 Modifikasi yang Mungkin

Untuk mengurutkan dari harga tertinggi ke terendah, ubah baris sorting menjadi:
```javascript
pickles.sort((a, b) => b.price - a.price); // Descending order
```
