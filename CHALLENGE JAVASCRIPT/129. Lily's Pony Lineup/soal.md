# 🦄 Lily's Pony Lineup

## Level Challenge
**Easy** 🟢

---

## 📋 Gambaran Umum

Buat sebuah function bernama `arrangePonies` yang membantu Lily mengatur mainan pony-nya dalam urutan khusus. Lily memiliki sekelompok pony yang sudah berbaris dan ingin menambahkan lebih banyak pony ke akhir barisan.

---

## 🎯 Tujuan

Function ini harus membuat array baru yang menggabungkan kedua kelompok pony, memastikan bahwa pony dari `poniesToAdd` muncul **setelah** pony dari `initialPonies` dalam susunan akhir.

---

## 📝 Function Signature

```javascript
function arrangePonies(initialPonies, poniesToAdd)
```

---

## 🔧 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `initialPonies` | `array` | Array berisi string yang merepresentasikan nama-nama pony yang sudah berbaris |
| `poniesToAdd` | `array` | Array berisi string yang merepresentasikan nama-nama pony yang ingin ditambahkan Lily ke barisan |

---

## 📤 Return Value

**Tipe:** `array`

Array berisi string yang merepresentasikan susunan akhir pony milik Lily, dengan pony dari `poniesToAdd` muncul setelah pony dari `initialPonies`.

---

## ⚙️ Persyaratan

- ✅ Function harus bekerja dengan benar jika salah satu input array kosong
- ✅ Jika ada nama pony yang duplikat antara kedua array, duplikat tersebut harus disertakan dalam array akhir
- ✅ Urutan harus dipertahankan: `initialPonies` terlebih dahulu, kemudian `poniesToAdd`

---

## 💡 Contoh Penggunaan

```javascript
// Contoh 1: Penggunaan dasar
const initial = ['Rainbow', 'Twilight', 'Pinkie'];
const toAdd = ['Fluttershy', 'Rarity'];
arrangePonies(initial, toAdd);
// Output yang diharapkan: ['Rainbow', 'Twilight', 'Pinkie', 'Fluttershy', 'Rarity']

// Contoh 2: Dengan duplikat
const initial = ['Rainbow', 'Twilight'];
const toAdd = ['Rainbow', 'Applejack'];
arrangePonies(initial, toAdd);
// Output yang diharapkan: ['Rainbow', 'Twilight', 'Rainbow', 'Applejack']

// Contoh 3: Array kosong
arrangePonies([], ['Fluttershy']);
// Output yang diharapkan: ['Fluttershy']

arrangePonies(['Rainbow'], []);
// Output yang diharapkan: ['Rainbow']
```

---

## 🎨 Tips

- Pertimbangkan untuk menggunakan array methods untuk menggabungkan array
- Ingat untuk menangani edge cases dengan array kosong
- Duplikat diperbolehkan dan harus dipertahankan

---

**Happy Coding!** 🚀
