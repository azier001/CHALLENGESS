
# Fungsi JavaScript: `reverseAndConcatenate`

Fungsi ini dibuat untuk **membalik** dua buah string dan **menggabungkannya** menjadi satu. Fungsi ini cocok untuk pemula yang ingin memahami cara kerja manipulasi string di JavaScript.

---

## 🧠 Penjelasan Fungsi

```javascript
function reverseAndConcatenate(str1, str2) {
  const reversed1 = str1.split('').reverse().join('');
  const reversed2 = str2.split('').reverse().join('');
  const concatenated = reversed1 + reversed2;
  return `The reversed and concatenated string is: ${concatenated}`;
}
```

### Langkah-langkahnya:

1. **`str1.split('').reverse().join('')`**
   - `split('')`: Memecah string menjadi array karakter.
   - `reverse()`: Membalik urutan array.
   - `join('')`: Menggabungkan kembali array menjadi string.

2. Hal yang sama dilakukan pada `str2`.

3. Hasil dari keduanya digabung (`reversed1 + reversed2`).

4. Fungsi mengembalikan string hasil gabungan dengan teks penjelas.

---

## 🧪 Contoh Penggunaan

```javascript
console.log(reverseAndConcatenate("halo", "dunia"));
// Output: The reversed and concatenated string is: olahnaiud
```

> Fungsi ini sangat membantu untuk latihan logika dan manipulasi string dasar dalam JavaScript.

---

## 📌 Tips

- Cobalah dengan string yang berbeda.
- Bisa dikembangkan untuk membalik lebih dari dua string.

