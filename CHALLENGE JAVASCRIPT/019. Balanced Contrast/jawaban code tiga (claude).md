# 🔄 Fungsi balancedContrast

## 📘 Deskripsi Fungsi

Fungsi `balancedContrast` melakukan dua operasi utama:

1. 🔢 Manipulasi Array:

   * Mengambil elemen yang lebih besar dari `condition`, lalu membalik urutan elemen tersebut dan menggantikannya di posisi semula.

2. 🔠 Manipulasi String:

   * Membalik string
   * Memodifikasi karakter berdasarkan posisi karakter asli:

     * `'a'` - `'m'` → jadikan huruf besar (uppercase)
     * `'n'` - `'z'` → jadikan huruf kecil (lowercase)
     * Spasi dan karakter lain tetap seperti aslinya

---

## 🧮 Parameter

| Nama Parameter | Tipe       | Deskripsi                                                  |
| -------------- | ---------- | ---------------------------------------------------------- |
| `arr`          | `number[]` | Array angka yang akan dimanipulasi                         |
| `condition`    | `number`   | Nilai pembanding untuk menentukan elemen yang akan dibalik |
| `str`          | `string`   | String yang akan dibalik dan dimodifikasi                  |

---

## ⚙️ Proses Kerja

### 🔁 Manipulasi Array

* Simpan elemen yang lebih besar dari `condition`
* Simpan indeks dari elemen-elemen tersebut
* Balik urutan elemen yang disimpan
* Ganti elemen pada indeks-asal dengan elemen yang sudah dibalik

### 🔡 Manipulasi String

* String dibalik terlebih dahulu → `reversedStr`
* Untuk setiap karakter:

  * Jika karakter asli `'a'`-`'m'`, ubah karakter hasil balik menjadi uppercase
  * Jika karakter asli `'n'`-`'z'`, ubah karakter hasil balik menjadi lowercase
  * Spasi dan simbol tetap seperti semula

📝 Tabel transformasi karakter:

| Karakter Asli | Karakter Balik | Hasil Akhir |
| ------------- | -------------- | ----------- |
| `'a'` - `'m'` | `x`            | `X`         |
| `'n'` - `'z'` | `X`            | `x`         |
| Spasi/simbol  | `?`            | `?`         |

---

## 🧪 Contoh Penggunaan

```js
balancedContrast([2, 10, 3, 12], 5, "hello world")
```

💡 Penjelasan:

* Array:

  * Elemen > 5 → `10`, `12`
  * Dibalik → `[12, 10]`
  * Disisipkan ke indeks asal → indeks 1 dan 3
  * Hasil: `[2, 12, 3, 10]`

* String:

  * Dibalik: `dlrow olleh`
  * Transformasi huruf sesuai aturan

📦 Output:

```js
{
  array: [2, 12, 3, 10],
  string: "dLROw oLLEH"
}
```

---

## 💻 Kode Lengkap

```js
function balancedContrast(arr, condition, str) {
  // Manipulasi array
  const manipulatedArray = [...arr];
  const elementsToReverse = [];
  const indicesToReverse = [];

  // Find elements greater than condition and their indices
  for (let i = 0; i < manipulatedArray.length; i++) {
    if (manipulatedArray[i] > condition) {
      elementsToReverse.push(manipulatedArray[i]);
      indicesToReverse.push(i);
    }
  }

  // Reverse the elements and place them back
  elementsToReverse.reverse();
  for (let i = 0; i < indicesToReverse.length; i++) {
    manipulatedArray[indicesToReverse[i]] = elementsToReverse[i];
  }

  // Manipulasi string
  const reversedStr = str.split('').reverse().join('');
  let manipulatedString = '';

  for (let i = 0; i < str.length; i++) {
    const originalChar = str[i];
    const reversedChar = reversedStr[i];

    if (originalChar === ' ') {
      manipulatedString += reversedChar;
    } else if (originalChar >= 'a' && originalChar <= 'm') {
      manipulatedString += reversedChar.toUpperCase();
    } else if (originalChar >= 'n' && originalChar <= 'z') {
      manipulatedString += reversedChar.toLowerCase();
    } else {
      manipulatedString += reversedChar;
    }
  }

  return {
    array: manipulatedArray,
    string: manipulatedString
  };
}
```

---

## 🧠 Tips Tambahan

* Gunakan array clone `[...arr]` agar array asli tidak termutasi
* Logika manipulasi string memperhatikan posisi karakter asli
* Berguna untuk aplikasi data transformation berbasis kondisi numerik dan string karakter

---
