# 🐴 Dokumentasi Fungsi `arrangePonies`

## 📋 Deskripsi

Fungsi `arrangePonies` adalah sebuah fungsi JavaScript yang digunakan untuk **menggabungkan dua array kuda poni** menjadi satu array baru. Fungsi ini mengambil array kuda poni yang sudah ada, lalu menambahkan kuda poni baru di bagian akhir array tersebut.

Fungsi ini menggunakan **spread operator** (`...`) untuk membuat array baru tanpa mengubah array asli, sehingga aman dan tidak akan merusak data yang sudah ada.

---

## 🔧 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `initialPonies` | Array | Array yang berisi kuda poni awal (bisa berupa string, object, atau tipe data lainnya) |
| `poniesToAdd` | Array | Array yang berisi kuda poni yang ingin ditambahkan ke array awal |

---

## 📤 Return Value

**Tipe:** `Array`

Fungsi ini mengembalikan array baru yang berisi gabungan dari `initialPonies` dan `poniesToAdd`. Array yang dikembalikan adalah array baru, bukan referensi ke array asli.

---

## 💻 Kode Fungsi

```javascript
function arrangePonies(initialPonies, poniesToAdd) {
  // Menggabungkan array initialPonies dan poniesToAdd menggunakan spread operator
  // Hasilnya adalah array baru yang berisi semua elemen dari kedua array
  return [...initialPonies, ...poniesToAdd];
}
```

---

## 📝 Penjelasan Cara Kerja

1. **Spread Operator (`...`)**: Operator ini "membuka" isi dari sebuah array dan menyebarkan elemennya
2. **Array Baru**: Tanda kurung siku `[]` membuat array baru
3. **Penggabungan**: Elemen dari `initialPonies` dimasukkan terlebih dahulu, kemudian diikuti oleh elemen dari `poniesToAdd`
4. **Immutability**: Array asli (`initialPonies` dan `poniesToAdd`) tidak akan berubah

---

## 🎯 Contoh Penggunaan

### Contoh 1: Menggabungkan Array String

```javascript
const kponiAwal = ['Rainbow Dash', 'Twilight Sparkle'];
const kponiBaru = ['Pinkie Pie', 'Fluttershy'];

const semuaKponi = arrangePonies(kponiAwal, kponiBaru);

console.log(semuaKponi);
```

**Output:**
```javascript
['Rainbow Dash', 'Twilight Sparkle', 'Pinkie Pie', 'Fluttershy']
```

---

### Contoh 2: Menggabungkan Array Angka

```javascript
const kelompok1 = [1, 2, 3];
const kelompok2 = [4, 5, 6];

const hasilGabungan = arrangePonies(kelompok1, kelompok2);

console.log(hasilGabungan);
```

**Output:**
```javascript
[1, 2, 3, 4, 5, 6]
```

---

### Contoh 3: Menggabungkan Array Object

```javascript
const poniAwal = [
  { nama: 'Rainbow Dash', warna: 'Biru' },
  { nama: 'Twilight Sparkle', warna: 'Ungu' }
];

const poniBaru = [
  { nama: 'Applejack', warna: 'Orange' },
  { nama: 'Rarity', warna: 'Putih' }
];

const semuaPoni = arrangePonies(poniAwal, poniBaru);

console.log(semuaPoni);
```

**Output:**
```javascript
[
  { nama: 'Rainbow Dash', warna: 'Biru' },
  { nama: 'Twilight Sparkle', warna: 'Ungu' },
  { nama: 'Applejack', warna: 'Orange' },
  { nama: 'Rarity', warna: 'Putih' }
]
```

---

## 🎨 Tabel Karakter Poni (Contoh Data)

Berikut adalah contoh karakter poni yang bisa digunakan dengan fungsi ini:

| Nama | Warna Utama | Elemen | Tipe |
|------|-------------|--------|------|
| Rainbow Dash | Biru | Loyalitas | Pegasus |
| Twilight Sparkle | Ungu | Sihir | Unicorn |
| Pinkie Pie | Pink | Tertawa | Earth Pony |
| Fluttershy | Kuning | Kebaikan | Pegasus |
| Applejack | Orange | Kejujuran | Earth Pony |
| Rarity | Putih | Kemurahan | Unicorn |

---

## ⚠️ Catatan Penting

- Fungsi ini **tidak mengubah** array asli (immutable)
- Urutan elemen tetap dipertahankan (elemen dari `initialPonies` muncul terlebih dahulu)
- Bisa digunakan untuk array dengan tipe data apa saja (string, number, object, dll)
- Jika salah satu parameter adalah array kosong `[]`, hasilnya akan tetap berupa array yang berisi elemen dari parameter yang lain

---

## 🚀 Keuntungan Menggunakan Spread Operator

1. **Mudah dibaca**: Sintaks yang simple dan clean
2. **Aman**: Tidak mengubah data asli
3. **Fleksibel**: Bisa menggabungkan lebih dari 2 array jika diperlukan
4. **Modern**: Menggunakan sintaks ES6 yang merupakan standar JavaScript modern

---

## 📚 Referensi Tambahan

Untuk mempelajari lebih lanjut tentang spread operator dan manipulasi array di JavaScript:
- [MDN Web Docs - Spread Syntax](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Spread_syntax)
- [MDN Web Docs - Array](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array)

---

**Dibuat dengan ❤️ untuk memudahkan pemahaman pemula**
