# 💍 **createAntiqueJewelryBox**

## 📖 Deskripsi  
Fungsi `createAntiqueJewelryBox` digunakan untuk menghasilkan pola kotak perhiasan antik dalam bentuk **pola ASCII** berlapis. Setiap lapisan mewakili tingkat hiasan: semakin ke dalam, pola semakin sederhana, hingga ke inti minimalis. Pola ini berguna untuk visualisasi atau dekorasi teks.

## 🧾 Tanda Tangan Fungsi

```javascript
function createAntiqueJewelryBox(layers)
```

## 📥 Parameter

| Parameter | Tipe   | Deskripsi |
|-----------|--------|-----------|
| `layers`  | number | Bilangan bulat ≥ 0. Menentukan jumlah lapisan hiasan pada kotak perhiasan. |

## 🎨 Karakter yang Digunakan

| Karakter | Makna |
|----------|-------|
| `*` | Bingkai luar dan pola hiasan utama |
| `.` | Ruang kosong atau ornamen bagian dalam |

## 📐 Aturan Pola

- Ukuran kotak: `size = 2 * layers + 3`
- Baris pertama dan terakhir, serta kolom pertama dan terakhir selalu `*`
- Setiap lapisan bergantian antara `*` dan `.` secara pola persegi
- Bagian inti diisi dengan `.`

## ✅ Contoh Output

### Input: `layers = 2`

```
*******
*.....*
*.*.*.*
*.....*
*******
```

### Input: `layers = 3`

```
*********
*.......*
*.*****.*
*.*...*.*
*.*...*.*
*.*****.*
*.......*
*********
```

## 📚 Contoh Penggunaan

```javascript
console.log(createAntiqueJewelryBox(2));
```

## 💻 Kode

```javascript
function createAntiqueJewelryBox(layers) {
  const size = 2 * layers + 3;
  let box = [];

  for (let i = 0; i < size; i++) {
    let row = '';
    for (let j = 0; j < size; j++) {
      if (i === 0 || i === size - 1 || j === 0 || j === size - 1) {
        row += '*';
      } else {
        const layer = Math.min(i, j, size - 1 - i, size - 1 - j);
        if (layer === layers) {
          row += '.';
        } else if (layer % 2 === 0) {
          row += '*';
        } else {
          row += '.';
        }
      }
    }
    box.push(row);
  }

  return box.join('\n');
}
```
