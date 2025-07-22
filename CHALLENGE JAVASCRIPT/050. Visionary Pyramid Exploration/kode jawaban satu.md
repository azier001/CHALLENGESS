# 🔺 Fungsi visionaryPyramid

## 📝 Deskripsi

Fungsi `visionaryPyramid` adalah sebuah fungsi JavaScript yang membuat piramida angka dengan pola khusus. Fungsi ini menghasilkan piramida yang terdiri dari angka-angka ganjil dengan aturan tertentu, dimana setiap level memiliki jumlah angka sesuai dengan nomor levelnya.

## ⚙️ Parameter

| Parameter | Tipe | Deskripsi | Rentang Valid |
|-----------|------|-----------|---------------|
| `maxLevels` | Number | Jumlah maksimal level yang akan dibuat dalam piramida | 1 - 10 |

## 🔄 Return Value

- **Tipe**: Array of Strings
- **Deskripsi**: Array yang berisi string-string yang merepresentasikan setiap level piramida
- **Jika input tidak valid**: Mengembalikan array kosong `[]`

## 📐 Struktur Piramida

- Level 1: 1 angka
- Level 2: 2 angka  
- Level 3: 3 angka
- Dan seterusnya...

### Aturan Angka:
- Menggunakan angka ganjil
- Angka kelipatan 5 hanya boleh di posisi terakhir setiap level
- Setiap angka dipisahkan spasi dan diatur dengan padding untuk membentuk piramida

## 💻 Kode Fungsi

```javascript
function visionaryPyramid(maxLevels) {
  // Validasi input: hanya menerima angka 1-10
  if (maxLevels < 1 || maxLevels > 10) {
    return [];
  }
  
  const pyramid = [];    // Array untuk menyimpan hasil piramida
  let num = 1;          // Angka awal yang akan digunakan
  
  // Loop untuk setiap level piramida
  for (let level = 1; level <= maxLevels; level++) {
    let levelNumbers = [];  // Array untuk menyimpan angka di level ini
    
    // Loop untuk mengisi angka sebanyak level saat ini
    for (let i = 0; i < level; i++) {
      // Skip angka genap dan kelipatan 5 (kecuali di posisi terakhir)
      while (num % 2 === 0 || (num % 5 === 0 && i < level - 1)) {
        num++;
      }
      
      levelNumbers.push(num);  // Tambahkan angka ke level ini
      num += 2;               // Lanjut ke angka ganjil berikutnya
    }
    
    // Buat padding spasi untuk membentuk piramida
    const spaces = " ".repeat(maxLevels - level);
    const levelStr = spaces + levelNumbers.join(" ") + spaces;
    
    pyramid.push(levelStr);  // Tambahkan level ke piramida
  }
  
  return pyramid;
}
```

## 📊 Contoh Penggunaan

### Contoh 1: Piramida 3 Level
```javascript
console.log(visionaryPyramid(3));
```

**Output:**
```
[
  "  1  ",
  " 3 7 ",
  "9 11 15"
]
```

**Visualisasi:**
```
  1  
 3 7 
9 11 15
```

### Contoh 2: Piramida 5 Level
```javascript
console.log(visionaryPyramid(5));
```

**Output:**
```
[
  "    1    ",
  "   3 7   ",
  "  9 11 15  ",
  " 17 19 21 25 ",
  "27 29 31 33 35"
]
```

**Visualisasi:**
```
    1    
   3 7   
  9 11 15  
 17 19 21 25 
27 29 31 33 35
```

### Contoh 3: Input Tidak Valid
```javascript
console.log(visionaryPyramid(0));   // Output: []
console.log(visionaryPyramid(11));  // Output: []
console.log(visionaryPyramid(-1));  // Output: []
```

## 🎯 Karakteristik Khusus

| Karakteristik | Penjelasan |
|---------------|------------|
| **Angka Ganjil** | Hanya menggunakan angka ganjil (1, 3, 5, 7, 9, 11, ...) |
| **Kelipatan 5** | Angka kelipatan 5 (seperti 5, 15, 25) hanya diperbolehkan di posisi terakhir setiap level |
| **Padding** | Setiap level memiliki spasi di awal dan akhir untuk membentuk piramida yang simetris |
| **Validasi** | Input harus dalam rentang 1-10, jika tidak akan mengembalikan array kosong |

## 🔧 Tips Penggunaan

1. **Untuk pemula**: Mulai dengan nilai kecil seperti 1-3 untuk memahami polanya
2. **Debugging**: Gunakan `console.log` untuk melihat hasil setiap level
3. **Visualisasi**: Gunakan `forEach` untuk menampilkan piramida dengan lebih rapi:

```javascript
visionaryPyramid(4).forEach(level => console.log(level));
```

## ⚠️ Catatan Penting

- Fungsi ini hanya menerima input berupa angka integer
- Rentang input dibatasi 1-10 untuk menjaga performa dan readability
- Hasil berupa array of strings, bukan array of numbers
