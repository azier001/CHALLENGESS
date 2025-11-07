# 🥕🍅 Fungsi `harvestVegetables`

Fungsi `harvestVegetables` digunakan untuk **menggabungkan dua keranjang sayur** (carrot dan tomato) menjadi satu hasil panen dalam bentuk array. Fungsi ini merupakan versi sederhana dari penggabungan dua array tanpa penanganan tambahan seperti placeholder untuk keranjang kosong.

---

## 🧩 Deskripsi Fungsi

Fungsi ini menerima dua parameter berupa array — `carrotBasket` dan `tomatoBasket`. Keduanya mewakili daftar hasil panen dari dua jenis sayuran: wortel dan tomat. Fungsi kemudian menggabungkannya menjadi satu array baru menggunakan **spread operator (`...`)**.

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

1. Fungsi tidak menggunakan variabel tambahan.
2. Menggunakan **spread operator (`...`)** untuk menggabungkan isi dua array.
3. Mengembalikan hasil penggabungan dalam satu array baru.

---

## 💻 Kode Lengkap

```javascript
function harvestVegetables(carrotBasket, tomatoBasket) {
  // Gabungkan isi kedua keranjang menjadi satu array baru
  return [...carrotBasket, ...tomatoBasket];
}
```

---

## 🧠 Contoh Penggunaan

```javascript
// Contoh 1: Kedua keranjang berisi sayuran
theHarvest = harvestVegetables(['carrot1', 'carrot2'], ['tomato1', 'tomato2']);
console.log(theHarvest);
// Output: ['carrot1', 'carrot2', 'tomato1', 'tomato2']

// Contoh 2: Salah satu keranjang kosong
theHarvest = harvestVegetables([], ['tomatoA']);
console.log(theHarvest);
// Output: ['tomatoA']

// Contoh 3: Keduanya kosong
theHarvest = harvestVegetables([], []);
console.log(theHarvest);
// Output: []
```

---

## 📝 Catatan Tambahan

* Fungsi ini sangat sederhana dan efisien, cocok untuk latihan **penggabungan array dasar** di JavaScript.
* Menggunakan **spread operator (`...`)**, yang merupakan fitur modern JavaScript untuk menyalin dan menggabungkan array dengan mudah.

---

## 🌱 Ringkasan

| Aspek           | Penjelasan                                                 |
| --------------- | ---------------------------------------------------------- |
| Tujuan          | Menggabungkan dua keranjang sayur menjadi satu hasil panen |
| Bahasa          | JavaScript                                                 |
| Konsep Penting  | Array, Spread Operator                                     |
| Level Kesulitan | 🟢 Mudah (Cocok untuk Pemula)                              |
