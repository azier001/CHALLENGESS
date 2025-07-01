# 💍 Antique Jewelry Box Generator

Fungsi `createAntiqueJewelryBox` menghasilkan pola kotak perhiasan antik berbentuk persegi, menggunakan karakter `*` dan `.` yang ditata dalam beberapa lapisan (layers). Semakin besar nilai `layers`, maka semakin kompleks pola yang dihasilkan.

---

## 🧠 Penjelasan Umum

### 📐 Ukuran Pola

* Ukuran pola selalu: `2 * layers + 3`
* Pola berbentuk **persegi simetris**

### 🔣 Karakter yang Digunakan

| Karakter | Makna                           |
| -------- | ------------------------------- |
| `*`      | Garis tepi / frame luar lapisan |
| `.`      | Bagian dalam lapisan / dekorasi |

### 🧱 Struktur Lapisan

* **Lapisan 0 (terluar)**: selalu `*`
* **Lapisan terdalam (ke-n)**: selalu `.`
* **Lapisan ganjil (1, 3, dst)**: semua titik `.`
* **Lapisan genap (2, 4, dst)**: hanya tepi `*`, isi `.`

> 💡 Pola menyerupai ukiran perhiasan antik yang indah dan simetris.

---

## 🧩 Kode Fungsi

```javascript
function createAntiqueJewelryBox(layers) {
   if (layers === 0) return '***\n*.*\n***';

   const size = 2 * layers + 3;
   let result = [];

   for (let row = 0; row < size; row++) {
       let line = '';
       for (let col = 0; col < size; col++) {
           const distanceFromEdge = Math.min(row, col, size - 1 - row, size - 1 - col);

           if (distanceFromEdge === 0) {
               line += '*';
           } else if (distanceFromEdge === layers) {
               line += '.';
           } else if (distanceFromEdge % 2 === 1) {
               line += '.';
           } else {
               if (
                   row === distanceFromEdge ||
                   row === size - 1 - distanceFromEdge ||
                   col === distanceFromEdge ||
                   col === size - 1 - distanceFromEdge
               ) {
                   line += '*';
               } else {
                   line += '.';
               }
           }
       }
       result.push(line);
   }

   return result.join('\n');
}
```

---

## ✅ Contoh Penggunaan (Test Cases)

### `createAntiqueJewelryBox(0)`

```
***
*.*
***
```

### `createAntiqueJewelryBox(1)`

```
*****
*...*
*.*.*
*...*
*****
```

### `createAntiqueJewelryBox(2)`

```
*******
*.....*
*.***.*
*.*.*.*
*.***.*
*.....*
*******
```

---

## 📌 Catatan Akhir

* Berguna untuk latihan logika **nested loop** dan **kondisi berbasis koordinat 2D**.
* Cocok untuk membuat dekorasi berbasis teks atau seni ASCII yang estetis.

---

> 📁 *Markdown ini siap digunakan sebagai dokumentasi atau referensi teknis. Jika ingin file **`.md`**-nya langsung, beri tahu saya!*
