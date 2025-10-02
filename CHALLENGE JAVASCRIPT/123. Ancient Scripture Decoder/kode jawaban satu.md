# 📜 Dokumentasi Fungsi `decodeScripture`

## 📋 Deskripsi

Fungsi `decodeScripture` adalah sebuah fungsi yang menggabungkan array asli dengan dua elemen terakhir dari array tambahan. Fungsi ini mengambil dua kata/elemen terakhir dari baris tambahan dan menambahkannya ke akhir baris asli, kemudian mengembalikan array gabungan yang baru.

---

## 🔧 Sintaks

```javascript
decodeScripture(originalLine, additionalLine)
```

---

## 📥 Parameter

| Parameter | Tipe | Deskripsi |
|-----------|------|-----------|
| `originalLine` | Array | Array/baris asli yang akan digabungkan dengan elemen dari array tambahan |
| `additionalLine` | Array | Array/baris tambahan yang dua elemen terakhirnya akan diambil |

---

## 📤 Nilai Kembalian

**Tipe:** `Array`

Mengembalikan array baru yang berisi semua elemen dari `originalLine` ditambah dengan dua elemen terakhir dari `additionalLine`.

---

## 💻 Kode Fungsi

```javascript
function decodeScripture(originalLine, additionalLine) {
  // Mengambil dua elemen terakhir dari array tambahan
  const lastTwoWords = additionalLine.slice(-2);
  
  // Menggabungkan array asli dengan dua elemen terakhir, lalu mengembalikan hasilnya
  return [...originalLine, ...lastTwoWords];
}
```

---

## 📝 Cara Kerja

1. **Mengambil Dua Elemen Terakhir**: Fungsi menggunakan metode `slice(-2)` untuk mengambil dua elemen terakhir dari `additionalLine`
2. **Menggabungkan Array**: Menggunakan spread operator (`...`) untuk menggabungkan `originalLine` dengan `lastTwoWords`
3. **Mengembalikan Hasil**: Mengembalikan array baru yang sudah digabungkan

---

## 🎯 Contoh Penggunaan

### Contoh 1: Menggabungkan Array Kata-kata

```javascript
const baris1 = ["Aku", "suka"];
const baris2 = ["makan", "nasi", "goreng", "pedas"];

const hasil = decodeScripture(baris1, baris2);
console.log(hasil);
```

**Output:**
```javascript
["Aku", "suka", "goreng", "pedas"]
```

---

### Contoh 2: Menggabungkan Array Angka

```javascript
const angkaAsli = [1, 2, 3];
const angkaTambahan = [4, 5, 6, 7, 8];

const hasil = decodeScripture(angkaAsli, angkaTambahan);
console.log(hasil);
```

**Output:**
```javascript
[1, 2, 3, 7, 8]
```

---

### Contoh 3: Menggabungkan Kalimat

```javascript
const kalimat1 = ["Belajar", "coding"];
const kalimat2 = ["itu", "sangat", "menyenangkan", "sekali"];

const hasil = decodeScripture(kalimat1, kalimat2);
console.log(hasil);
```

**Output:**
```javascript
["Belajar", "coding", "menyenangkan", "sekali"]
```

---

## ⚠️ Catatan Penting

- Jika `additionalLine` memiliki kurang dari 2 elemen, maka semua elemen yang ada akan diambil
- Fungsi ini tidak mengubah array asli (`originalLine` dan `additionalLine`), melainkan membuat array baru
- Pastikan kedua parameter yang diberikan adalah array yang valid

---

## 🎓 Tips untuk Pemula

- **Spread Operator (`...`)**: Digunakan untuk "membuka" isi array sehingga elemennya bisa digabungkan dengan array lain
- **Slice Method**: `slice(-2)` artinya ambil 2 elemen dari akhir array. Angka negatif dimulai dari akhir
- **Immutability**: Fungsi ini tidak mengubah array original, sehingga aman digunakan berulang kali

---

## 📚 Referensi

- [MDN: Array.prototype.slice()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/slice)
- [MDN: Spread Syntax](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Spread_syntax)
