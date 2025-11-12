# 📦 Dokumentasi Fungsi `combineOfficeSupplies`

## 📝 Deskripsi

Fungsi `combineOfficeSupplies` adalah fungsi JavaScript yang digunakan untuk **menggabungkan dua array** (daftar) barang perlengkapan kantor menjadi satu array baru. Fungsi ini sangat berguna ketika Anda ingin mengkombinasikan inventori barang yang sudah ada dengan barang-barang baru yang baru datang.

## ✨ Fitur Utama

- ✅ Menggabungkan dua array menjadi satu
- ✅ Tidak mengubah array asli (immutable)
- ✅ Menggunakan spread operator untuk sintaks yang bersih
- ✅ Mudah digunakan dan dipahami

## 📋 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `existingItems` | Array | Daftar barang perlengkapan kantor yang sudah ada sebelumnya |
| `newItems` | Array | Daftar barang perlengkapan kantor yang baru akan ditambahkan |

## 🔄 Return Value

**Tipe:** `Array`

Mengembalikan array baru yang berisi gabungan dari `existingItems` dan `newItems`. Array asli tidak akan berubah (non-destructive).

## 💻 Kode Fungsi

```javascript
function combineOfficeSupplies(existingItems, newItems) {
  // Menggabungkan array existingItems dan newItems menggunakan spread operator (...)
  // Spread operator akan "membuka" kedua array dan menggabungkannya menjadi satu array baru
  return [...existingItems, ...newItems];
}
```

## 📖 Cara Kerja

1. Fungsi menerima dua parameter: `existingItems` (barang lama) dan `newItems` (barang baru)
2. Menggunakan **spread operator** (`...`) untuk "menyebarkan" elemen-elemen dari kedua array
3. Menggabungkan kedua array menjadi satu array baru
4. Mengembalikan array hasil gabungan

## 🎯 Contoh Penggunaan

### Contoh 1: Menggabungkan Alat Tulis

```javascript
const barangLama = ['Pensil', 'Penghapus', 'Penggaris'];
const barangBaru = ['Spidol', 'Stabilo', 'Correction Tape'];

const semuaBarang = combineOfficeSupplies(barangLama, barangBaru);

console.log(semuaBarang);
```

**Output:**
```javascript
['Pensil', 'Penghapus', 'Penggaris', 'Spidol', 'Stabilo', 'Correction Tape']
```

### Contoh 2: Menggabungkan dengan Array Kosong

```javascript
const inventoriSekarang = ['Kertas A4', 'Stapler'];
const barangTambahan = [];

const hasilGabungan = combineOfficeSupplies(inventoriSekarang, barangTambahan);

console.log(hasilGabungan);
```

**Output:**
```javascript
['Kertas A4', 'Stapler']
```

### Contoh 3: Menggabungkan Objek Barang dengan Detail

```javascript
const stokLama = [
  { nama: 'Pulpen Biru', jumlah: 10 },
  { nama: 'Buku Tulis', jumlah: 5 }
];

const stokBaru = [
  { nama: 'Lem Kertas', jumlah: 3 },
  { nama: 'Gunting', jumlah: 2 }
];

const totalStok = combineOfficeSupplies(stokLama, stokBaru);

console.log(totalStok);
```

**Output:**
```javascript
[
  { nama: 'Pulpen Biru', jumlah: 10 },
  { nama: 'Buku Tulis', jumlah: 5 },
  { nama: 'Lem Kertas', jumlah: 3 },
  { nama: 'Gunting', jumlah: 2 }
]
```

## ⚠️ Catatan Penting

- Fungsi ini **tidak mengubah** array asli (`existingItems` dan `newItems` tetap sama)
- Jika ada item yang sama di kedua array, item tersebut akan **muncul dua kali** dalam hasil
- Urutan elemen dalam hasil adalah: semua elemen dari `existingItems` diikuti semua elemen dari `newItems`

## 🎓 Untuk Pemula

**Apa itu Spread Operator (`...`)?**

Spread operator adalah fitur JavaScript yang digunakan untuk "membuka" atau "menyebarkan" elemen-elemen dari array. Bayangkan seperti membuka dus berisi barang-barang dan mengeluarkan semua isinya.

Contoh sederhana:
```javascript
const array1 = [1, 2, 3];
const array2 = [...array1]; // Sama dengan [1, 2, 3]
```

Dalam fungsi `combineOfficeSupplies`, kita menggunakan spread operator untuk mengambil semua item dari dua array dan memasukkannya ke dalam satu array baru!

## 📚 Referensi

- [MDN Web Docs - Spread Operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Spread_syntax)
- [MDN Web Docs - Arrays](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array)
