
# 🔁 Reverse and Concatenate Strings in JavaScript

Fungsi ini digunakan untuk membalik dua string, lalu menggabungkannya, dan mengembalikan hasilnya dalam format teks yang mudah dibaca.

## 🧠 Source Code

```javascript
// Fungsi untuk membalik dan menggabungkan dua string
function reverseAndConcatenate(str1, str2) {
  // Membalik string pertama
  const string1 = Array.from(str1).reverse().join('');
  
  // Membalik string kedua
  const string2 = Array.from(str2).reverse().join('');
  
  // Mengembalikan hasil dalam format string yang jelas
  return `The reversed and concatenated string is: ${string1}${string2}`;
}

// Contoh penggunaan fungsi
const hasil1 = reverseAndConcatenate('abc', 'def');
console.log(hasil1); // Output: The reversed and concatenated string is: cbafed
```

## 📌 Penjelasan Kode

- `Array.from(str)`  
  Mengubah string menjadi array karakter individual.
  
- `reverse()`  
  Membalik urutan karakter dalam array.
  
- `join('')`  
  Menggabungkan kembali karakter menjadi string.

- Template literal  
  Digunakan untuk menyusun output agar lebih mudah dibaca.

## 🧪 Contoh Output

```
The reversed and concatenated string is: cbafed
```

## 📘 Catatan

Fungsi ini sangat berguna untuk kebutuhan manipulasi string, seperti:
- Proses validasi sederhana
- Teka-teki string
- Menyusun ulang data string dengan pola tertentu

---

✍️ Dibuat untuk latihan manipulasi string dengan JavaScript.
