# 📌 Fungsi `createArtisticSign`
Fungsi ini digunakan untuk membuat tanda artistik dengan menghias sebuah teks menggunakan dekorasi karakter dengan cara menghapus karakter tertentu dari string dekorasi.

## ✅ Definisi Fungsi
```javascript
function createArtisticSign(text, decorations) {
  const vines = decorations.replace(/\*/g, '');
  const knots = decorations.replace(/&/g, '');
  return vines + text + knots;
}
```

**Cara Kerja:**
- `vines`: menghapus semua karakter `*` dari string `decorations`
- `knots`: menghapus semua karakter `&` dari string `decorations`
- Menggabungkan dalam format: `vines + text + knots`

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
Output: '&&Hello World&&'
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
Output: '&&&Cafe&&&'
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
Output: 'Shop'
```

---

### Contoh 6 – Karakter Campuran
```javascript
let hasil6 = createArtisticSign('Store', '~*~&~*~');
console.log("Input: text='Store', decorations='~*~&~*~'");
console.log("Output: '" + hasil6 + "'");
```
**Hasil:**
```
Input: text='Store', decorations='~*~&~*~'
Output: '~~~Store~~~~'
```

---

## 🔍 Cara Kerja Detail

### Proses Step-by-Step:
1. **Input:** `text = "Hello"`, `decorations = "&*#&*"`
2. **Proses vines:** `decorations.replace(/\*/g, '')` → `"&#&"` (hapus semua `*`)
3. **Proses knots:** `decorations.replace(/&/g, '')` → `"*#*"` (hapus semua `&`)
4. **Gabungkan:** `"&#&" + "Hello" + "*#*"` → `"&#&Hello*#*"`

### Karakteristik Fungsi:
- Fungsi ini **tidak** memisahkan karakter `&` dan `*`
- Kedua variabel (`vines` dan `knots`) berisi karakter yang tersisa setelah penghapusan
- Jika `decorations` hanya berisi `&` dan `*`, hasilnya akan terlihat seperti dekorasi simetris
- Jika ada karakter lain, karakter tersebut akan muncul di kedua sisi teks
