# 📦 Dokumentasi Fungsi `combineOfficeSupplies`

## 📝 Deskripsi

Fungsi `combineOfficeSupplies` adalah fungsi JavaScript yang digunakan untuk **menggabungkan dua array** (daftar) barang perlengkapan kantor menjadi satu array baru. Fungsi ini sangat berguna ketika Anda ingin mengkombinasikan inventori barang yang sudah ada dengan barang-barang baru yang baru datang.

## ✨ Fitur Utama

- ✅ Menggabungkan dua array menjadi satu
- ✅ Tidak mengubah array asli (immutable)
- ✅ Menggunakan method `concat()` yang powerful
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
    // Menggabungkan array existingItems dan newItems menggunakan method concat()
    // Method concat() akan membuat array baru yang berisi semua elemen dari kedua array
    // tanpa mengubah array asli
    return existingItems.concat(newItems);
}
```

## 📖 Cara Kerja

1. Fungsi menerima dua parameter: `existingItems` (barang lama) dan `newItems` (barang baru)
2. Menggunakan **method `concat()`** untuk menggabungkan kedua array
3. Method `concat()` membuat array baru tanpa mengubah array asli
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

### Contoh 4: Membuktikan Array Asli Tidak Berubah

```javascript
const stokAwal = ['Penggaris', 'Pensil'];
const stokTambahan = ['Spidol', 'Penghapus'];

const stokGabungan = combineOfficeSupplies(stokAwal, stokTambahan);

console.log('Stok Awal:', stokAwal);
console.log('Stok Tambahan:', stokTambahan);
console.log('Stok Gabungan:', stokGabungan);
```

**Output:**
```javascript
Stok Awal: ['Penggaris', 'Pensil']
Stok Tambahan: ['Spidol', 'Penghapus']
Stok Gabungan: ['Penggaris', 'Pensil', 'Spidol', 'Penghapus']
```

## ⚠️ Catatan Penting

- Fungsi ini **tidak mengubah** array asli (`existingItems` dan `newItems` tetap sama)
- Jika ada item yang sama di kedua array, item tersebut akan **muncul dua kali** dalam hasil
- Urutan elemen dalam hasil adalah: semua elemen dari `existingItems` diikuti semua elemen dari `newItems`
- Method `concat()` dapat menerima lebih dari satu parameter jika dipanggil langsung

## 🎓 Untuk Pemula

**Apa itu Method `concat()`?**

`concat()` adalah method bawaan JavaScript yang digunakan untuk menggabungkan dua atau lebih array. Nama "concat" berasal dari kata "concatenate" yang artinya "menggabungkan" atau "menyambung".

**Keunggulan `concat()`:**
- ✅ Tidak mengubah array asli (immutable)
- ✅ Mengembalikan array baru
- ✅ Dapat menggabungkan lebih dari 2 array sekaligus
- ✅ Sintaks yang mudah dibaca

**Contoh sederhana:**
```javascript
const array1 = [1, 2, 3];
const array2 = [4, 5, 6];
const gabungan = array1.concat(array2);

console.log(gabungan); // [1, 2, 3, 4, 5, 6]
console.log(array1);   // [1, 2, 3] (tidak berubah)
```

**Menggabungkan lebih dari 2 array:**
```javascript
const array1 = ['A', 'B'];
const array2 = ['C', 'D'];
const array3 = ['E', 'F'];

const hasil = array1.concat(array2, array3);
console.log(hasil); // ['A', 'B', 'C', 'D', 'E', 'F']
```

## 🔍 Perbandingan dengan Method Lain

| Method | Mengubah Array Asli? | Kecepatan | Kasus Penggunaan |
|--------|---------------------|-----------|------------------|
| `concat()` | ❌ Tidak | Sedang | Menggabungkan array tanpa mengubah aslinya |
| `push()` | ✅ Ya | Cepat | Menambah elemen ke akhir array asli |
| Spread `[...]` | ❌ Tidak | Cepat | Sintaks modern untuk menggabungkan array |

## 📚 Referensi

- [MDN Web Docs - Array.concat()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/concat)
- [MDN Web Docs - Arrays](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array)
