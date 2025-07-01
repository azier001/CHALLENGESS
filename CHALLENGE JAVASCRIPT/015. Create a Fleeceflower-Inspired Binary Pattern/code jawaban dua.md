# 🌸 Dokumentasi Fungsi createFleeceflowerPattern

## 📌 Deskripsi

Fungsi `createFleeceflowerPattern` digunakan untuk membuat pola bunga fleece (seperti pola simetris berbentuk berlian) menggunakan angka `1` dan `0` yang disusun secara bergantian. Fungsi ini hanya menerima bilangan ganjil yang lebih besar dari atau sama dengan 3.

---

## 🔧 Deklarasi Fungsi

```javascript
function createFleeceflowerPattern(size)
```

---

## 🧩 Kode Lengkap

```javascript
function createFleeceflowerPattern(size) {
  if (size < 3 || size % 2 === 0) {
    return "Invalid input";
  }

  let pattern = [];
  let mid = Math.floor(size / 2);

  for (let i = 0; i < size; i++) {
    let row = [];
    let rowSize = size - Math.abs(mid - i) * 2;

    // Tambah spasi di awal baris
    for (let j = 0; j < (size - rowSize) / 2; j++) {
      row.push(" ");
    }

    // Tambah angka 1 dan 0 secara bergantian
    for (let j = 0; j < rowSize; j++) {
      row.push(j % 2 === 0 ? "1" : "0");
    }

    // Tambah spasi di akhir baris
    for (let j = 0; j < (size - rowSize) / 2; j++) {
      row.push(" ");
    }

    pattern.push(row.join(""));
  }

  return pattern.join("\n");
}
```

---

## 🧾 Parameter

| Parameter | Tipe   | Deskripsi                                     |
| --------- | ------ | --------------------------------------------- |
| size      | Number | Ukuran pola (harus bilangan ganjil minimal 3) |

---

## 🔄 Cara Kerja

1. Mengecek apakah ukuran valid (ganjil dan ≥ 3).
2. Menentukan titik tengah.
3. Untuk setiap baris:

   * Hitung ukuran baris berdasarkan jaraknya dari tengah.
   * Tambahkan spasi di awal dan akhir untuk membuat pola simetris.
   * Isi baris dengan pola `1` dan `0` secara bergantian.
4. Gabungkan semua baris menjadi satu string yang dipisah dengan baris baru (`\n`).

---

## 📤 Nilai Kembali

* **Tipe:** `String`
* **Deskripsi:** Pola fleeceflower dalam bentuk teks multiline.

---

## 🎯 Contoh Penggunaan

```javascript
console.log(createFleeceflowerPattern(5));
```

### ✅ Output

```
  1  
 101
10101
 101
  1  
```

---

## ⚠️ Validasi Input

Jika masukan tidak valid:

```javascript
console.log(createFleeceflowerPattern(4));
```

### Output:

```
Invalid input
```

---

## 📎 Catatan

* Fungsi ini berguna untuk latihan manipulasi array dan pola simetris.
* Mengajarkan konsep titik tengah dan simetri secara visual.

---

Selamat belajar dan semangat membuat pola! 🌼
