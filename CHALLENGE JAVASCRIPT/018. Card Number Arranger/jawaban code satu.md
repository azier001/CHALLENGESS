# 🃏 Dokumentasi Fungsi arrangeCardNumbers

## 📌 Deskripsi

Fungsi `arrangeCardNumbers` digunakan untuk menyusun ulang angka-angka pada kartu. Angka genap akan disortir secara **menaik** (dari kecil ke besar), sedangkan angka ganjil akan disortir secara **menurun** (dari besar ke kecil). Hasil akhirnya adalah gabungan dari angka genap yang sudah diurutkan dan diikuti oleh angka ganjil yang sudah diurutkan.

Fungsi ini berguna sebagai latihan pemula dalam:

* Menyaring elemen array
* Menggunakan metode `.filter()` dan `.sort()`
* Menggabungkan array

---

## 🔧 Deklarasi Fungsi

```javascript
function arrangeCardNumbers(numbers)
```

---

## 🧩 Kode Lengkap

```javascript
function arrangeCardNumbers(numbers) {
  let result = [];

  const even = numbers.filter((n) => n % 2 === 0).sort((a, b) => a - b);

  const odd = numbers.filter((n) => n % 2 !== 0).sort((a, b) => b - a);

  result = [...even, ...odd];

  return result;
}
```

---

## 🧾 Parameter

| Parameter | Tipe  | Deskripsi                                  |
| --------- | ----- | ------------------------------------------ |
| numbers   | Array | Array yang berisi kumpulan angka (integer) |

---

## 🔄 Cara Kerja

1. **Menyaring angka genap:** Semua angka genap dipisahkan dan diurutkan dari kecil ke besar.
2. **Menyaring angka ganjil:** Semua angka ganjil dipisahkan dan diurutkan dari besar ke kecil.
3. **Menggabungkan hasil:** Angka genap diletakkan di depan, diikuti angka ganjil.

---

## 🔢 Contoh Perilaku Karakter

Misal kita punya input:

```javascript
[3, 8, 1, 6, 7, 4, 5]
```

Langkah-langkahnya:

* Angka genap: `[8, 6, 4]` → disortir menjadi `[4, 6, 8]`
* Angka ganjil: `[3, 1, 7, 5]` → disortir menjadi `[7, 5, 3, 1]`

Gabungan akhir:

```javascript
[4, 6, 8, 7, 5, 3, 1]
```

---

## 💡 Contoh Penggunaan

```javascript
console.log(arrangeCardNumbers([10, 3, 5, 2, 7, 4]));
```

### ✅ Output

```
[2, 4, 10, 7, 5, 3]
```

---

## 🧪 Contoh Tambahan

| Input                | Output               |
| -------------------- | -------------------- |
| `[1, 2, 3, 4, 5, 6]` | `[2, 4, 6, 5, 3, 1]` |
| `[7, 9, 8, 2]`       | `[2, 8, 9, 7]`       |
| `[11, 14, 13, 12]`   | `[12, 14, 13, 11]`   |

---

## 📎 Catatan

* Cocok untuk latihan logika pemula menggunakan filter dan sort.
* Tidak mengubah data asli, hanya membuat array baru sebagai hasil.
* Tidak ada validasi input—pastikan `numbers` adalah array angka.

---

Selamat belajar sorting dan manipulasi array! 🚀
