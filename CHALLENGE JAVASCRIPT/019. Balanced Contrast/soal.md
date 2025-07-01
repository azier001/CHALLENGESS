# ⚖️ Fungsi Balanced Contrast

## 📘 Deskripsi Tantangan

**Tingkat Kesulitan**: Menengah

Buatlah sebuah fungsi bernama `balancedContrast` yang menerima tiga parameter: `arr`, `condition`, dan `str`.

Fungsi ini akan memanipulasi array dan string yang diberikan untuk menciptakan **kontras yang seimbang** berdasarkan kondisi tertentu.

---

## 🔢 Manipulasi Array

* Jika sebuah elemen **lebih besar dari `condition`**, maka posisinya akan **dibalik** dalam array.
* Jika sebuah elemen **kurang dari atau sama dengan `condition`**, maka posisinya akan **tetap**.

> Contoh: jika `arr = [5, 10, 3, 12]` dan `condition = 5`, maka hanya elemen `10` dan `12` yang posisinya akan dibalik.

---

## 🔠 Manipulasi String

1. Balik seluruh string.
2. Untuk setiap karakter dalam string **asli**:

   * Jika karakter berada pada setengah awal alfabet (`'a'` sampai `'m'`), ubah karakter yang bersesuaian dalam string yang telah dibalik menjadi **huruf besar**.
   * Jika karakter berada pada setengah akhir alfabet (`'n'` sampai `'z'`), ubah karakter yang bersesuaian dalam string yang telah dibalik menjadi **huruf kecil**.

> Hal ini menciptakan kontras visual berdasarkan posisi karakter dalam alfabet.

---

## 📥 Parameter

| Nama        | Tipe       | Deskripsi                                                   |
| ----------- | ---------- | ----------------------------------------------------------- |
| `arr`       | `number[]` | Array berisi angka yang akan dimanipulasi                   |
| `condition` | `number`   | Nilai ambang batas untuk menentukan elemen yang dibalik     |
| `str`       | `string`   | String huruf kecil (bisa mengandung spasi) yang akan diolah |

---

## 📤 Nilai Kembalian

Fungsi mengembalikan sebuah **objek** dengan dua properti:

```js
{
  array: [...],   // Array hasil manipulasi
  string: "..."   // String hasil manipulasi
}
```

---

## 🧪 Contoh Penggunaan

Input:

```js
arr = [5, 10, 3, 12]
condition = 5
str = "hello world"
```

Output yang Diharapkan:

```js
{
  array: [5, 12, 3, 10],
  string: "dLROw oLLEH"
}
```

---

## 🧠 Tips

* Kamu dapat menggunakan method array seperti `.filter()`, `.map()`, dan `.reverse()`.
* Untuk string, pertimbangkan menggunakan `.split('')`, `.toUpperCase()`, `.toLowerCase()`.
* Perhatikan kesesuaian posisi karakter antara string asli dan string yang dibalik.

> 🧩 Tantangan ini sangat cocok untuk melatih kemampuan dalam **transformasi array**, **logika string**, dan **pemetaan berdasarkan posisi**.

---


