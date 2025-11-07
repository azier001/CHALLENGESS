# 🥕 Panen Kebun Belakang

## 🌿 Gambaran Tantangan

**Tingkat Kesulitan:** Easy
**Tujuan:** Menggabungkan dua keranjang sayuran menjadi satu daftar hasil panen.

---

## 🧺 Deskripsi Tugas

Buat sebuah function bernama **`harvestVegetables`** yang menerima dua parameter:

* **`carrotBasket`** *(array)*: Array berisi string yang merepresentasikan wortel yang dipanen dari keranjang wortel.
* **`tomatoBasket`** *(array)*: Array berisi string yang merepresentasikan tomat yang dipanen dari keranjang tomat.

Function ini harus menggabungkan sayuran dari kedua keranjang menjadi satu array yang mewakili total hasil panen.

---

## 🧩 Persyaratan Function

### ✅ Parameter

* `carrotBasket`: Array of strings (contoh: `["carrot1", "carrot2"]`)
* `tomatoBasket`: Array of strings (contoh: `["tomato1", "tomato2"]`)

### 🎯 Nilai Kembalian

* Mengembalikan **array of strings** yang berisi semua sayuran hasil panen dari kedua keranjang.
* Urutannya harus:

  1. Semua **carrot** terlebih dahulu (dengan urutan asli)
  2. Diikuti oleh semua **tomato** (dengan urutan asli)

---


## 🌱 Ringkasan

* Menggabungkan dua array menjadi satu daftar hasil panen.
* Mempertahankan urutan asli dari keranjang wortel dan tomat.
* Solusi sederhana dan efisien menggunakan array spread syntax (`...`).

> 🍅 Tip: Kamu juga bisa menggunakan `concat()` untuk mendapatkan hasil yang sama!
