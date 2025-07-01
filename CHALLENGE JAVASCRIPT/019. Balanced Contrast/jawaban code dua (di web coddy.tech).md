# 🔄 Fungsi balancedContrast

## 📘 Deskripsi Fungsi

Fungsi `balancedContrast` melakukan dua operasi:

1. 🔢 Manipulasi array:

   * Jika elemen array lebih besar dari nilai `condition`, maka diganti dengan elemen dari posisi cermin di array (dihitung dari belakang).
2. 🔠 Manipulasi string:

   * String dibalik.
   * Karakter dimodifikasi (uppercase/lowercase) tergantung posisi karakter aslinya:

     * `'a'` - `'m'` → jadikan huruf besar
     * `'n'` - `'z'` → jadikan huruf kecil

---

## 🧮 Parameter

| Nama Parameter | Tipe       | Deskripsi                                 |
| -------------- | ---------- | ----------------------------------------- |
| `arr`          | `number[]` | Array angka yang akan dimanipulasi        |
| `condition`    | `number`   | Nilai pembanding untuk elemen array       |
| `str`          | `string`   | String yang akan dibalik dan dimodifikasi |

---

## ⚙️ Proses Kerja

### Array:

* Iterasi setiap elemen:

  * Jika `element > condition`, ganti dengan elemen dari posisi `arr.length - 1 - index`
  * Jika tidak, biarkan tetap

### String:

* Balik string → `reversedString`
* Untuk setiap karakter dari hasil balik:

  * Ambil karakter asli di posisi yang sama
  * Ubah karakter hasil balik:

    * Huruf `'a'` hingga `'m'` → kapital
    * Huruf `'n'` hingga `'z'` → huruf kecil
    * Lainnya (spasi, simbol) → tidak berubah

---

## 🧪 Contoh Penggunaan

```js
balancedContrast([5, 10, 3, 12], 5, "hello world")
```

💡 Penjelasan:

* Array:

  * Elemen `10` dan `12` > 5
  * Ganti: `10 → arr[1] → 10`, `12 → arr[0] → 5` → posisi dicerminkan
* String:

  * Dibalik: `dlrow olleh`
  * Berdasarkan posisi asli:

    * `'h'` → kapital → `D`
    * `'e'` → kapital → `L`
    * `'l'` → kapital → `R`
    * `'o'` → kecil → `o`
    * dst

📦 Output:

```js
{
  array: [5, 2, 3, 5],
  string: "dLROw oLLEH"
}
```

---

## 💻 Kode Lengkap

```js
function balancedContrast(arr, condition, str) {
  // Manipulate the array
  const manipulatedArray = arr.map((element, index) => {
    if (element > condition) {
      return arr[arr.length - 1 - index];
    }
    return element;
  });

  // Manipulate the string
  const reversedString = str.split('').reverse().join('');
  const manipulatedString = reversedString.split('').map((char, index) => {
    const originalChar = str[index];
    if (originalChar >= 'a' && originalChar <= 'm') {
      return char.toUpperCase();
    } else if (originalChar >= 'n' && originalChar <= 'z') {
      return char.toLowerCase();
    }
    return char;
  }).join('');

  // Combine the manipulated array and string into an object
  const result = {
    array: manipulatedArray,
    string: manipulatedString
  };

  return result;
}
```

---

## 🧠 Tips Tambahan

* Gunakan `.map()` untuk transformasi array dan string.
* Manfaatkan indeks untuk cermin posisi array.
* Gunakan pengurutan karakter `'a'`-`'z'` untuk logika transformasi huruf.

---
