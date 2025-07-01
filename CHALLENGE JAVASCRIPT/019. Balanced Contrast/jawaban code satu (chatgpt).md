# ⚖️ Fungsi balancedContrast

## 📘 Deskripsi Fungsi

Fungsi `balancedContrast` melakukan manipulasi terhadap array dan string untuk menciptakan efek **kontras yang seimbang** berdasarkan kondisi tertentu.

* Elemen array yang **lebih besar** dari `condition` akan dibalik posisinya.
* String akan dibalik, lalu diubah besar/kecil hurufnya berdasarkan karakter pada string asli.

Fungsi ini berguna untuk melatih kemampuan **manipulasi array**, **transformasi string**, dan **pemetaan posisi karakter**.

---

## 🧮 Parameter

| Parameter   | Tipe       | Deskripsi                                             |
| ----------- | ---------- | ----------------------------------------------------- |
| `arr`       | `number[]` | Array angka yang akan dimanipulasi                    |
| `condition` | `number`   | Nilai pembanding untuk menentukan elemen yang dibalik |
| `str`       | `string`   | String berisi huruf kecil dan spasi yang akan diolah  |

---

## 🛠️ Proses Manipulasi

### 🔁 Array

* Ambil semua angka yang lebih besar dari `condition`, lalu balik urutannya.
* Sisipkan kembali angka-angka tersebut ke posisi aslinya dalam array.

### 🔤 String

* Balik seluruh string (`reverse`).
* Untuk setiap karakter dalam string asli:

  * Jika berada antara `'a'` hingga `'m'`, karakter yang sesuai pada string yang dibalik akan menjadi **huruf besar**.
  * Jika berada antara `'n'` hingga `'z'`, karakter yang sesuai pada string yang dibalik akan menjadi **huruf kecil**.
  * Spasi dan karakter lain tetap.

---

## 🔡 Tabel Referensi Huruf

| Asli (`str[i]`) | Rentang | Hasil pada `reversed[i]` |
| --------------- | ------- | ------------------------ |
| `'a'` - `'m'`   | Awal    | Huruf **BESAR**          |
| `'n'` - `'z'`   | Akhir   | Huruf **kecil**          |
| `' '`           | Spasi   | Tetap                    |

---

## 📤 Nilai Kembalian

Objek dengan properti:

```js
{
  array: [...],   // array hasil manipulasi
  string: "..."   // string hasil manipulasi
}
```

---

## 🧪 Contoh Penggunaan

```js
balancedContrast([5, 10, 3, 12], 5, "hello world")
```

**Hasil:**

```js
{
  array: [5, 12, 3, 10],
  string: "dLROw oLLEH"
}
```

---

## 💡 Tips

* Gunakan `.filter()` dan `.reverse()` untuk mengatur urutan angka.
* Gunakan `.split('')`, `.map()`, `.toUpperCase()`, dan `.toLowerCase()` untuk manipulasi string.
* Pastikan posisi karakter antara string asli dan yang dibalik tetap sinkron.

---

## 🧾 Kode Lengkap

```js
function balancedContrast(arr, condition, str) { 
  // Manipulasi array
  const greater = arr.filter(num => num > condition).reverse();
  const resultArray = [];
  let gIndex = 0;

  for (let i = 0; i < arr.length; i++) {
    if (arr[i] > condition) {
      resultArray.push(greater[gIndex++]);
    } else {
      resultArray.push(arr[i]);
    }
  }

  // Manipulasi string
  const reversed = str.split('').reverse();
  const manipulatedStr = reversed.map((char, i) => {
    const originalChar = str[i];
    if (originalChar >= 'a' && originalChar <= 'm') {
      return char.toUpperCase();
    } else if (originalChar >= 'n' && originalChar <= 'z') {
      return char.toLowerCase();
    } else {
      return char;
    }
  }).join('');

  return {
    array: resultArray,
    string: manipulatedStr
  };
}
```

---

## 📎 Catatan

> Cocok untuk melatih logika transformasi data dan pengolahan string dengan pendekatan berbasis posisi karakter.

---
