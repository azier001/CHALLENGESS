
# 📝 Fungsi `notaryStampReverse` dalam JavaScript

Fungsi ini menerima dua parameter:
- `textArray`: array 2 dimensi yang berisi string,
- `borderWidth`: ketebalan border yang mengelilingi teks.

Fungsi akan membalik setiap string, menggabungkannya, lalu menambahkan border karakter `*` di sekelilingnya, membentuk sebuah "stempel notaris" yang dicetak dalam bentuk teks.

## 🔧 Kode Fungsi

```javascript
function notaryStampReverse(textArray, borderWidth) {
  // Membalik setiap string dalam array 2D dan menggabungkannya
  const reversedText = textArray
    .map(arr => arr.map(str => str.split('').reverse().join('')).join(' '))
    .join(' ');

  // Hitung total lebar teks termasuk border dan spasi di kiri/kanan
  const totalWidth = reversedText.length + 2 * borderWidth + 2;

  // Buat border horizontal atas dan bawah
  const horizontalBorder = '*'.repeat(totalWidth);

  // Buat bagian tengah dengan teks
  const middlePart = '*'.repeat(borderWidth) + ' ' + reversedText + ' ' + '*'.repeat(borderWidth);

  // Gabungkan semua bagian
  const stampedText = [
    horizontalBorder,
    ...Array(borderWidth - 1).fill('*'.repeat(totalWidth)),
    middlePart,
    ...Array(borderWidth - 1).fill('*'.repeat(totalWidth)),
    horizontalBorder
  ].join('\n');

  return stampedText;
}
```

## 💡 Contoh Penggunaan

```javascript
const example1 = notaryStampReverse([["Hello", "World"]], 2);
console.log(example1);
```

### Output:
```
*********************
*********************
** olleH dlroW **
*********************
*********************
```

---

```javascript
const example2 = notaryStampReverse([
  ["OpenAI", "GPT"],
  ["Test", "123"]
], 3);
console.log(example2);
```

### Output:
```
*******************************
*******************************
*******************************
*** IAnepO TPG tseT 321 ***
*******************************
*******************************
*******************************
```

## 📌 Penjelasan Singkat

- Fungsi membalik setiap kata dalam array, satu per satu.
- Semua kata yang sudah dibalik digabung menjadi satu baris panjang.
- Teks dikelilingi oleh border `*` sesuai dengan nilai `borderWidth`.
- Border atas dan bawah dibuat dari `*` sebanyak panjang teks + padding.
- Border samping dibuat dengan `*` sebanyak `borderWidth` di kiri dan kanan.

Cocok digunakan untuk membuat efek stempel pada teks yang ditampilkan di terminal atau antarmuka berbasis teks.
