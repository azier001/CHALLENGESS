
# ✨ JavaScript Function: `notaryStampReverse`


---

## 🔧 Kode 

```javascript
/**
 * Membuat stempel teks dengan border berdasarkan teks yang dibalik.
 * @param {string[][]} textArray - Array 2 dimensi berisi string.
 * @param {number} borderWidth - Ketebalan border bintang.
 * @returns {string} - Teks yang telah dibingkai dengan border.
 */


function notaryStampReverse(textArray, borderWidth) {
  const reverseString = str => str.split('').reverse().join('');

  const reversedText = textArray
    .map(row => row.map(reverseString).join(' '))
    .join(' ');

  const padding = ' ';
  const contentWidth = reversedText.length + padding.length * 2;
  const totalWidth = contentWidth + borderWidth * 2;

  const horizontalBorder = '*'.repeat(totalWidth);
  const middleLine = `${'*'.repeat(borderWidth)}${padding}${reversedText}${padding}${'*'.repeat(borderWidth)}`;

  const verticalBorder = '*'.repeat(totalWidth);
  const sideBorders = Array(borderWidth - 1).fill(verticalBorder);

  const result = [
    horizontalBorder,
    ...sideBorders,
    middleLine,
    ...sideBorders,
    horizontalBorder
  ];

  return result.join('\n');
}
```

---

## 📌 Penjelasan

| Komponen           | Penjelasan |
|--------------------|------------|
| `reverseString`    | Fungsi kecil untuk membalik string. |
| `reversedText`     | Semua teks dalam array dibalik dan digabung. |
| `padding`          | Spasi tambahan di kiri dan kanan teks. |
| `totalWidth`       | Total panjang border atas/bawah. |
| `horizontalBorder` | Baris atas dan bawah dari karakter `*`. |
| `middleLine`       | Teks utama yang dikelilingi oleh border kiri dan kanan. |
| `sideBorders`      | Baris tambahan atas dan bawah di luar middle line. |

---

## 💡 Contoh Penggunaan

```javascript
console.log(notaryStampReverse([["Hello", "World"]], 2));
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

Fungsi ini sangat berguna untuk menampilkan teks dengan gaya visual seperti stempel dalam aplikasi berbasis teks/terminal.
