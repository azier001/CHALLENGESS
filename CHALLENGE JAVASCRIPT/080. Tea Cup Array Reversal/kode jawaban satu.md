# 🍵 Dokumentasi Fungsi `reverseTeaCupArray`

## 📋 Deskripsi Fungsi

Fungsi `reverseTeaCupArray` adalah sebuah fungsi JavaScript yang digunakan untuk membalik urutan elemen dalam array cangkir teh tanpa mengubah array asli. Fungsi ini sangat berguna ketika Anda ingin menampilkan daftar cangkir teh dalam urutan terbalik, misalnya dari yang terakhir ditambahkan hingga yang pertama.

## 🔧 Sintaks

```javascript
reverseTeaCupArray(teaCups)
```

## 📝 Parameter

| Parameter | Tipe | Wajib | Deskripsi |
|-----------|------|-------|-----------|
| `teaCups` | Array | ✅ Ya | Array yang berisi elemen-elemen cangkir teh yang akan dibalik urutannya |

### Penjelasan Parameter:
- **`teaCups`**: Parameter ini menerima array yang berisi data cangkir teh. Array ini bisa berupa string, objek, angka, atau tipe data lainnya yang merepresentasikan cangkir teh.

## ↩️ Nilai Kembalian

Fungsi ini mengembalikan array baru dengan urutan elemen yang terbalik dari array asli. Array asli tidak akan berubah (immutable).

## 💻 Kode Fungsi

```javascript
function reverseTeaCupArray(teaCups) {
    // Membuat salinan array menggunakan slice() untuk tidak mengubah array asli
    // Kemudian membalik urutan elemen dengan reverse()
    return teaCups.slice().reverse();
}
```

### Penjelasan Kode:
1. **`teaCups.slice()`** - Membuat salinan shallow dari array asli
2. **`.reverse()`** - Membalik urutan elemen pada salinan array
3. **`return`** - Mengembalikan array yang sudah dibalik

## 📊 Contoh Penggunaan

### Contoh 1: Array String Sederhana
```javascript
const cangkirTeh = ['Earl Grey', 'Jasmine', 'Green Tea', 'Oolong'];
const hasilTerbalik = reverseTeaCupArray(cangkirTeh);

console.log('Array asli:', cangkirTeh);
console.log('Array terbalik:', hasilTerbalik);
```

**Output:**
```
Array asli: ['Earl Grey', 'Jasmine', 'Green Tea', 'Oolong']
Array terbalik: ['Oolong', 'Green Tea', 'Jasmine', 'Earl Grey']
```

### Contoh 2: Array Objek
```javascript
const koleksiTeh = [
    { nama: 'Earl Grey', suhu: 85 },
    { nama: 'Jasmine', suhu: 80 },
    { nama: 'Green Tea', suhu: 75 }
];

const koleksiTerbalik = reverseTeaCupArray(koleksiTeh);
console.log(koleksiTerbalik);
```

**Output:**
```javascript
[
    { nama: 'Green Tea', suhu: 75 },
    { nama: 'Jasmine', suhu: 80 },
    { nama: 'Earl Grey', suhu: 85 }
]
```

### Contoh 3: Array Kosong
```javascript
const arrayKosong = [];
const hasilKosong = reverseTeaCupArray(arrayKosong);

console.log(hasilKosong); // Output: []
```

## ✅ Keunggulan Fungsi

- **Immutable**: Tidak mengubah array asli
- **Sederhana**: Mudah dipahami dan digunakan
- **Fleksibel**: Dapat bekerja dengan berbagai tipe data dalam array
- **Aman**: Tidak menimbulkan efek samping pada data asli

## ⚠️ Catatan Penting

1. Fungsi ini membuat **shallow copy** dari array, artinya jika array berisi objek, referensi objek akan sama dengan array asli
2. Jika parameter yang diberikan bukan array, fungsi akan menghasilkan error
3. Array asli tetap tidak berubah setelah fungsi dijalankan

## 🔍 Contoh Perbandingan

```javascript
const tehFavorit = ['Chamomile', 'Peppermint', 'Black Tea'];

// Menggunakan fungsi reverseTeaCupArray
const metode1 = reverseTeaCupArray(tehFavorit);

// Metode lain (tidak disarankan karena mengubah array asli)
const metode2 = tehFavorit.reverse();

console.log('Array asli setelah reverseTeaCupArray:', tehFavorit);
// Output: ['Chamomile', 'Peppermint', 'Black Tea'] (tidak berubah)

console.log('Hasil metode1:', metode1);
// Output: ['Black Tea', 'Peppermint', 'Chamomile']
```

## 🏷️ Tag dan Kategori

- **Kategori**: Array Manipulation, Utility Functions
- **Level**: Pemula
- **JavaScript Version**: ES5+
