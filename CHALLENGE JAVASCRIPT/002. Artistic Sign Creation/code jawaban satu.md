
# 📌 Fungsi `createArtisticSign`

Fungsi ini digunakan untuk membuat tanda artistik dengan menghias sebuah teks menggunakan dekorasi karakter `&` (vine) dan `*` (knot).

## ✅ Definisi Fungsi

```javascript
function createArtisticSign(text, decorations) {
  // Memisahkan karakter dekorasi menjadi vine (&) dan knot (*)
  let vines = ''; // untuk menyimpan karakter '&'
  let knots = ''; // untuk menyimpan karakter '*'

  // Loop melalui setiap karakter dalam string decorations
  for (let i = 0; i < decorations.length; i++) {
    if (decorations[i] === '&') {
      vines += '&'; // tambahkan ke vine decorations
    } else if (decorations[i] === '*') {
      knots += '*'; // tambahkan ke knot decorations
    }
  }

  // Menggabungkan vine + text + knot untuk membuat sign yang indah
  return vines + text + knots;
}
```

---

## 💡 Contoh Penggunaan

### Contoh 1

```javascript
let hasil1 = createArtisticSign('Welcome', '&*&*');
console.log("Input: text='Welcome', decorations='&*&*'");
console.log("Output: '" + hasil1 + "'");
```

**Hasil:**
```
Input: text='Welcome', decorations='&*&*'
Output: '&&Welcome**'
```

---

### Contoh 2

```javascript
let hasil2 = createArtisticSign('Hello World', '&&***');
console.log("Input: text='Hello World', decorations='&&***'");
console.log("Output: '" + hasil2 + "'");
```

**Hasil:**
```
Input: text='Hello World', decorations='&&***'
Output: '&&Hello World***'
```

---

### Contoh 3

```javascript
let hasil3 = createArtisticSign('Beautiful', '*&*&*&');
console.log("Input: text='Beautiful', decorations='*&*&*&'");
console.log("Output: '" + hasil3 + "'");
```

**Hasil:**
```
Input: text='Beautiful', decorations='*&*&*&'
Output: '&&&Beautiful***'
```

---

### Contoh 4 – Hanya Vine

```javascript
let hasil4 = createArtisticSign('Cafe', '&&&');
console.log("Input: text='Cafe', decorations='&&&'");
console.log("Output: '" + hasil4 + "'");
```

**Hasil:**
```
Input: text='Cafe', decorations='&&&'
Output: '&&&Cafe'
```

---

### Contoh 5 – Hanya Knot

```javascript
let hasil5 = createArtisticSign('Shop', '***');
console.log("Input: text='Shop', decorations='***'");
console.log("Output: '" + hasil5 + "'");
```

**Hasil:**
```
Input: text='Shop', decorations='***'
Output: 'Shop***'
```
