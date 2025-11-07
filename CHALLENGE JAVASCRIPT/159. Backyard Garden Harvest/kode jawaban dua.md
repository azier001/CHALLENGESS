# 🥕🍅 Fungsi `harvestVegetables`

Fungsi `harvestVegetables` digunakan untuk **menggabungkan dua keranjang sayur** (carrot dan tomato) menjadi satu hasil panen dalam bentuk array. Fungsi ini akan memastikan bahwa jika salah satu keranjang kosong, tetap akan ada elemen kosong (`''`) yang mewakilinya agar hasil tetap konsisten.

---

## 🧩 Deskripsi Fungsi

Fungsi ini menerima dua parameter berupa array — `carrotBasket` dan `tomatoBasket`. Keduanya mewakili daftar hasil panen dari dua jenis sayuran: wortel dan tomat. Fungsi kemudian menggabungkannya dalam satu array baru.

Jika salah satu keranjang kosong, fungsi akan menambahkan **string kosong ('')** sebagai placeholder agar tetap ada posisi untuk keranjang tersebut.

---

## 📥 Parameter

| Nama Parameter | Tipe Data | Deskripsi                                                |
| -------------- | --------- | -------------------------------------------------------- |
| `carrotBasket` | `array`   | Daftar hasil panen wortel (setiap elemen berupa string). |
| `tomatoBasket` | `array`   | Daftar hasil panen tomat (setiap elemen berupa string).  |

---

## 📤 Nilai Kembalian

| Tipe Data | Deskripsi                                                               |
| --------- | ----------------------------------------------------------------------- |
| `array`   | Array baru yang berisi gabungan dari `carrotBasket` dan `tomatoBasket`. |

---

## 💡 Penjelasan Logika

1. Buat array kosong bernama `result` untuk menyimpan hasil akhir.
2. Periksa apakah salah satu keranjang kosong (`carrotBasket` atau `tomatoBasket`). Jika ya, isi dengan string kosong `''` agar tidak ada data yang hilang.
3. Gabungkan kedua array dengan urutan: **carrot terlebih dahulu, kemudian tomato** menggunakan **spread operator (`...`)**.

---

## 💻 Kode Lengkap

```javascript
function harvestVegetables(carrotBasket, tomatoBasket) {
  const result = [];

  // Jika salah satu keranjang kosong, tambahkan elemen kosong sebagai placeholder
  if (carrotBasket.length === 0) carrotBasket = [''];
  if (tomatoBasket.length === 0) tomatoBasket = [''];

  // Gabungkan keduanya sesuai urutan: carrot dulu, lalu tomato
  return [...carrotBasket, ...tomatoBasket];
}
```

---

## 🧠 Contoh Penggunaan

```javascript
// Contoh 1: Kedua keranjang terisi
theHarvest = harvestVegetables(['carrot1', 'carrot2'], ['tomato1', 'tomato2']);
console.log(theHarvest);
// Output: ['carrot1', 'carrot2', 'tomato1', 'tomato2']

// Contoh 2: Salah satu keranjang kosong
theHarvest = harvestVegetables([], ['tomatoA']);
console.log(theHarvest);
// Output: ['', 'tomatoA']

// Contoh 3: Keduanya kosong
theHarvest = harvestVegetables([], []);
console.log(theHarvest);
// Output: ['', '']
```

---

## 📝 Catatan Tambahan

* Fungsi ini sederhana dan cocok untuk latihan **manipulasi array dasar** di JavaScript.
* Konsep yang digunakan di sini:

  * **Spread Operator (`...`)** untuk menggabungkan dua array.
  * **Pemeriksaan kondisi** untuk menghindari array kosong tanpa elemen.

---

## 🌱 Ringkasan

| Aspek           | Penjelasan                                                 |
| --------------- | ---------------------------------------------------------- |
| Tujuan          | Menggabungkan dua keranjang sayur menjadi satu hasil panen |
| Bahasa          | JavaScript                                                 |
| Konsep Penting  | Array, Spread Operator, Kondisi If                         |
| Level Kesulitan | 🟢 Mudah (Cocok untuk Pemula)                              |
