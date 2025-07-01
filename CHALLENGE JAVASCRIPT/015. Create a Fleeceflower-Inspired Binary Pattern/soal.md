
# 🌸 Dokumentasi Fungsi `createFleeceflowerPattern`

## Ringkasan

Fungsi `createFleeceflowerPattern` menghasilkan representasi pola **biner berbentuk bunga fleeceflower** secara sederhana. Pola ini ditampilkan menggunakan karakter `1` dan `0` yang disusun secara simetris menyerupai kelopak bunga.

---

## ✨ Fitur

- Pola simetris di tengah
- Nilai biner berselang-seling (`1`, `0`, `1`, ...)
- Pola mengembang dan menyusut menyerupai bentuk bunga
- Setiap baris dirapikan dengan spasi
- Cocok untuk tampilan visual berbasis konsol

---

## 🧾 Deklarasi Fungsi

```javascript
function createFleeceflowerPattern(size)
```

---

## 📥 Parameter

| Parameter | Tipe   | Deskripsi                                                |
|-----------|--------|----------------------------------------------------------|
| `size`    | number | Bilangan **ganjil ≥ 3**. Menentukan jumlah baris pola.  |

> ⚠️ Nilai `size` harus merupakan **bilangan ganjil** dan **minimal 3** agar pola dapat terbentuk dengan benar.

---

## 📤 Nilai Kembali

- Sebuah `string` yang merepresentasikan pola bunga.
- Tiap baris dipisahkan oleh karakter newline (`\n`).
- Setiap baris diposisikan di tengah dengan penambahan spasi.

---

## 🧮 Penjelasan Pola

Jika `size = 5`, hasilnya:

```
  1  
 101 
10101
 101 
  1  
```

### Ciri-ciri:

- Pola bersifat **simetris vertikal dan horizontal**
- **Baris tengah** merupakan baris terlebar
- Karakter biner **berselang-seling** dimulai dari `1`
- Bentuk pola **mengembang** dari atas, mencapai puncak di tengah, lalu **menyusut** ke bawah

---

## 🛠️ Contoh Penggunaan

```javascript
console.log(createFleeceflowerPattern(5));
```

**Output:**
```
  1  
 101 
10101
 101 
  1  
```

---

## 📌 Catatan

- Gunakan perulangan dan penggabungan string untuk membentuk setiap baris.
- Jumlah digit biner di tiap baris mengikuti pola:
  - Dari atas ke tengah: `1, 3, 5, ...`
  - Dari tengah ke bawah: mencerminkan bagian atas secara simetris

---

## 🧑‍💻 Petunjuk Implementasi

Langkah-langkah membangun pola:

1. Lakukan loop dari `0` hingga `size - 1`
2. Hitung lebar baris berdasarkan jarak dari tengah menggunakan `Math.abs(mid - i)`
3. Tambahkan karakter `1` dan `0` secara bergantian sebanyak lebar baris
4. Tambahkan spasi di kiri dan kanan agar pola berada di tengah

---
